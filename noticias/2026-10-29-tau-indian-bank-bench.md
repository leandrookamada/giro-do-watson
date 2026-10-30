---
titulo: "Benchmark do NPCI mostra que 6,5% a 12% das sessões bancárias 'bem-sucedidas' de agentes pulam etapas obrigatórias"
data: 2026-10-29
area: ia
secao: Pesquisa e arquiteturas
veredito: PROVÁVEL
confianca: 78
contestado: false
checagem: dupla
tags: [ia, agentes, avaliacao, npci]
---
O TauIndianBankBench (arXiv 2610.30161, 30/09), de autor do NPCI (National Payments Corporation of India), tem 1.000 tarefas de varejo bancário com cliente simulado por LLM. Além do estado final das contas, verifica se o agente cumpriu as etapas obrigatórias e não fez alterações não pedidas. Em seis modelos com pesos abertos, de 6,5% a 12% das sessões que contariam como sucesso pelo resultado violam o procedimento; o Qwen3.8-27B cai de 0,920 para 0,849 quando o procedimento entra na conta. Código e dados estão no GitHub e no Hugging Face, com licença não declarada.

**Por que importa:** quem avalia agentes só pelo resultado final pode aprovar um fluxo que descumpre regras de compliance.

## Evidências
- [arXiv 2610.30161](https://arxiv.org/abs/2610.30161)
- [npci/TauIndianBankBench (GitHub)](https://github.com/npci/TauIndianBankBench)
- [Retail Banker International](https://www.retailbankerinternational.com/news/india-npci-hdfc-sovereign-ai-retail-banking-model/)

## Red flags
- Paper de 30/09, só agora no Hugging Face: não é novidade da semana.
- Números do próprio NPCI, que lançou o benchmark junto com um modelo bancário com o HDFC.
- Só modelos open-weight pequenos e médios; sem modelos de fronteira.
- Simulador LLM sem erro medido; dados sintéticos e só em inglês; licença indefinida (NOASSERTION).

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · paper e imprensa confirmam o lançamento do benchmark.

Edição: [[2026-10-29-ia]]
