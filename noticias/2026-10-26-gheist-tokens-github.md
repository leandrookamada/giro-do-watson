---
titulo: "Campanha Gheist usa tokens roubados do GitHub para imprimir segredos do Actions; trava do GitHub barrou os repositórios públicos"
data: 2026-10-26
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 84
contestado: false
checagem: dupla
tags: [tech, vazamento, cloud, github, wiz]
---
Desde 15/09, a campanha automatizada "Gheist" usa tokens do GitHub roubados (provavelmente de logs de infostealers e de comprometimentos anteriores, como o do Trivy em março) para criar branches `ci-sync-xxxxxx` com o workflow `sync-check.yml`. O workflow imprime os segredos do repositório nos logs do Actions em base32, driblando o mascaramento. A ferramenta baixa o log pela API (user agent `gheist`) e apaga o run segundos depois. Segundo a Wiz, até 24/10 foram mais de 13.500 branches plantadas a partir de mais de 850 contas. Em repositórios públicos, a trava de aprovação do GitHub (em vigor desde 28/07) impediu a execução dos payloads; em repositórios privados e no GitHub Enterprise Server, os runs completaram. Num caso corporativo, credenciais de nuvem obtidas assim foram usadas para enumerar o AWS Secrets Manager.

**Por que importa:** quem tem repositório privado com segredos no Actions deve procurar branches `ci-sync-*`, runs apagados em menos de 1 minuto e o user agent `gheist`. Apagar a branch não desfaz a exposição: é preciso rotacionar todos os segredos acessíveis, revogar o token usado e checar infostealer na máquina do dono. Runners self-hosted que rodaram uma branch `ci-sync` devem ser tratados como comprometidos.

## Evidências
- [Wiz Research: relatório original com IoCs](https://www.wiz.io/blog/gheist-attempted-scaled-abuse-of-stolen-github-tokens-stumbles)
- [GitHub changelog: trava de workflows suspeitos (28/07)](https://github.blog/changelog/2026-07-28-github-actions-holds-potentially-malicious-workflows-for-approval/)

## Red flags
- "Milhares de repositórios" (cobertura da imprensa): a fonte primária fala em branches plantadas e contas usadas, não em repositórios com segredos roubados com sucesso. A Wiz não quantifica segredos exfiltrados.
- O título original da Wiz diz que a campanha "tropeçou" ("stumbles"): manchetes de sucesso em massa invertem o sentido.
- Fonte primária única (Wiz, que vende segurança de nuvem), sem corroboração independente nem posição do GitHub sobre a Gheist; o relatório, porém, é técnico e com IoCs verificáveis.
- A origem dos tokens é "compatível com" infostealers e incidentes anteriores, não confirmada.

Edição: [[2026-10-26-tech]]
