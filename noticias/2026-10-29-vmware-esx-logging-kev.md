---
titulo: "CISA põe no KEV falha de logging de baixa severidade do VMware ESX (CVE-2026-41709); CrowdStrike diz que grupo chinês a usou para apagar rastros"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 82
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, vmware, cisa]
---
A CISA incluiu a CVE-2026-41709 no KEV em 28/10, com prazo de 11/11. A falha deixa um administrador do ESX executar certas operações sem que fiquem registradas em log. A Broadcom a corrigiu em 29/07 (VMSA-2026-0006) com severidade baixa (CVSS 2.7). Segundo relatório da CrowdStrike, o grupo WARP PANDA, ligado à China, explorou a falha como zero-day em intrusões contra escritórios de advocacia nos EUA até o início de 2026. A CISA não descreve os ataques.

**Por que importa:** quem não aplicou o patch de julho no ESX pode ter invasores sem trilha de auditoria; a falha não dá acesso, mas esconde o que um admin já comprometido faz.

## Evidências
- [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search_api_fulltext=CVE-2026-41709)
- [Registro CVE](https://raw.githubusercontent.com/CVEProject/cvelistV5/main/cves/2026/41xxx/CVE-2026-41709.json)
- [Aviso da Broadcom](https://support.broadcom.com/web/ecx/support-content-notification/-/external/content/SecurityAdvisories/0/38017)
- [CrowdStrike 2026 Legal Threat Landscape Report](https://www.crowdstrike.com/en-us/blog/crowdstrike-2026-legal-threat-landscape-report/)
- [SecurityWeek](https://www.securityweek.com/chinese-hackers-quietly-used-low-severity-esxi-logging-flaw-as-zero-day/)

## Red flags
- A atribuição à China vem só da CrowdStrike (fornecedor), sem corroboração independente.
- A manchete junta KEV e atribuição como se fossem a mesma evidência.
- Exige privilégio de administrador; "zero-day" soa maior do que o impacto (anti-forense).

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · KEV e CrowdStrike corroboram inclusão e uso como zero-day.

Edição: [[2026-10-29-tech]]
