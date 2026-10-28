---
titulo: "CISA põe no KEV o PolyShell do Magento (CVE-2026-48356), corrigido em julho e explorado desde março; elo com o Brotli não tem base"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 60
contestado: true
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, web, adobe-commerce]
---
A CISA adicionou a CVE-2026-48356 (Adobe Commerce e Magento, upload irrestrito de arquivo perigoso) ao KEV em 27/10, com prazo em 10/11. A falha foi corrigida pela Adobe em 14/07/2026 (APSB26-73). Segundo a Sansec, é a falha usada nos ataques PolyShell, divulgados em 17/03 e explorados em massa desde 19/03, com 471 lojas atingidas em uma hora. A Sansec acompanha um operador com loader em 953 lojas desde julho de 2025, mas por vetores mistos (PolyShell e SessionReaper), e diz que as reescritas de outubro não usaram falha nova.

**Por que importa:** lojas Magento/Adobe Commerce sem o APSB26-73 seguem expostas. Atualizar não remove um webshell já enviado, então quem ficou sem patch desde março precisa procurar arquivos estranhos na pasta de upload e bloquear execução nela.

## Evidências
- [CISA KEV (JSON)](https://raw.githubusercontent.com/cisagov/kev-data/develop/known_exploited_vulnerabilities.json)
- [Registro CVE (CNA Adobe)](https://raw.githubusercontent.com/CVEProject/cvelistV5/main/cves/2026/48xxx/CVE-2026-48356.json)
- [Sansec: 953 lojas e o loader deepveindrilling](https://sansec.io/research/magento-cms-block-loader-deepveindrilling)
- [Sansec: onda de ataques PolyShell](https://sansec.io/research/polyshell-mass-attack-wave)
- [heise](https://heise.de/news/Angreifer-nehmen-Brotli-Adobe-Commerce-und-Magento-Lecks-ins-Visier-11502623.html)

## Red flags
- A manchete do The Hacker News trata como surto atual uma falha explorada desde março e corrigida em julho; o KEV chega com meses de atraso.
- "Centenas de lojas" é um acumulado de 15 meses, com mais de um vetor; não são todas invasões por esta CVE.
- O vínculo com tráfego do Brotli não aparece em nenhuma fonte técnica (Sansec e heise tratam os temas como separados).
- O registro CVE da Adobe exige interação do usuário (UI:R), enquanto a Sansec descreve upload não autenticado; o mapeamento PolyShell ↔ CVE é da Sansec.
**Contestado:** Watson deu CONFIRMADO (KEV e vínculo PolyShell ↔ CVE pela Sansec); Mycroft deu EXAGERADO pelo enquadramento de ataque novo e pelo elo inexistente com o Brotli.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · KEV e ataques às lojas confirmados, mas nada comprova tráfego do Brotli nesses ataques.

Edição: [[2026-10-28-tech]]
