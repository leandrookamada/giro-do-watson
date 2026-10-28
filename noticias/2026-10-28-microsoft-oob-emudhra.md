---
titulo: "Microsoft publica updates fora de ciclo que removem 7 raízes da eMudhra em máquinas Windows sem atualização automática da lista de confiança"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 86
contestado: false
checagem: dupla
tags: [tech, criptografia, web, microsoft, emudhra]
---
Em 26/10 a Microsoft lançou atualizações fora de ciclo (KB5134133 para Windows 11 24H2, 25H2 e 26H2; KB5134125 para Windows 10, segundo o BleepingComputer) que removem sete certificados da lista de confiança: seis raízes eMudhra G3 e um cross-sign da AAA Certificate Services. São para máquinas que não recebem a lista de confiança (CTL) automaticamente; as demais já recebem a mudança por ela. Antes, em 20/10, a Microsoft já tinha bloqueado as oito intermediárias da eMudhra com chaves triviais (seis de TLS e duas de assinatura de código). O Edge removeu as raízes em 27/10, e a Microsoft ainda investiga as demais raízes da eMudhra.

**Por que importa:** máquinas desconectadas ou com CTL automática desligada precisam do KB para deixar de confiar nessas raízes. Quem tem certificado emitido sob elas precisa trocá-lo.

## Evidências
- [MSRC: resposta às chaves comprometidas da eMudhra](https://www.microsoft.com/en-us/msrc/blog/2026/10/microsoft-response-to-compromised-emudhra-certificate-authority-keys)
- [Microsoft: KB5134133](https://support.microsoft.com/help/5134133)
- [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-windows-oob-updates-to-distrust-emudhra-certificates/)
- [The Register (incidente das chaves)](https://www.theregister.com/a/5304312)

## Red flags
- "Protege sistemas Windows" simplifica: o OOB é só para quem não recebe CTL automática.
- A remoção das raízes é um ato diferente do bloqueio das intermediárias comprometidas, que já tinha ocorrido em 20/10. A Microsoft diz que isso "não é o mesmo que revogar".
- Não há evidência de abuso das chaves; o risco descrito é de forjar certificados.
- A página emudhra.we-have-a-problem.com, citada na triagem, trata da Apple, não da Microsoft, e não foi usada como prova.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · fontes primárias da Microsoft confirmam os updates; imprensa independente corrobora.

Edição: [[2026-10-28-tech]]
