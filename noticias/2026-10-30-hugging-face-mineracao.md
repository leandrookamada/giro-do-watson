---
titulo: "Segunda onda de repositórios maliciosos no Hugging Face minera cripto ao carregar modelos com trust_remote_code"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 80
contestado: false
checagem: dupla
tags: [tech, malware, seguranca-de-ia, open-source, hugging-face]
---
A Pluto Security documentou a campanha "Load/Mine": 31 repositórios maliciosos em 7 contas do Hugging Face, em duas ondas; a segunda (19 repositórios) apareceu dias depois da remoção da primeira. O código roda ao carregar o modelo com `trust_remote_code=True` e instala o minerador peakminer, mirando hosts de GPU com Xinference e GPUStack. A primeira onda plantou chave SSH e a segunda usou reverse shells. O modelo qwen2-tiny teve cerca de 28 mil downloads.

**Por que importa:** quem carrega modelos de terceiros com `trust_remote_code=True` executa código arbitrário; servidores de inferência com GPU são alvo de mineração e acesso persistente.

## Evidências
- [Pluto Security: campanha Load/Mine no Hugging Face](https://pluto.security/blog/hugging-face-malware-campaign-load-mine/)
- [BleepingComputer: campanha volta a sequestrar GPUs](https://www.bleepingcomputer.com/news/security/hugging-face-malware-campaign-returns-to-hijack-gpus-for-crypto-mining/)

## Red flags
- Downloads não são infecções; a evidência concreta de impacto é de poucas máquinas, e a carteira da primeira onda recebeu cerca de US$ 5 mil.
- Fonte primária única, de empresa de segurança com interesse comercial; a imprensa repete o relatório, com confirmação própria do payload.
- A manchete omite o pré-requisito `trust_remote_code=True`; atribuição a operador chinês é inferência.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · relatório da Pluto e cobertura da BleepingComputer confirmam a campanha via trust_remote_code

Edição: [[2026-10-30-tech]]
