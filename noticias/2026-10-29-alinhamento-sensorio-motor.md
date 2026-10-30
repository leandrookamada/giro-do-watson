---
titulo: "Preprint propõe métrica offline S² que se correlaciona com o sucesso de políticas robóticas em amostras de 5 a 12 modelos"
data: 2026-10-29
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 67
contestado: false
checagem: dupla
tags: [ia, robotica, avaliacao]
---
O preprint "Sensorimotor Alignment" (arXiv 2610.31670), de pesquisadores da Rice University e da NVIDIA, propõe a métrica S², que mede quanto as representações de imagem e texto de um modelo se alinham com a geometria das trajetórias do robô, sem treino nem teste em malha fechada. Os autores reportam correlação de r=0,717 em 12 modelos VLA, 0,681 em 8 VLMs, 0,718 em 6 world-action models (p=0,054) e 0,831 em 5 políticas num robô real. O código está no GitHub, sem licença declarada.

**Por que importa:** avaliar robôs em malha fechada é caro; uma métrica offline barata ajudaria a triar modelos, se a correlação se sustentar.

## Evidências
- [arXiv 2610.31670](https://arxiv.org/abs/2610.31670)
- [Página do projeto](https://yunfeixie233.github.io/s2/)
- [yunfeixie233/sensorimotor-alignment (GitHub)](https://github.com/yunfeixie233/sensorimotor-alignment)

## Red flags
- Correlação com amostras muito pequenas; um dos resultados não é significativo a 5%; p-values unilaterais.
- Os próprios autores dizem que a relação é correlacional e não substitui a avaliação em malha fechada.
- O rótulo "Platonic" vende mais do que a métrica entrega.
- Preprint sem revisão; sem reprodução independente.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · correlações apresentadas, sem reprodução independente.

Edição: [[2026-10-29-ia]]
