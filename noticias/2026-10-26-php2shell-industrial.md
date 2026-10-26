---
titulo: "PHP2Shell chega a produtos industriais: Siemens, Schneider, B&R e outros publicam advisories; vínculo com a Coreia do Norte é só suspeita"
data: 2026-10-26
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 78
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, hardware, php, ics]
---
Fabricantes industriais começaram a publicar advisories sobre o PHP2Shell (CVE-2026-109618 e CVE-2026-109619). A Siemens confirma impacto só no RUGGEDCOM APE1808 (via PAN-OS, de terceiros) e lista 28 produtos como não afetados. Segundo o SecurityWeek, que compila os advisories:
- **Schneider:** patch no EcoStruxure Security Expert 1.48.4.0.
- **B&R:** patches no APROL previstos para 26 e 29/10.
- **Johnson Controls:** patches para câmeras Illustra.
- **Belden NetModule NRSW:** sem patch; mitigação é desativar a interface web.
- **Rockwell e Hitachi Energy:** ainda investigam. A Moxa não é afetada.

Separadamente, a CYFIRMA atribui uma campanha de varredura, contra 216 hosts que os próprios operadores dizem ser vulneráveis, ao ecossistema Lazarus, com confiança **moderada**.

**Por que importa:** quem opera ambiente industrial deve checar os advisories dos seus fornecedores. Em vários casos a correção é atualizar o PHP embutido ou isolar a interface web, e não há patch do produto em si.

## Evidências
- [Siemens SSA-566512 (APE1808 afetado)](https://cert-portal.siemens.com/productcert/html/ssa-566512.html)
- [Siemens SSA-566435 (28 produtos não afetados)](https://cert-portal.siemens.com/productcert/html/ssa-566435.html)
- [SecurityWeek: compilação dos fabricantes](https://www.securityweek.com/industrial-vendors-check-products-for-php2shell-vulnerabilities/)
- [CYFIRMA: atribuição suspeita](https://www.cyfirma.com/research/cyfirma-threat-advisory-suspected-dprk-campaign-staging-php2shell-targeting-against-global-php-infrastructure/)
- [CISA: alerta do PHP](https://www.cisa.gov/news-events/alerts/2026/10/21/critical-vulnerabilities-php-require-immediate-patching)

## Red flags
- "Siemens confirmou produtos afetados" é verdade para um único produto, via componente de terceiros. O impacto na ABB também é num componente embutido (DokuWiki).
- A atribuição à Coreia do Norte vem de uma única fornecedora de threat intel, baseada em idioma e comportamento, sem infraestrutura ou malware em comum. A própria CYFIRMA admite um grupo criminoso sem vínculo estatal como alternativa.
- O link do The Hacker News ainda diz "exploitation hits government", mas a Unit 42 retirou esse caso em 25/10.
- Só o advisory da Siemens foi lido direto. Os demais fabricantes estão via SecurityWeek.
- Nenhum comprometimento confirmado em ambiente industrial. A única exploração bem-sucedida pública segue sendo em honeypot.

Atualização de: [[2026-10-26-php2shell-honeypot-unit42]]

Edição: [[2026-10-26-tech]]
