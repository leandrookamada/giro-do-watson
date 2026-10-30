---
titulo: "TeamViewer corrige estouro de inteiro (CVSS 8,8) que pode causar DoS ou, possivelmente, execução de código ao conectar a host malicioso"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 85
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, teamviewer]
---
O boletim TV-2026-1011 (27/10) descreve o CVE-2026-111585, um estouro de inteiro (CWE-190) no processamento de tela do controle remoto, com CVSS 8,8 (exige interação do usuário). Um host malicioso pode causar negação de serviço ou, "dependendo da plataforma", possivelmente executar código com os privilégios do visualizador; o técnico precisa iniciar sessão com o host do atacante. Afeta Full Client, Portable e o app Remote Control para Android antes da 15.83. A TeamViewer não conhece exploração ativa, e a pesquisa é da Remedio.

**Por que importa:** técnicos de suporte que se conectam a máquinas de terceiros são o alvo; atualize para 15.83 (ou 15.64.10 / 14.7.48868 nas linhas legadas).

## Evidências
- [TeamViewer: boletim TV-2026-1011](https://www.teamviewer.com/en-us/resources/trust-center/security-bulletins/tv-2026-1011/)
- [SecurityWeek: falha deixa hosts maliciosos assumirem máquinas de técnicos](https://www.securityweek.com/teamviewer-flaw-could-let-malicious-hosts-take-over-support-technicians-machines/)

## Red flags
- A manchete "take over"/execução de código é mais forte que o texto do fabricante, que fala de DoS e RCE "possível"; não há PoC público.
- Sem exploração conhecida nem KEV; escrever "explorada" seria exagero.
- NVD/OpenCVE ainda sem enriquecimento; a pesquisa da Remedio não foi aberta.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · boletim do fabricante e SecurityWeek confirmam CVE, CVSS, correção e ausência de exploração conhecida

Edição: [[2026-10-30-tech]]
