---
titulo: "Lumen descreve a rede Silent Train do Volt Typhoon; Talos diz que a infraestrutura de malware que rouba chaves no Cisco SD-WAN se sobrepõe a ela"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 75
contestado: false
checagem: dupla
tags: [tech, exploracao-ativa, malware, volt-typhoon, cisco]
---
A Lumen (Black Lotus Labs) descreve a Silent Train como rede encoberta do Volt Typhoon, com cadeias rotativas de roteadores e dispositivos comprometidos, usada em quatro campanhas de zero-day confirmadas e uma provável. Em 28/10, a Cisco Talos publicou o malware KeyDrift (módulos PolyFlame e LittleFilch), que o cluster UAT-11473 instalou no Cisco Catalyst SD-WAN explorando a CVE-2026-20127 (CVSS 10, corrigida em fevereiro) para roubar material de chaves. A Talos avalia com alta confiança que a infraestrutura desse cluster se sobrepõe à Silent Train, mas não diz que ele é o Volt Typhoon.

**Por que importa:** quem tem Catalyst SD-WAN sem o patch de fevereiro deve investigar comprometimento, não só atualizar.

## Evidências
- [Lumen: Silent Train](https://www.lumen.com/blog/en-us/silent-train-volt-typhoon-operational-framework)
- [Cisco Talos: UAT-11473 e KeyDrift](https://blog.talosintelligence.com/uat-11473-keydrift/)
- [SecurityWeek](https://www.securityweek.com/cisco-sd-wan-zero-day-exploitation-tied-to-volt-typhoons-silent-train-network/)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/volt-typhoon-hides-zero-day-attacks-using-silent-train-framework/)

## Red flags
- A manchete funde dois atores: a Talos atribui ao UAT-11473 e fala só em sobreposição de infraestrutura com o Volt Typhoon.
- Em fevereiro a Talos atribuiu a exploração da mesma CVE a outro cluster (UAT-8616).
- A Lumen não menciona o KeyDrift; a ligação depende só da Talos.
- A Talos chama a atividade de histórica, sem data.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · Lumen, Talos e SecurityWeek corroboram as alegações centrais.

Edição: [[2026-10-29-tech]]
