---
titulo: "Cisco corrige negação de serviço explorada em ASA e FTD (CVE-2026-76418) que derruba firewalls com SSL VPN e autenticação secundária"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 81
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, cisco]
---
A Cisco publicou em 28/10 o aviso cisco-sa-asaftd-tunnel-dos-s6mgkb75 para a CVE-2026-76418 (CVSS 8.6). Um atacante remoto sem autenticação pode forçar o reinício de firewalls ASA e FTD com Remote Access SSL VPN, desde que algum tunnel group use autenticação secundária. A Cisco diz que soube de exploração ativa em outubro, sem divulgar autoria nem IOCs. Não há workaround; a mitigação (tirar a autenticação secundária) enfraquece a VPN. Versões corrigidas incluem ASA 9.16.4.104, 9.18.4.96, 9.20.4.50, 9.22.3.200, 9.23.1.48 e 9.24.1.27, e FTD 7.0.11, 7.2.13, 7.4.9, 7.6.7, 7.7.14, 10.0.3 e 10.1.1.

**Por que importa:** quem tem ASA/FTD com VPN e MFA via autenticação secundária deve atualizar já; o Shadowserver vê mais de 51 mil ASA com SSL VPN expostos.

## Evidências
- [Aviso da Cisco](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-tunnel-dos-s6mgkb75)
- [SecurityWeek](https://www.securityweek.com/attackers-exploit-second-cisco-firewall-vpn-zero-day-since-august/)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/cisco-warns-of-firewall-zero-day-exploited-to-crash-ssl-vpn-devices/)
- [Qualys: zero-day de agosto (CVE-2026-20349)](https://threatprotect.qualys.com/2026/08/13/cisco-asa-and-ftd-dos-vulnerability-exploited-in-the-wild-cve-2026-20349/)

## Red flags
- A manchete omite o pré-requisito (autenticação secundária num tunnel group); não é todo ASA/FTD.
- O impacto é só DoS (reinício), não execução de código.
- "Segundo zero-day desde agosto" é contagem da imprensa, não da Cisco.
- Veículos divergem sobre a mitigação; desativar a autenticação secundária reduz a segurança da VPN.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · aviso da Cisco e imprensa confirmam o DoS explorado.

Edição: [[2026-10-29-tech]]
