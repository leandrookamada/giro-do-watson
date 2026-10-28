---
titulo: "Dream diz que atacante encadeou PHP2Shell e Fragnesia e virou root em 24 firewalls, um deles em ambiente afiliado ao governo dos EUA; vínculo com a China é só indício"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 66
contestado: false
checagem: dupla
tags: [tech, exploracao-ativa, incidente, linux, php2shell]
---
A Dream, empresa de segurança, relatou que em 23 e 24/10 um atacante encadeou PHP2Shell (CVE-2026-109618 e -109619, execução como `nobody`) com Fragnesia (CVE-2026-46300, escalada local no kernel Linux) numa única requisição HTTP. O ataque deu root em 25 servidores: 24 firewalls de perímetro de um fabricante não nomeado e 1 servidor de gerenciamento. Os alvos saíram de uma busca no FOFA por cerca de 19.000 firewalls. Num ambiente que a Dream diz ser afiliado ao governo dos EUA, três servidores foram atingidos. A Dream não nomeia grupo nem fabricante, e não confirmou o sucesso das etapas seguintes no Active Directory.

**Por que importa:** confirma que PHP2Shell (no KEV desde ontem) e Fragnesia, ambos com correção e PoC públicos, já são usados juntos contra equipamentos de borda. Quem expõe firewalls com PHP deve aplicar as duas correções.

## Evidências
- [Dream: relatório original](https://dreamgroup.com/blog/chained-php2shell-exploit-roots-25-servers)
- [SecurityWeek](https://www.securityweek.com/china-linked-hackers-exploit-php2shell-to-root-firewalls/)
- [Unite.ai](https://www.unite.ai/dream-reports-php2shell-attack-chain-that-compromised-25-servers/)
- [Security Boulevard](https://securityboulevard.com/2026/10/cisa-says-php2shell-flaw-under-attack-as-reports-of-more-come-in/)

## Red flags
- A manchete do SecurityWeek afirma "China-linked", mas a Dream só fala em "potencial" operação "Chinese-nexus", sem ator nomeado. Os indícios (países-alvo, uso do FOFA, DeepSeek/Kimi configurados, horários UTC+8, prompts em chinês) são circunstanciais e fáceis de forjar.
- Fonte única e comercial: a imprensa só reescreve a Dream. Não há vítima nomeada nem confirmação da CISA para este incidente.
- O número de servidores do ambiente governamental varia entre os textos (1, 2 ou 3); a fonte primária diz 3.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · encadeamento confirmado pela Dream, sem fonte independente para o incidente nem para o vínculo chinês.

Edição: [[2026-10-28-tech]]
