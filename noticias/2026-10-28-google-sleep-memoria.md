---
titulo: "Google Research divulga em blog o 'Sleep', método de consolidação de memória para LLMs descrito em preprint de junho, sem código"
data: 2026-10-28
area: ia
secao: Pesquisa e arquiteturas
veredito: EXAGERADO
confianca: 75
contestado: false
checagem: dupla
tags: [ia, llm, treinamento, rl, google-research]
---
O blog do Google Research de 27/10, de Ali Behrouz e Vahab Mirrokni, descreve um aprendizado contínuo que alterna uma fase ativa ("wake") e uma offline ("sleep"). No "sono", o modelo consolida o contexto de curto prazo nos parâmetros (Knowledge Seeding) e treina em currículos sintéticos gerados por RL ("dreaming"). O trabalho é o preprint "Language Models Need Sleep" (arXiv 2606.03979), com v1 em 02/06 e v2 em 10/07/2026, sem revisão por pares e sem código. O blog cita AIME24 79,2, AIME25 69,0, HMMT25 46,1 e retenção quase sem queda no BABILong até 10M tokens.

**Por que importa:** é uma linha de pesquisa sobre como LLMs podem aprender continuamente sem esquecer, mas ainda não dá para avaliar o alcance dos resultados.

## Evidências
- [Google Research: blog](https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/)
- [arXiv 2606.03979](https://arxiv.org/abs/2606.03979)

## Red flags
- "Nova forma" é de um paper de junho, com versão no OpenReview desde set/2025.
- O blog não nomeia o modelo base nem dá números das baselines, o que torna os resultados difíceis de interpretar. A comparação com GPT-4 usa um modelo antigo.
- Segundo agregadores, no AIME-25 uma variante "Semantic Reward" fica um pouco acima (69,2), o que o blog omite.
- Sem código, sem reprodução e sem discussão de limitações ou do custo da fase de sono. O PDF não foi lido; os números vêm do blog.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · blog e preprint confirmam o framework, sem fonte independente sobre a novidade.

Edição: [[2026-10-28-ia]]
