---
titulo: "Preprint apresenta Falcon, extração audiovisual de locutor-alvo que iguala a qualidade do baseline com cerca de 20 vezes menos computação"
data: 2026-10-29
area: ia
secao: Pesquisa e arquiteturas
veredito: EXAGERADO
confianca: 69
contestado: false
checagem: dupla
tags: [ia, audio, eficiencia]
---
O Falcon (arXiv 2610.32749, 23/10), de Tsinghua, Qinghai University e Chinese Institute for Brain Research, é um modelo causal leve que usa vídeo do rosto para isolar a voz de um locutor em tempo real. Segundo os autores, tem 0,5M parâmetros contra 6,2M do AV-TFGridNet causal, 20,2 vezes menos computação e 11,1 vezes menos latência em GPU. Na qualidade, fica em paridade: 7,7 dB de SI-SNRi contra 7,6 dB. Código e pesos estão sob Apache-2.0.

**Por que importa:** extração de voz eficiente abre caminho para aparelhos auditivos e chamadas em dispositivos modestos; o ganho real é de eficiência, não de qualidade.

## Evidências
- [arXiv 2610.32749](https://arxiv.org/abs/2610.32749)
- [Página do projeto](https://cslikai.cn/Falcon/)
- [JusperLee/Falcon (GitHub)](https://github.com/JusperLee/Falcon)
- [Pesos no Hugging Face](https://huggingface.co/JusperLee/Falcon)

## Red flags
- "Alta qualidade" e "cenas acústicas reais" vão além do que o paper mostra: a qualidade é de paridade, e o conjunto real tem só cerca de 84 minutos, 10 participantes e métricas não intrusivas.
- Benchmark RealSSA criado pelos próprios autores; baselines avaliados por eles.
- Em CPU a latência é de 1.361 ms por clipe de 2 s.
- O checkpoint de 47 MB não bate com 0,5M parâmetros; não esclarecido.
- Preprint sem revisão; sem reprodução independente.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · eficiência demonstrada, avaliação em cenas reais limitada.

Edição: [[2026-10-29-ia]]
