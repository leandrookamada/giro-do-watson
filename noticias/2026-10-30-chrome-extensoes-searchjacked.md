---
titulo: "Socket reporta 319 extensões do Chrome que redirecionam buscas, com 13,4 milhões de instalações listadas; a maioria já foi removida"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 60
contestado: false
checagem: dupla
tags: [tech, malware, privacidade, web, chrome]
---
Segundo o BleepingComputer, um relatório da Socket (John Tuckner) descreve 319 extensões do Chrome, 57 de abril de 2025 e 264 novas, somando cerca de 13,4 milhões de instalações listadas. As buscas dos usuários passam por proxies dos operadores antes de chegar ao Bing ou Yahoo, para gerar receita de afiliados. A maioria das extensões já foi removida e o Google não respondeu.

**Por que importa:** extensões de aparência inofensiva monetizam o tráfego de busca e dão ao operador visibilidade sobre o que o usuário pesquisa; vale auditar extensões instaladas.

## Evidências
- [BleepingComputer: extensões do Chrome com 13,4 milhões de instalações sequestram buscas](https://www.bleepingcomputer.com/news/security/chrome-extensions-with-134-million-installs-caught-hijacking-searches/)
- [Socket: relatório searchjacked (citado pela matéria, não verificado)](https://socket.dev/blog/searchjacked)

## Red flags
- Fonte única: só o BleepingComputer, que repete o relatório da Socket; o relatório devolveu 403 e nenhuma outra fonte foi achada.
- 13,4 milhões são contadores de instalação da loja (não usuários únicos), manipuláveis e talvez com sobreposição; é um teto histórico, pois a maioria já saiu do ar.
- Um verificador achou que a aritmética não fecha (57 + 264 = 321 extensões; ~14,7 mi); o outro viu as contas internas batendo.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · baseada no relatório da Socket via BleepingComputer, sem fontes independentes para os números

Edição: [[2026-10-30-tech]]
