---
titulo: "Trajectory2Gym (Ant International) treina agentes de ferramentas com interações sintéticas em vez de só trajetórias bem-sucedidas"
data: 2026-10-27
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 73
contestado: false
checagem: dupla
tags: [ia, agentes, treinamento, ant-international]
---
O preprint "Trajectory2Gym" (arXiv 2610.33568, 24/10, oito autores ligados à Ant International) defende que uma trajetória bem-sucedida não é necessariamente boa supervisão para agentes que usam ferramentas. Em vez de coletar trajetórias, o método sintetiza interações executáveis em torno de estruturas multi-etapa pouco cobertas e supervisiona só decisões ancoradas no que o agente via. Em modelos Qwen3 de 1,7B a 30B-A3B, os autores reportam ganhos de +16,9 a +29,8 pontos na média de Tau1, Tau2 e BFCL; o modelo de 8B supera checkpoints públicos de outros grupos que eles reavaliaram. O código foi liberado (Apache-2.0); pesos e dados não foram verificados.

**Por que importa:** é uma receita concreta, com código, para melhorar agentes pequenos de uso de ferramentas sem depender de coletar trajetórias de modelos grandes.

## Evidências
- [arXiv 2610.33568](https://arxiv.org/abs/2610.33568)
- [Hugging Face Papers (324 votos)](https://huggingface.co/papers/2610.33568)
- [Código (GitHub)](https://github.com/yihaohu0118/Trajectory2Gym)

## Red flags
- O baseline principal é o próprio Qwen3 sem ajuste para agentes, fácil de vencer. Os checkpoints de terceiros foram reavaliados pelos autores, e eles mesmos dizem que a comparação não é de computação equivalente.
- A ablação mostra que a seleção estrutural, a ideia central, soma só cerca de 2,3 pontos: boa parte do ganho vem do ajuste fino com dados sintéticos em geral.
- Possível sobreposição entre domínios de treino e de teste (Retail e Airline). Um dos cenários é "seen-task" pela própria definição dos autores.
- Preprint sem revisão por pares nem reprodução externa. Os votos medem atenção.

Edição: [[2026-10-27-ia]]
