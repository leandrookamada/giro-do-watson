---
titulo: "NVIDIA libera pesos do Nemotron 3.5 Transcribe, modelo de transcrição guiado por prompt, e o manifesto de dados Granary v2"
data: 2026-10-29
area: ia
secao: Modelos e lançamentos
veredito: PROVÁVEL
confianca: 79
contestado: false
checagem: dupla
tags: [ia, audio, open-weights, nvidia]
---
A NVIDIA publicou em 28/10 o Nemotron 3.5 Transcribe (checkpoint NVIDIA-Nemotron-3.5-Transcribe-30B-A4B) e o Granary v2. O modelo aceita instruções em linguagem natural para transcrever, diarizar, traduzir, responder perguntas sobre o áudio e gerar timestamps por palavra. Transcreve 40 idiomas, traduz 31 e faz diarização em 13, com gravações de até 1 hora e 8 falantes, só offline. O model card dá licença OpenMDW-1.1 (open weights) e cerca de 34B parâmetros totais, 4,3B ativos. O Granary v2 é um manifesto de 463.062 horas em 48 idiomas; o áudio é baixado à parte, sob a licença de cada corpus.

**Por que importa:** é um modelo de fala com pesos abertos e uso comercial permitido que pode ser ajustado por prompt ou fine-tuning para domínios como saúde.

## Evidências
- [Post da NVIDIA no blog do Hugging Face](https://huggingface.co/blog/nvidia/nemotron-transcribe-granary)
- [Model card](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B)

## Red flags
- Benchmarks reportados pela NVIDIA e parceiros (WER 5,33% no Open ASR inglês, 1º empatado no AA-WER); sem avaliação independente ainda.
- Blog e model card divergem no tamanho (30B/4B contra 34B/4,3B ativos).
- O throughput de "100 h de áudio em menos de 3 min" usa a versão NVFP4, ainda "em breve".
- Licença só aparece no model card, não no post.
- Nenhuma corroboração independente do lançamento.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · blog e model card sustentam as capacidades, mas falta avaliação independente.

Edição: [[2026-10-29-ia]]
