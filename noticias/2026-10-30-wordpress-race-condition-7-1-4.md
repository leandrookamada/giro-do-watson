---
titulo: "WordPress 7.1.4 corrige condição de corrida no update do core com potencial RCE; Wordfence vê sondagens, sem comprometimento confirmado"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 68
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, web, wordpress]
---
O WordPress 7.1.4 (28/10) corrigiu uma condição de corrida no processo de atualização do core, com potencial execução remota de código; o crédito oficial vai para Umut Bayram e não há CVE nem CVSS. A Patchstack a classifica como não autenticada, mas de complexidade alta: exige acertar uma janela de segundos durante uma atualização e que `wp-content/upgrade/` seja acessível pela web. Via SecurityWeek, a Wordfence registrou mais de 18.500 requisições a `setup-config.php` em staging em 21 horas, sem comprometimento confirmado.

**Por que importa:** é falha no core, não em plugin; sites devem atualizar para a 7.1.4 (há backports), mas o risco prático é limitado a quem está no meio de uma atualização.

## Evidências
- [SecurityWeek: falha do WordPress na mira de atacantes](https://www.securityweek.com/fresh-wordpress-vulnerability-in-attackers-crosshairs/)
- [Patchstack: release de segurança 7.1.4](https://patchstack.com/articles/wordpress-7-1-4-security-release/)

## Red flags
- "Sob tentativa de exploração" vem de telemetria da Wordfence (vende firewall) via uma única matéria; são sondagens, não exploração bem-sucedida. A Patchstack diz não considerar a exploração prática.
- Sem CVE e sem CVSS publicado; relatos divergem sobre autenticação (um diz que os detalhes não foram divulgados).
- Posts da Wordfence e da WordPress.org não puderam ser lidos; o release oficial só foi visto em resultado de busca.
- A manchete soa como zero-day, mas há patch desde 28/10.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · release do WordPress.org, Patchstack e SecurityWeek corroboram a falha e as sondagens sem comprometimento comprovado

Edição: [[2026-10-30-tech]]
