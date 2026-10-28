---
titulo: "Estudo de escala até 919M parâmetros indica quando truncar o backprop compensa em transformers em loop"
data: 2026-10-28
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 70
contestado: false
checagem: dupla
tags: [ia, arquitetura, treinamento, eficiencia]
---
O preprint "Truncate or Not?" (arXiv 2610.26030, 21/10) roda 592 treinos de transformers em loop, de 58M a 919M parâmetros, com 100B tokens do FineWeb-Edu, e ajusta uma lei de escala. Quando o número de loops na ida e na volta é livre, a lei favorece o backprop completo (BPTT): 4 loops completos vencem 8 com 2 de volta, com o mesmo compute. Com o número de loops fixo, truncar pode ser ótimo, com cerca de 34% de economia de compute em 8 loops. Com tamanho de modelo livre, a lei favorece não usar loop; 2 loops empatam com cerca de 27% menos parâmetros e 8% mais compute.

**Por que importa:** dá uma regra prática para quem treina modelos com computação recorrente; o ganho é modesto e medido só em perda de validação.

## Evidências
- [Hugging Face Papers / arXiv 2610.26030](https://huggingface.co/papers/2610.26030)

## Red flags
- "BPTT completo supera truncado" só vale com os loops otimizados em conjunto; o próprio título do paper indica a nuance.
- Escala pequena (até 919M), só modelos densos e só perda de validação, sem tarefas reais. A extrapolação para escalas maiores é da lei ajustada.
- Preprint sem código nem reprodução.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · o preprint mostra o resultado no regime de loops livres e descreve os dois regimes.

Edição: [[2026-10-28-ia]]
