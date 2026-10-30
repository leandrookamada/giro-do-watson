---
titulo: "Talos detalha o malware KeyDrift do grupo UAT-11473 contra controladores Cisco SD-WAN sem o patch de fevereiro (CVE-2026-20127)"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 82
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, malware, cisco]
---
A Cisco Talos passou a rastrear o grupo UAT-11473, que explorou o CVE-2026-20127 (bypass de autenticação no Cisco Catalyst SD-WAN, CVSS 10) para instalar o framework KeyDrift, que captura material de chave AES-256 de IPsec. Os alvos descritos são espaço/satélite, defesa/aeroespacial e think tanks. A falha foi corrigida em fevereiro e está no KEV desde 25/02/2026. Só o rastreamento do grupo é novo.

**Por que importa:** controladores SD-WAN expostos e sem o patch de fevereiro continuam sendo porta de entrada para espionagem de alto nível e roubo de chaves de túneis.

## Evidências
- [Cisco Talos: UAT-11473 e KeyDrift](https://blog.talosintelligence.com/uat-11473-keydrift/)
- [Registro CVE-2026-20127 (CNA Cisco)](https://raw.githubusercontent.com/CVEProject/cvelistV5/main/cves/2026/20xxx/CVE-2026-20127.json)
- [BleepingComputer: hackers exploram falha do Cisco SD-WAN com KeyDrift](https://www.bleepingcomputer.com/news/security/hackers-exploit-cisco-sd-wan-flaw-to-deploy-custom-keydrift-malware/)

## Red flags
- A manchete "grupo recém-identificado explora falha" dá ar de novidade; a falha tem 8 meses e patch, e a atividade é histórica.
- O UAT-8616 (zero-day desde 2023) é outro cluster; a imprensa mistura os atores.
- Ligação com o Volt Typhoon ("Silent Train") é sobreposição de infraestrutura, não atribuição firme.
- O advisory da Cisco em si não foi lido; só o registro CVE e o KEV.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · blog da Talos e imprensa corroboram o grupo, a CVE e o malware; vínculo com Volt Typhoon é só sobreposição

Edição: [[2026-10-30-tech]]
