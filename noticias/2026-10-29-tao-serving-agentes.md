---
titulo: "Preprint propõe TAO, escalonador de agentes LLM que considera a prontidão das ferramentas; ganho de até 27% na latência, com perdas sob carga alta"
data: 2026-10-29
area: ia
secao: Ferramentas e infraestrutura
veredito: PROVÁVEL
confianca: 63
contestado: false
checagem: dupla
tags: [ia, agentes, eficiencia]
---
O TAO (arXiv 2610.37230, 27/10) escalona sessões de agentes LLM entre nós de GPU pontuando a prontidão das ferramentas, o aproveitamento do cache KV e o consumo de tokens, e decide a alocação por programação dinâmica. Em 12 configurações com DeepSeek-V4 Flash, Qwen3-32B e GLM-4.7 em H100, os autores reportam redução de latência de até 26,8%, de TTFT de até 36,3% e ganho de throughput de até 29,5%, sempre contra o melhor baseline daquela métrica (vLLM, Dynamo, ThunderAgent). Não há código publicado.

**Por que importa:** serving de agentes passa muito tempo esperando ferramentas; escalonar levando isso em conta pode cortar custo de infraestrutura.

## Evidências
- [arXiv 2610.37230](https://arxiv.org/abs/2610.37230)
- [Hugging Face Papers](https://huggingface.co/papers/2610.37230)

## Red flags
- "Até 26,8%" é o melhor caso, não a média.
- Em algumas configurações o TAO perde: com 128 workers no AutomationBench o TTFT médio vai a 19,1 s contra 3,2 s do Dynamo.
- O programa dinâmico superou uma heurística simples em poucos snapshots (17% a 26%).
- Sem código; preprint sem revisão; sem avaliação independente.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · resultados do paper sustentam a melhoria, sem código nem corroboração.

Edição: [[2026-10-29-ia]]
