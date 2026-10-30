---
titulo: "Preprint propõe OmniShowcase, LoRA sobre o Wan2.1 para vídeo com sujeito consistente a partir de várias fotos; código e dados ainda não saíram"
data: 2026-10-29
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 60
contestado: false
checagem: dupla
tags: [ia, multimodal, visao]
---
O OmniShowcase (arXiv 2610.35684, 26/10), de KAIST, FLIPTION e Inha University, gera vídeos com órbitas de câmera de até 360 graus em torno de um objeto a partir de quatro fotos de referência. Usa vídeos de treino sintéticos renderizados de ativos 3D e condicionamento por mapas de normais de superfície. É uma LoRA sobre o Wan2.1 I2V-14B. Os autores declaram estado da arte em identidade do sujeito e consistência 3D no benchmark próprio (50 sujeitos) e no NAVI (35).

**Por que importa:** vídeo de produto girando a partir de poucas fotos tem uso comercial direto, mas ainda não dá para testar.

## Evidências
- [arXiv 2610.35684](https://arxiv.org/abs/2610.35684)
- [Página do projeto](http://justin4ai.github.io/OmniShowcase)
- [justin4ai/OmniShowcase (GitHub)](https://github.com/justin4ai/OmniShowcase)

## Red flags
- Código, dados e benchmark são só promessa: o repositório tem todos os itens de release pendentes e não tem licença.
- Benchmark principal criado pelos autores; baselines adaptados por eles.
- Falha com sujeitos não rígidos; treino só com dados sintéticos.
- Estudo com usuários pequeno (44 pessoas, 24 vídeos).

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · paper descreve o método, sem evidência independente.

Edição: [[2026-10-29-ia]]
