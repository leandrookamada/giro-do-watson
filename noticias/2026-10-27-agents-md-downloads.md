---
titulo: "AGENTS.md malicioso na pasta Downloads tenta sequestrar agente de código: um caso real, bloqueado, e testes que mostram Codex e Claude Code obedecendo"
data: 2026-10-27
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 75
contestado: false
checagem: dupla
tags: [tech, seguranca-de-ia, malware, claude-code, codex]
---
A Forever Security relatou ter encontrado um `AGENTS.md` malicioso (~13 KB) na pasta `~/Downloads` de um cliente. Quando o usuário abriu um agente de código nessa pasta, o agente tentou instalar o pacote npm `function-color`, da campanha de malware MALFEX documentada pela Checkmarx. A ferramenta da Forever bloqueou a instalação antes de o malware rodar, e não se sabe como o arquivo chegou ali. Nos testes da própria Forever, com payload inofensivo, o Codex obedeceu em mais de 90% das vezes e o Claude Code em cerca de 50%. O BleepingComputer reproduziu que Chrome, Edge e Firefox salvam o arquivo em Downloads sem aviso.

**Por que importa:** quem usa Claude Code, Codex ou similares não deve abrir o agente em `~/Downloads` nem em `~`. Leia `AGENTS.md` e `CLAUDE.md` que você não escreveu, mantenha aprovações e sandbox ligados e trate a instalação de `function-color` como sinal de comprometimento.

## Evidências
- [Forever Security: pesquisa original](https://forever.security/blog/hijacking-ai-agents-via-downloads-folder)
- [BleepingComputer (com teste próprio)](https://www.bleepingcomputer.com/news/security/ai-coding-agents-hijacked-using-agentsmd-file-in-downloads-folder/)
- [CSO Online](https://www.csoonline.com/article/4240222/malicious-downloads-can-trick-ai-coding-agents-into-compromising-themselves.html)
- [Checkmarx: campanha MALFEX](https://checkmarx.com/zero-post/malfex-npm-malware-campaign-three-payloads-and-an-adversary-that-signs-their-work/)

## Red flags
- "Ataque em uso real" é **um** caso, bloqueado, sem vítima comprometida e com origem desconhecida. A entrega por site malicioso foi só demonstrada em laboratório.
- Não é técnica nova: é prompt injection indireta via arquivo de instrução, já conhecida. A novidade é o vetor da pasta Downloads.
- As taxas (>90% e ~50%) vêm dos testes da própria Forever, sem número de tentativas, e ela vende monitoramento de agentes. Nenhum dos achados foi validado de forma independente.
- Um analista da IDC chamou o caso de "alerta antecipado crível, não evidência de exploração generalizada".

Edição: [[2026-10-27-tech]]
