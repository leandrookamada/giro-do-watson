---
titulo: "CISA põe no KEV o Fragnesia (CVE-2026-46300), escalação local para root no kernel Linux divulgada em maio com PoC público; prazo federal é 31/10"
data: 2026-10-29
area: tech
secao: Cybersecurity
veredito: CONFIRMADO
confianca: 83
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, linux, cisa]
---
A CISA incluiu a CVE-2026-46300, conhecida como Fragnesia, no catálogo KEV em 28/10, com prazo de 31/10 e triagem forense exigida. A falha está no caminho ESP-in-TCP do kernel: um flag não é propagado ao juntar fragmentos de pacote, e o ESP pode decifrar sobre páginas do page cache, alterando arquivos somente leitura. O resultado é escalação local de privilégio até root (CVSS 7.8), com exploit público desde maio. A nota do KEV diz que ela pode ser encadeada com as falhas PHP2Shell para instalar webshells e rodar comandos como root. A CISA não diz quem explora.

**Por que importa:** servidores Linux com PHP exposto ganham um caminho de webshell a root; a correção está nas séries estáveis 5.10.257, 5.15.208, 6.1.174, 6.6.141, 6.12.91, 6.18.33, 7.0.10 e no 7.1.

## Evidências
- [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search_api_fulltext=CVE-2026-46300)
- [Alerta da CISA de 28/10](https://www.cisa.gov/news-events/alerts/2026/10/28/cisa-adds-two-known-exploited-vulnerabilities-catalog)
- [Registro CVE](https://raw.githubusercontent.com/CVEProject/cvelistV5/main/cves/2026/46xxx/CVE-2026-46300.json)
- [Rapid7: módulo Metasploit](https://www.rapid7.com/db/modules/exploit/linux/local/cve_2026_46300_fragnesia/)

## Red flags
- O nome no KEV ("variável não inicializada... modificação não intencional de dados") esconde que é escalação para root.
- Não é falha nova: divulgada em 13/05 com PoC; o que mudou é a confirmação de exploração.
- Exige acesso local; quem explora e em que escala não foi divulgado.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · inclusão no KEV e descrição batem com o registro CVE.

Edição: [[2026-10-29-tech]]
