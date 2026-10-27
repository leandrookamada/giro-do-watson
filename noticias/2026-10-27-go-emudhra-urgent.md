---
titulo: "Go detalha sua primeira correção URGENT: 1.27.3 e 1.26.10 deixam de confiar em 8 intermediárias da eMudhra com chaves quebráveis"
data: 2026-10-27
area: tech
secao: Cybersecurity
veredito: CONFIRMADO
confianca: 90
contestado: false
checagem: dupla
tags: [tech, criptografia, open-source, golang, emudhra]
---
Em 26/10, o time de segurança do Go publicou a cronologia de sua primeira release de segurança URGENT. Oito CAs intermediárias da eMudhra (seis de TLS e duas de assinatura de código) tinham chaves privadas recuperáveis "em microssegundos". O Go 1.27.3 e o 1.26.10, lançados em 19/10 em menos de 7,5 horas desde o alerta, fazem o verificador de certificados do `crypto/x509` (usado por `net/http`, `crypto/tls` e gRPC) rejeitar cadeias que passem por essas intermediárias (CVE-2026-111943). No Windows e no macOS o Go delega a verificação ao sistema; o impacto prático é no Linux, onde não há revogação uniforme.

**Por que importa:** quem distribui binários Go que fazem TLS no Linux precisa **recompilar** com 1.27.3 ou 1.26.10. Atualizar o Go instalado não muda binários já compilados. Para conferir: `go version -m <binário>` e `govulncheck -mode=binary <binário>`.

## Evidências
- [Blog do Go: resposta ao incidente](https://go.dev/blog/emudhra-incident)
- [Notas de release do Go](https://go.dev/doc/devel/release)
- [Issue golang/go#82345 (CVE-2026-111943)](https://github.com/golang/go/issues/82345)

## Red flags
- O post é também autopromoção do processo URGENT, mas a cronologia é verificável na issue e nas release notes.
- A eMudhra diz que a maioria das intermediárias nunca foi usada em produção. Mesmo assim, revogação só protege quem checa revogação, e por isso a mudança no Go importa.

Contexto: incidente da eMudhra em 17/10, com Mozilla, Google, Apple e Microsoft bloqueando as intermediárias.

Edição: [[2026-10-27-tech]]
