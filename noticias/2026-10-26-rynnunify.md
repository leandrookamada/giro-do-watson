---
titulo: "Alibaba DAMO apresenta RynnUnify, cérebro embodied de 8B+8B que une raciocínio, vídeo e controle de robô, com código e pesos"
data: 2026-10-26
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 79
contestado: false
checagem: dupla
tags: [ia, robotica, arquitetura, multimodal, alibaba]
---
O preprint "RynnUnify: Towards Unified Embodied Brain" (arXiv 2610.32965, 23/10) é do DAMO Academy, da Alibaba.
- **Arquitetura:** um raciocinador autorregressivo de 8B e um gerador de vídeo por difusão de 8B, que planejam intercalando linguagem e vídeo, mais duas extensões. Uma é agêntica, treinada com RL (BCPO); a outra é "world-action", para controle de robô.
- **Resultados autodeclarados:**
  - a maior média de compreensão embodied entre os modelos unificados que os próprios autores avaliaram;
  - +9,75 pontos sobre o Cosmos 3 Nano em planejamento visual;
  - 51,5% de sucesso em 20 tarefas simuladas do RoboCasa365;
  - 46,7% em 3 tarefas com robô real.
- **Liberado:** código (Apache-2.0) e três checkpoints.

**Por que importa:** é uma arquitetura aberta que tenta unir entender, imaginar (gerar vídeo) e agir num só sistema, a linha dos "modelos de mundo" para robótica. Como código e pesos estão liberados, outros grupos podem testar.

## Evidências
- [arXiv 2610.32965](https://arxiv.org/abs/2610.32965)
- [Hugging Face Papers (33 votos)](https://huggingface.co/papers/2610.32965)
- [Código (GitHub)](https://github.com/alibaba-damo-academy/RynnUnify)
- [Página do projeto](https://alibaba-damo-academy.github.io/RynnUnify.github.io/)

## Red flags
- "Estado da arte" vale só entre os modelos unificados que os autores escolheram avaliar.
- Os dois benchmarks principais (Rynn-VP e Rynn-GEU) foram criados pelos próprios autores.
- Pouca amostra no robô real: 3 tarefas, sem baselines nem variância no resumo.
- "16B" é a soma de dois modelos de 8B, e o controle de robô vem de uma extensão com checkpoint próprio.
- É um preprint, sem revisão por pares nem reprodução independente. Os votos no Hugging Face medem atenção.

Edição: [[2026-10-26-ia]]
