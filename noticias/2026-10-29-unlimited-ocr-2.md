---
titulo: "Baidu publica o Unlimited-OCR-2, modelo de OCR de 3B para documentos longos sob licença MIT; resultados de ponta são do próprio grupo"
data: 2026-10-29
area: ia
secao: Modelos e lançamentos
veredito: CONFIRMADO
confianca: 83
contestado: false
checagem: dupla
tags: [ia, visao, open-weights, baidu]
---
A organização oficial da Baidu no Hugging Face publicou o Unlimited-OCR-2 em 26/10. Tem cerca de 3,34B parâmetros, licença MIT e código no GitHub oficial da empresa. O método, descrito no paper da primeira versão (arXiv 2606.23050, junho), troca a atenção do decodificador por uma janela deslizante com cache KV constante e usa o codificador do DeepSeek OCR. Segundo o paper, transcreve dezenas de páginas numa passada, dentro de um limite de 32K tokens.

**Por que importa:** OCR aberto e permissivo para documentos longos, útil para quem processa PDFs extensos localmente.

## Evidências
- [Registro na API do Hugging Face](https://huggingface.co/api/models/baidu/Unlimited-OCR-2)
- [Model card](https://huggingface.co/baidu/Unlimited-OCR-2)
- [Paper da V1 (arXiv 2606.23050)](https://arxiv.org/abs/2606.23050)
- [baidu/Unlimited-OCR (GitHub)](https://github.com/baidu/Unlimited-OCR)

## Red flags
- "Estado da arte" em MPDocBench e MarathonDocBench é autodeclarado; os números estão só numa imagem, e o MarathonDocBench é da própria Baidu.
- Não há relatório técnico da V2; as mudanças em relação à V1 não estão documentadas.
- "Unlimited" no nome; o limite declarado é 32K tokens.
- Exige `trust_remote_code`: revise o código antes de rodar.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · Hugging Face, GitHub e arXiv confirmam publicação, data e licença.

Edição: [[2026-10-29-ia]]
