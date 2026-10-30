---
titulo: "Crate zip do Rust (até 9.0.4) tem divergência de cabeçalhos que pode burlar scanners e sobrescrever arquivos; correção da 9.0.5 precisa ser ativada"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 76
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, open-source, rust]
---
O GitHub Advisory GHSA-m665-v7pm-7grj (CVE-2026-115905, 28/10) classifica como crítica uma falha no crate `zip` do Rust, versões até 9.0.4. O `ZipArchive` lê o diretório central e o `ZipStreamReader` lê o cabeçalho local; um arquivo montado com cabeçalhos divergentes pode parecer inofensivo para um scanner e ser extraído com outro nome, sobrescrevendo arquivos. A execução de código só ocorre em pipelines que usam os dois leitores e sobrescrevem algo executado depois. A versão 9.0.5 traz a validação de consistência, mas desligada por padrão.

**Por que importa:** quem extrai ZIPs não confiáveis com o crate deve atualizar e ativar `enforce_header_consistency` ou `validate_header_consistency()`; só atualizar não basta.

## Evidências
- [GitHub Advisory GHSA-m665-v7pm-7grj](https://github.com/advisories/GHSA-m665-v7pm-7grj)
- [Commit da correção](https://github.com/zip-rs/zip2/commit/8068ab480ccf8daa7411424e365fcdbe6d09443e)
- [Release v9.0.5](https://github.com/zip-rs/zip2/releases/tag/v9.0.5)

## Red flags
- CVSS 10.0 e "RCE" na manchete ignoram que o ataque depende de um pipeline específico; o próprio advisory diz "possível" RCE.
- A correção é opt-in; o advisory diz que atualizar resolve.
- As notas da 9.0.5 não mencionam segurança.
- Sem exploração conhecida nem cobertura independente.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · advisory e projeto confirmam a falha crítica e a possível sobrescrita.

Edição: [[2026-10-29-tech]]
