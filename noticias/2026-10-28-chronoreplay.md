---
titulo: "ChronoReplay propõe treino espacial em ordem cronológica para VLMs e reporta ganhos autodeclarados em 3 benchmarks; efeito da ordem em si é de ~2 pontos"
data: 2026-10-28
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 66
contestado: false
checagem: dupla
tags: [ia, visao, multimodal, treinamento]
---
O preprint ChronoReplay (arXiv 2610.34283, 27/10) chama de "interface lock-in" o fato de que pós-treinar um VLM espacial num tipo de resposta melhora esse tipo e piora outros. A proposta é reproduzir supervisão espacial mista em episódios cronológicos, com o formato de resposta nativo de cada tarefa. Sobre o Qwen3-VL-8B, os autores reportam OVO-S-Bench de 48,98 para 53,89, OST-Bench de 50,52 para 63,93 e UCS-Bench de 45,33 para 52,77. O código está em github.com/yihaohu0118/ChronoReplay, sem licença declarada.

**Por que importa:** mostra que a forma de misturar os dados de treino muda o que um modelo de visão aprende sobre espaço, mas o ganho da ordem cronológica em si é pequeno.

## Evidências
- [Hugging Face Papers / arXiv 2610.34283](https://huggingface.co/papers/2610.34283)
- [Repositório no GitHub](https://github.com/yihaohu0118/ChronoReplay)

## Red flags
- Todos os números são autodeclarados, em 3 benchmarks de nicho, com um só modelo base; sem avaliação independente ainda.
- O treino só categórico chega a 58,03 no OVO-S, acima do ChronoReplay; o método só é o melhor na média.
- O efeito isolado da ordem cronológica é de cerca de 2,41 pontos no OST, com duas sementes. Os próprios autores dizem que as comparações não isolam a causa.
- Só cenas internas; repositório sem licença, o que limita o uso legal.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · método e ganhos confirmados no preprint, sem validação independente.

Edição: [[2026-10-28-ia]]
