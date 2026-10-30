---
titulo: "Alpine Linux reconstrói seu GitLab após tentativas de explorar a CVE-2026-97229 oito dias depois da correção; sem prova de sucesso"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: CONFIRMADO
confianca: 85
contestado: false
checagem: simples
tags: [tech, exploracao-ativa, open-source, alpine-linux, gitlab]
---
O Alpine Linux relatou em 28/10 que, em 20 e 21/10, uma conta recém-criada enviou configurações de CI manipuladas ao GitLab do projeto, derrubando processos 8 vezes e avançando parcialmente em 4 delas. A falha é a CVE-2026-97229 (CVSS 10, estouro de inteiro no compilador de regex de CI), corrigida pelo GitLab em 12/10. O Alpine não achou prova de que o exploit funcionou, mas tratou a instância como comprometida, trocou segredos e a reconstruiu. Diz que as chaves de assinatura de pacotes nunca estiveram no servidor e que não viu adulteração em pacotes. A imagem própria continuava vulnerável porque a correção completa depende de um patch no Ruby.

**Por que importa:** quem roda GitLab próprio, sobretudo com cadastro aberto, deve estar em 19.4.2, 19.3.5 ou 19.2.8 e conferir o Ruby da imagem.

## Evidências
- [Relato do Alpine Linux](https://alpinelinux.org/posts/GitLab-security-incident-CVE-2026-97229.html)
- [Patch release do GitLab](https://docs.gitlab.com/releases/patches/patch-release-gitlab-19-4-2-released/)
- [Rapid7](https://www.rapid7.com/blog/post/etr-cve-2026-97229-critical-unauthenticated-remote-code-execution-in-gitlab/)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/gitlab-warns-of-max-severity-rce-flaw-in-regex-compiler-engine/)

## Red flags
- O ataque ao Alpine tem uma única fonte primária, a própria vítima.
- A parte técnica sobre o patch do Ruby não foi verificada de forma independente.
- O BleepingComputer cita 19.3.4 como corrigida; o GitLab diz 19.3.5.

Edição: [[2026-10-29-tech]]
