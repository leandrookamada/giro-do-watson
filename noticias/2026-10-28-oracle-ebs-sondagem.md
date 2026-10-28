---
titulo: "Honeypots registram as primeiras sondagens da SQL injection crítica do Oracle E-Business Suite (CVE-2026-101767), corrigida em 20/10"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 83
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, web, oracle]
---
A CVE-2026-101767 é uma SQL injection sem autenticação no servlet TCF (`/OA_HTML/AppsTCFServer`) do Oracle E-Business Suite 12.2.3 a 12.2.15, com CVSS 9.8. Segundo a Horizon3.ai, que a descobriu e reportou em 24/07, ela leva a execução de comandos no sistema. A Oracle corrigiu no CPU de 20/10. Em 27/10, os decoys da Defused registraram tentativas exploratórias. O registro CVE marca exploração "none", e a falha não está no KEV.

**Por que importa:** há mais de 670 instâncias de EBS expostas na internet (Shadowserver). Quem não aplicou o CPU de outubro deve aplicar ou, até lá, restringir a camada web e tirar `/OA_HTML/AppsTCFServer` da allowlist.

## Evidências
- [Horizon3.ai: análise técnica](https://horizon3.ai/attack-research/vulnerabilities/cve-2026-101767/)
- [Registro CVE](https://raw.githubusercontent.com/CVEProject/cvelistV5/main/cves/2026/101xxx/CVE-2026-101767.json)
- [SecurityWeek](https://www.securityweek.com/hackers-start-probing-fresh-oracle-ebs-vulnerability/)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-now-scanning-systems-for-recently-patched-oracle-flaw/)

## Red flags
- A sondagem tem uma única origem (Defused, que vende decoys), sem metodologia; não há comprometimento confirmado.
- O advisory da Oracle não foi lido diretamente (403).
- Não confundir com a CVE-2026-46817, outra falha do EBS, essa sim explorada.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · falha confirmada e tentativas de sondagem registradas.

Edição: [[2026-10-28-tech]]
