---
titulo: "PHP reconstrói os pacotes oficiais para Windows com Brotli 1.2.1 contra a CVE-2026-111497"
data: 2026-10-26
area: tech
secao: Cybersecurity
veredito: CONFIRMADO
confianca: 88
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, web, php, brotli]
---
Em 26/10, o php.net publicou os builds para Windows 8.5.12-1, 8.4.27-1, 8.3.36-1 e 8.2.35-1, que trazem o Brotli 1.2.1 e corrigem a CVE-2026-111497. O código-fonte e a versão do PHP não mudam: o sufixo "-1" marca só a reconstrução do pacote com dependências atualizadas. Segundo o PHP, o decodificador vulnerável só é alcançado pela extensão cURL quando a descompressão automática de respostas HTTP está ligada, o que vem desligado por padrão mas pode ser ativado por aplicações e bibliotecas cliente HTTP. A extensão PECL brotli é outra coisa e não foi citada.

**Por que importa:** quem roda PHP no Windows com builds oficiais deve trocar pelos pacotes "-1", principalmente se usa cURL com descompressão automática. No Linux e em outros sistemas, o que conta é a libbrotli da distribuição.

## Evidências
- [php.net: anúncio dos builds Windows](https://www.php.net/)
- [Brotli v1.2.1 (upstream)](https://github.com/google/brotli/releases/tag/v1.2.1)
- [Microsoft: atualizações .NET fora de ciclo (25/10)](https://devblogs.microsoft.com/dotnet/dotnet-october-2026-oob-security-updates/)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/critical-http2shell-brotli-vulnerability-triggers-emergency-patches/)

## Red flags
- "Falha crítica no PHP para Windows" exagera o alcance: o risco depende de cURL com descompressão automática ativada.
- "Segunda atualização de segurança em cinco dias" é contagem do The Hacker News; o php.net não usa essa frase. A primeira atualização (21/10) foi o PHP2Shell, que é outra falha.
- Não confundir HTTP2Shell (Brotli) com PHP2Shell: são vulnerabilidades independentes com nomes parecidos.
- Há PoCs públicos, mas nenhuma exploração em campo reportada até 26/10. Ver o dossiê para o que está provado.

Dossiê: [[2026-10-26-cve-2026-111497]]

Edição: [[2026-10-26-tech]]
