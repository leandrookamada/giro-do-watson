---
titulo: "Drupal Commerce Core tem bypass de autorização sem login, já explorado segundo o aviso oficial; atualize para 3.3.13 ou 8.x-2.41"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: CONFIRMADO
confianca: 89
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, web, drupal]
---
O aviso SA-CONTRIB-2026-254, de 28/10, descreve um bypass de acesso por falta de autorização no módulo Commerce Core (CVE-2026-118539, risco 21/25 "highly critical") e diz que ele "está sendo explorado ativamente". Qualquer atacante sem autenticação pode explorar. A correção está nas versões 3.3.13 e 8.x-2.41, e o Drupal recomenda auditar os pedidos da loja.

**Por que importa:** o módulo está em mais de 42 mil sites de e-commerce; lojas sem patch podem ter pedidos e pagamentos manipulados.

## Evidências
- [Drupal.org: SA-CONTRIB-2026-254](https://www.drupal.org/sa-contrib-2026-254)
- [BleepingComputer: Drupal alerta para falha crítica explorada](https://www.bleepingcomputer.com/news/security/drupal-warns-of-critical-commerce-core-flaw-exploited-in-attacks/)
- [SecurityWeek: falha do Commerce Core explorada contra lojas](https://www.securityweek.com/drupal-commerce-core-vulnerability-exploited-against-online-stores/)

## Red flags
- A exploração ativa é declaração do próprio fabricante; não há KEV nem telemetria independente, e o Drupal não revelou método, atacantes nem se foi zero-day.
- O número de 42 mil é o total de instalações do módulo, não de sites vulneráveis.
- CVE não conferida no cve.org; BleepingComputer diz "critical" e o aviso "highly critical".

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · aviso oficial e imprensa independente confirmam vulnerabilidade, gravidade, exploração ativa e correções

Edição: [[2026-10-30-tech]]
