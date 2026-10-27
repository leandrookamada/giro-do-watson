---
titulo: "Apple leva ao iOS 18.7.11 a correção do CoreGraphics que pode ter sido explorada em ataque direcionado"
data: 2026-10-27
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 85
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, apple]
---
Em 26/10, a Apple lançou o iOS/iPadOS 18.7.11 para aparelhos que não recebem o iOS 26/27: iPhone XS, XS Max e XR, iPad de 7ª geração e outros. A versão traz a correção da CVE-2026-86950, uma escrita fora dos limites no CoreGraphics que executa código ao processar arquivo malicioso, crédito da Meta Product Security. A Apple diz que a falha "pode ter sido explorada em um ataque extremamente sofisticado contra indivíduos específicos". A mesma correção saiu em 28/09 no iOS 26.7.1, e a falha está no KEV da CISA desde 29/09. No mesmo dia saíram o iOS 27.2 e o macOS 27.2, com cerca de 286 correções segundo o SecurityWeek, nenhuma nova marcada como explorada.

**Por que importa:** quem tem iPhone ou iPad antigo (linha iOS 18) agora tem a correção. O ataque foi direcionado, então o risco para o usuário comum é baixo, mas atualizar continua sendo o recomendado.

## Evidências
- [Apple: iOS/iPadOS 18.7.11](https://support.apple.com/en-us/149225)
- [Apple: correção original (26.7.1)](https://support.apple.com/en-us/149226)
- [BleepingComputer](https://www.bleepingcomputer.com/news/apple/apple-backports-coregraphics-zero-day-patches-to-older-iphones/)
- [SANS ISC](https://isc.sans.edu/diary/rss/33458)

## Red flags
- "Zero-day explorado" é mais forte que a Apple, que diz "pode ter sido explorada". E não é zero-day novo: é a falha de setembro levada a aparelhos antigos.
- A contagem de falhas corrigidas varia: cerca de 286 (SecurityWeek, que desconta sobreposições) contra 304 (SANS ISC). Não é número da Apple.
- Um repositório de "PoC" no GitHub citado junto trata de outras CVEs (112610/112611), foi criado no próprio dia e não tem relação demonstrada com esta falha. Não execute.

Edição: [[2026-10-27-tech]]
