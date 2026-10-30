---
titulo: "Palo Alto passa a relatar exploração do PHP2Shell contra interfaces de gestão do PAN-OS expostas; hotfixes ainda saem por branch"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 74
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, palo-alto-networks, php2shell]
---
O advisory da Palo Alto para a CVE-2026-109618, atualizado em 29/10, diz que as falhas PHP2Shell afetam PAN-OS e Panorama só pela interface de gestão e que "foi observada exploração ativa" contra interfaces expostas à internet. GlobalProtect e Captive Portal não são afetados. A CISA pôs as falhas no KEV em 26/10. As correções do PAN-OS saem como hotfixes por branch entre 25 e 29/10, com uma ainda prevista para 30/10. Em 25/10 a Unit 42, da própria Palo Alto, retratou a ligação que tinha feito entre o PHP2Shell e uma intrusão num órgão europeu.

**Por que importa:** quem expõe a gestão do PAN-OS à internet deve restringi-la a IPs confiáveis e aplicar o hotfix do seu branch.

## Evidências
- [Advisory da Palo Alto](https://security.paloaltonetworks.com/CVE-2026-109618)
- [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog)
- [Unit 42: retratação](https://unit42.paloaltonetworks.com/cve-2026-109618-cve-2026-109619/)
- [Help Net Security (22/10)](https://www.helpnetsecurity.com/2026/10/22/php2shell-vulnerability-fortinet-cisco-palo-alto-networks/)

## Red flags
- "Já corrigidas" vale para o PHP upstream; no PAN-OS os hotfixes ainda estavam saindo em 29/10.
- Até 22-24/10 a Palo Alto dizia não conhecer exploração contra seus produtos; não se sabe quando o advisory mudou.
- A exploração confirmada pela CISA e pela imprensa é contra PHP genérico (Apache mod_php), não especificamente PAN-OS.
- O artigo do The Hacker News não pôde ser lido (403).

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · o advisory declara exploração ativa, corroborado pelo KEV.

Edição: [[2026-10-29-tech]]
