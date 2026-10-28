---
titulo: "ZDI detalha que o zero-day do PeopleSoft usado pela ShinyHunters entre maio e junho eram três falhas, corrigidas sob uma só CVE"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 80
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, oracle, shinyhunters]
---
A Zero Day Initiative, que reportou o problema à Oracle, publicou que a falha corrigida como CVE-2026-35273 (CVSS 9.8, PeopleTools 8.61 e 8.62) são três vulnerabilidades: SSRF no PSIGW, escrita arbitrária de arquivo no PSEMHUB e desserialização insegura no PSEMHUB. Encadeadas, dão execução remota sem login. A ZDI está pedindo CVEs separadas. A exploração pela ShinyHunters (UNC6240) foi observada pela Mandiant entre 27/05 e 09/06/2026, antes do advisory da Oracle de 10/06; a falha está no KEV desde 12/06.

**Por que importa:** não muda a ação para quem já aplicou o patch de junho; ajuda quem investiga incidentes a procurar os três estágios (SSRF, escrita de arquivo e desserialização) nos logs.

## Evidências
- [ZDI: análise técnica](https://www.zerodayinitiative.com/blog/2026/10/20/cve-2026-35273-ssrf-to-rce-in-oracle-peoplesoft)
- [Cybersecurity Dive](https://www.cybersecuritydive.com/news/shinyhunters-exploitation-critical-flaw-oracle-peoplesoft/822796/)
- [Google Threat Intelligence (Mandiant)](https://cloud.google.com/blog/topics/threat-intelligence/shinyhunters-targets-education-sector-oracle-exploit)

## Red flags
- "Explora desde maio" soa como campanha em curso; o caso tem mais de quatro meses, e a novidade é só a análise técnica.
- A divisão em três falhas é da ZDI; a Oracle não a comentou.
- O relatório da Mandiant e o advisory da Oracle não foram lidos diretamente; The Hacker News deu 403.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · ZDI detalha as três falhas e a Mandiant confirma a exploração no período.

Edição: [[2026-10-28-tech]]
