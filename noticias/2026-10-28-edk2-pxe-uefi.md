---
titulo: "Falha no driver PXE do EDK2 (CVE-2026-97631) pode travar e talvez executar código no boot de máquinas que iniciam pela rede; não afeta a maioria dos servidores"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 78
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, hardware, open-source, edk2]
---
O advisory GHSA-99cj-7hg9-mp4m do TianoCore descreve a CVE-2026-97631 (CVSS 4.0 9.5), publicada em 22/10. Os handlers de erro ICMP (IPv4 e IPv6) do driver PXE Base Code do EDK2 calculam mal os limites e estouram um campo de 504 bytes. O impacto confirmado é travar o boot. A execução de código na fase DXE, antes do Secure Boot, é só possível e exige conhecer o build do firmware do alvo. A falha só afeta máquinas que fazem boot pela rede (PXE), e a correção está no PR #13302. Não há relato de exploração.

**Por que importa:** quem usa PXE boot em servidores deve acompanhar os updates de firmware do fabricante (OEM/IBV), que tendem a atrasar em relação à correção do EDK2. Máquinas que iniciam só do disco local não são afetadas.

## Evidências
- [Advisory GHSA-99cj-7hg9-mp4m (TianoCore/EDK2)](https://github.com/tianocore/edk2/security/advisories/GHSA-99cj-7hg9-mp4m)
- [Security Affairs](https://securityaffairs.com/201928/security/cve-2026-97631-16-year-old-uefi-flaw-threatens-servers.html)
- [mlq.ai](https://mlq.ai/news/edk2-pxe-flaw-enables-pre-boot-code-execution-as-firmware-patches-lag/)
- [Ars Technica](https://arstechnica.com/security/2026/10/code-execution-flaw-in-uefi-firmware-threatens-most-servers-on-planet-earth/)

## Red flags
- "Ameaça a maioria dos servidores do planeta" (Ars Technica) não tem base: não há contagem de máquinas nem lista de modelos afetados, e o recorte real é PXE boot.
- Segundo o mlq.ai, a Intel diz não conhecer produto comercial com suporte afetado e a Arm diz que não se aplica diretamente.
- O artigo do Ars Technica não pôde ser lido; a crítica à manchete se apoia no advisory e na cobertura de outros veículos.
- A divulgação foi antecipada por um PR público da AMI, segundo o Security Affairs; os pesquisadores planejavam janeiro.

Opinião externa: groq/openai/gpt-oss-120b · EXAGERADO · falha confirmada, mas "maioria dos servidores" não tem respaldo nas fontes.

Edição: [[2026-10-28-tech]]
