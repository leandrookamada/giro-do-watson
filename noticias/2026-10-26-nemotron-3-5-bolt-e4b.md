---
titulo: "NVIDIA publica Nemotron 3.5 Bolt E4B, fine-tune do Gemma 4 com pesos abertos para assistentes em dispositivo"
data: 2026-10-26
area: ia
secao: Modelos e lançamentos
veredito: CONFIRMADO
confianca: 87
contestado: false
checagem: dupla
tags: [ia, open-weights, llm, eficiencia, nvidia]
---
Em 23/10, a NVIDIA publicou no Hugging Face o `NVIDIA-Nemotron-3.5-Bolt-E4B-BF16`, pós-treinado a partir do Gemma-4-E4B-it para assistentes de voz e de dispositivo, personas interativas e uso na borda. Pelo model card:
- **Tamanho:** 8B de parâmetros totais e 4B efetivos (daí o "E4B").
- **Contexto:** até 64K de entrada e 64K de saída.
- **Licença:** OpenMDW-1.1; o Gemma 4 de base é Apache 2.0.
- **Uso indicado:** o card diz que serve principalmente para customização e pós-treino.

Nos benchmarks da própria NVIDIA (Tau2-Bench 55,1; IHEval 84,8), o modelo não lidera tudo: o Qwen3.5 4B é melhor em Tau2-Bench, BFCL-v3 e RULER. A versão GGUF da unsloth passou de 56 mil downloads em três dias, contra cerca de 3,4 mil do repositório oficial em BF16.

**Por que importa:** é uma opção aberta e pequena (cabe em cerca de 4 GB quantizado) para rodar assistente local. Mas é um ajuste fino do Gemma 4, não um modelo novo do zero.

## Evidências
- [Model card oficial (NVIDIA)](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Bolt-E4B-BF16)
- [Blog técnico da NVIDIA](https://research.nvidia.com/labs/nemotron/NVIDIA-Nemotron-3.5-Bolt-E4B-4GB/)
- [GGUF da unsloth](https://huggingface.co/unsloth/NVIDIA-Nemotron-3.5-Bolt-E4B-GGUF)
- [LetsDataScience: anúncio de 15/10](https://letsdatascience.com/news/nvidia-expands-nemotron-35-with-super-vl-and-bolt-ff81d36b)

## Red flags
- É open weights, não open source: a licença OpenMDW não é a do Gemma, e parte dos dados de treino é fechada ou de acesso controlado.
- Os benchmarks são do harness da própria NVIDIA (NeMo Gym), sem avaliação independente ainda.
- Downloads de um repositório de terceiros medem curiosidade e espelhamento, não adoção em produção.
- O suporte oficial de execução é só Linux com GPU NVIDIA; a receita para llama.cpp ainda estava pendente.

Edição: [[2026-10-26-ia]]
