---
titulo: "CISA põe as falhas do PHP2Shell no KEV com prazo de 29/10; exploração existe, sucesso em massa não está confirmado"
data: 2026-10-27
area: tech
secao: Cybersecurity
veredito: CONFIRMADO
confianca: 91
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, php]
---
Em 26/10, a CISA adicionou ao catálogo KEV as CVE-2026-109618 ("PHP Memory Corruption") e CVE-2026-109619 ("PHP Stale Internal Request-State"). As duas são descritas como execução remota de código sem autenticação, com prazo de correção para as agências federais americanas em 29/10. O KEV é a evidência formal de exploração ativa, mas a CISA não divulgou detalhes:
- **Vítima nomeada:** nenhuma, e o uso por ransomware está marcado como "Unknown".
- **Tentativas:** Amazon, Cloudflare, Patchstack e outros registraram tentativas desde quatro dias antes do patch, classificadas como malsucedidas.
- **RCE confirmado:** o único público continua sendo em honeypot (mod_php, PHP 8.4.26).
- **Exploit:** a VulnCheck relata um exploit funcional que encadeia as duas falhas para driblar o ASLR.

**Por que importa:** muda o status de "tentativas" para "explorada segundo a CISA". Quem roda PHP deve estar em 8.5.12, 8.4.27, 8.3.36 ou 8.2.35, especialmente com mod_php. As linhas 8.1 e anteriores dependem de backport da distribuição.

## Evidências
- [Catálogo KEV (JSON)](https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json)
- [Alerta da CISA (26/10)](https://www.cisa.gov/news-events/alerts/2026/10/26/cisa-adds-two-known-exploited-vulnerabilities-catalog)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/cisa-confirms-php2shell-vulnerabilities-now-exploited-in-attacks/)
- [Security Affairs](https://securityaffairs.com/?p=201538)
- [Recorded Future](https://www.recordedfuture.com/blog/php2shell-vulnerability-exploitation)

## Red flags
- "CISA confirma ataques" (manchetes): o que a CISA publica é a inclusão no KEV. O alerta não traz evidência por CVE, e tentativa não é intrusão bem-sucedida.
- Os números de escala (milhões de tentativas, 34 milhões de serviços PHP expostos) medem exposição e varredura, não comprometimento.
- Os dois PoCs públicos mais citados usam uma teoria que o próprio autor invalidou (Recorded Future).

Histórico: [[2026-10-26-php2shell-honeypot-unit42]] · [[2026-10-26-php2shell-industrial]]

Edição: [[2026-10-27-tech]]
