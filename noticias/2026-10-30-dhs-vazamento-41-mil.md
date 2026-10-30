---
titulo: "Site de vazamento publica diretório com cerca de 41 mil funcionários e contratados do DHS; autenticidade só parcialmente verificada"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 74
contestado: false
checagem: dupla
tags: [tech, vazamento, privacidade, dhs]
---
Em 28/10 a DDoSecrets publicou registros de mais de 41 mil funcionários e contratados do DHS (166,7 MB). A origem declarada é um serviço de SSO Okta usado pelo DHS, obtido pelo grupo hacktivista "Department of Peace"; a Okta diz não ter evidência de comprometimento dos próprios sistemas. Os dados trazem rótulos de grupo como "Undercover Operations" e "Covert Operations". A autenticidade foi checada por amostra (a Reuters casou 6 pessoas com outras bases; a CyberScoop confirmou funcionários atuais da CISA). Não há resposta oficial do DHS.

**Por que importa:** expõe dados de pessoal de segurança interna dos EUA, com risco de doxxing e engenharia social, inclusive de quem atua em operações sensíveis.

## Evidências
- [DDoSecrets: dataset Icepick](https://ddosecrets.org/article/icepick)
- [CyberScoop: vazamento de dados de funcionários do DHS](https://cyberscoop.com/dhs-employee-data-leak-ddosecrets/)
- [GV Wire (Reuters): site de vazamento publica dados de dezenas de milhares de funcionários do DHS](https://gvwire.com/2026/10/28/leak-website-releases-data-on-tens-of-thousands-of-dhs-employees/)

## Red flags
- A manchete "agentes à paisana do ICE" vai além dos dados: são rótulos de grupo de usuários, sem prova de que cada pessoa seja agente infiltrado; a alegação de fotos faciais vem de um único veículo.
- Só 6.598 das cerca de 41 mil entradas são do ICE; a maioria é da CBP (21.329).
- Conjunto não verificado por inteiro; origem por hacktivistas com motivação política; a contagem varia entre veículos (40 a 42 mil).
- O artigo da Ars Technica não foi localizado; a matéria do CISO Advisor reescreve a da Wired.
- Dados pessoais de agentes: esta nota não reproduz nomes.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · DDoSecrets divulgou cerca de 41 mil registros e fontes independentes verificam parte, mas autenticidade completa e origem não foram corroboradas

Edição: [[2026-10-30-tech]]
