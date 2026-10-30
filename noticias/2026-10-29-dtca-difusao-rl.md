---
titulo: "Preprint propõe DTCA, crédito por token para RL em modelos de linguagem por difusão; ganho cai de 9 para 5 pontos com orçamento maior"
data: 2026-10-29
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 72
contestado: false
checagem: dupla
tags: [ia, rl, treinamento]
---
O preprint DTCA (arXiv 2610.35201, 26/10), de autores da Zhejiang University, NUS e SAP, pontua cada token pelo quanto ele aumenta a confiança nas posições ainda mascaradas e usa isso para escolher passos de denoising e escalar o sinal de RL, com uma calibração por entropia. Os testes são só no LLaDA-8B-Instruct, em MATH500 e GSM8K. O ganho sobre o modelo base é de +9,0 e +5,3 pontos com orçamento de 128 tokens e cai para +4,8 e +2,5 com 512. Contra o melhor baseline de RL (ESPO), a margem no melhor caso é de 2,2 pontos. O código está no GitHub sob Apache-2.0, sem pesos.

**Por que importa:** modelos de linguagem por difusão ainda têm pouca técnica de RL; o método é uma peça a mais, mas testado num único modelo.

## Evidências
- [arXiv 2610.35201](https://arxiv.org/abs/2610.35201)
- [ZJU-OmniAI/DTCA (GitHub)](https://github.com/ZJU-OmniAI/DTCA)

## Red flags
- Preprint sem revisão por pares; números autodeclarados; sem avaliação independente ainda.
- O destaque (+9,0) é contra o modelo base e no menor orçamento.
- Baselines reproduzidos pelos próprios autores; uma resposta por questão, temperatura 0, sem variância.
- GSM8K está perto da saturação.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · ganhos sustentam a alegação, mas sem reprodução nem variância.

Edição: [[2026-10-29-ia]]
