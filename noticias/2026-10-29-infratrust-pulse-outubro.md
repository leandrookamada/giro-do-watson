---
titulo: "InfraTrust Pulse de outubro conta 133 avisos de 18 fabricantes de rede, 16 com falhas do KEV, e alerta para o PHP2Shell embutido em firmware"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 79
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, infratrust]
---
O InfraTrust Pulse de outubro, publicado em 28/10 por Paul Asadoorian e Chase Snyder, cobre de 18/09 a 14/10. Registra 133 novos avisos de segurança de 18 fabricantes de equipamentos de rede, com 2.813 CVEs, 37 críticos, 5 com CVSS 10, 58 exploráveis sem autenticação e 16 com falhas do KEV. Dez avisos corrigem falhas já exploradas, de Citrix NetScaler, Ivanti, Check Point, Cisco SD-WAN, F5 e outros. O relatório alerta que o PHP2Shell, embutido em firmware de appliances, depende de patch de cada fabricante.

**Por que importa:** dá a dimensão do volume de patches em borda de rede e lista quais avisos corrigem falhas já exploradas.

## Evidências
- [InfraTrust Pulse, outubro de 2026](https://pulse.infra-trust.org/october-2026/)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/infratrust-report-warns-of-exploited-flaws-in-critical-network-infrastructure/)
- [CISO Advisor](https://www.cisoadvisor.com.br/relatorio-mapeia-falhas-exploradas-em-infraestrutura-de-rede/)

## Red flags
- Os 2.813 CVEs são contados por aviso; a mesma CVE aparece em vários avisos.
- Recorte de 18 fabricantes sem metodologia detalhada.
- Relatório de fornecedor de segurança (o BleepingComputer o atribui à Eclypsium, o que a página não confirma).
- Até o fechamento, os fabricantes não conheciam exploração do PHP2Shell em seus produtos; a manchete fala em exploração de forma ampla.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · relatório traz os números e fontes independentes corroboram.

Edição: [[2026-10-29-tech]]
