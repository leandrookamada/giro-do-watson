---
titulo: "Polymarket confirma comprometimento de fornecedor; script malicioso drenou cerca de US$ 2 a 2,7 mi de traders"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 80
contestado: false
checagem: dupla
tags: [tech, incidente, web, polymarket, debugbear]
---
A Polymarket disse que "um de nossos provedores terceirizados foi comprometido", interrompeu a negociação por cerca de uma hora e prometeu reembolsar os afetados. Pesquisadores da Hudson Rock apontam a DebugBear (monitoramento de desempenho de sites); a própria DebugBear diz ter um incidente de segurança em andamento. O script servido por cdn.debugbear.com reaproveitava a sessão já autenticada do trader para vender posições ou transferir tokens. Estimativas on-chain de terceiros vão de US$ 2,1 mi a US$ 2,7 mi.

**Por que importa:** é ataque de cadeia de suprimentos via script de front-end de terceiros, que atinge usuários mesmo sem falha na plataforma principal; é a segunda vez que a Polymarket sofre algo parecido (junho).

## Evidências
- [The Record: Polymarket confirma ataque via terceiro](https://therecord.media/polymarket-confirms-cyberattack-third-party)
- [BleepingComputer: análise do script e US$ 2,5 mi rastreados](https://www.bleepingcomputer.com/news/security/polymarket-halts-trading-after-crypto-draining-script-breach-25m-traced/)
- [SecurityWeek: US$ 2 mi drenados em ataque de cadeia de suprimentos](https://www.securityweek.com/2-million-drained-from-polymarket-traders-in-new-supply-chain-attack/)

## Red flags
- A Polymarket não nomeou o fornecedor nem divulgou perdas; a ligação com a DebugBear vem da Hudson Rock e da fala da própria DebugBear.
- Valores divergem entre fontes (2,19 a 2,71 mi) e 731 endereços não equivalem a 731 vítimas.
- Ainda não se sabe como o script foi adulterado nem se outros clientes da DebugBear foram afetados.
- O script reaproveita a sessão; não rouba credenciais ou chaves.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · declaração da Polymarket e análises independentes confirmam o fornecedor comprometido e o script que drenou US$ 2 a 2,7 mi

Edição: [[2026-10-30-tech]]
