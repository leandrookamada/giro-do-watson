---
titulo: "Preprint 'Memory Tax' indica que vários sistemas de memória para agentes rendem menos que RAG simples em benchmarks conversacionais"
data: 2026-10-28
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 72
contestado: false
checagem: dupla
tags: [ia, agentes, avaliacao, llm]
---
O preprint "Memory Tax" (arXiv 2610.34073, 25/10), de Tsinghua, UIUC, Renmin, Waterloo e da empresa Verdent.ai, afirma que muitos sistemas de memória dedicados para agentes rendem menos que um RAG ingênuo por chunks. O trabalho decompõe a perda em fidelidade, acessibilidade e robustez da memória. Também mostra casos em que a memória ganha, como tarefas web, e atribui parte do efeito a benchmarks com pouco espaço de melhora.

**Por que importa:** antes de adotar um sistema de memória para agentes, vale compará-lo com um RAG simples no próprio caso de uso.

## Evidências
- [arXiv 2610.34073](https://arxiv.org/abs/2610.34073)
- [Hugging Face Papers](https://huggingface.co/papers/2610.34073)

## Red flags
- Preprint sem revisão por pares; código só prometido ("will open-source"); sem reprodução.
- Um único juiz LLM (Qwen3.6-27B) e um único backbone; subconjuntos amostrados por custo (20% e 10% de dois benchmarks); algumas configurações diferentes das oficiais.
- O foco é memória conversacional, em inglês e offline; "larga escala" é generoso.
- Votos no Hugging Face medem atenção, não validade.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · o preprint declara o resultado e propõe o framework.

Edição: [[2026-10-28-ia]]
