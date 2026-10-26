---
titulo: "CERT-UA alerta para câmeras e gravadores Dahua invadidos por senhas fracas e falhas de 2021"
data: 2026-10-26
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 69
contestado: false
checagem: dupla
tags: [tech, exploracao-ativa, hardware, dahua, cert-ua]
---
Segundo o The Record, o CERT-UA alertou que câmeras e gravadores Dahua conectados à internet foram comprometidos: os atacantes alteraram configurações e criaram contas não autorizadas. Os vetores descritos são três:
- o recurso P2P Easy4IP, cujos números de série seguem padrões previsíveis;
- senhas fracas ou padrão;
- as falhas de bypass de autenticação CVE-2021-33044 e CVE-2021-33045, corrigidas desde 2021.

O CERT-UA não informou quantos dispositivos, quando nem quem. Em agosto, a Hunt.io havia documentado outra campanha ("CameraSwarm") com mais de 14.500 dispositivos Dahua comprometidos, sobretudo na Ucrânia e na Rússia; não há evidência de que seja o mesmo ataque.

**Por que importa:** quem tem câmeras ou gravadores Dahua deve:
- atualizar o firmware (advisory SA-2021-0130);
- desativar o P2P se não usa;
- trocar as senhas e procurar contas desconhecidas (a Hunt.io cita `p2pwn`);
- tirar a porta 37777 da internet.

## Evidências
- [The Record: relato do alerta do CERT-UA](https://therecord.media/ukraine-cert-ua-warning-chinese-dahua-cameras-hacked)
- [Hunt.io: campanha CameraSwarm (contexto, agosto)](https://hunt.io/blog/operation-cameraswarm-dahua-cameras-compromised)

## Red flags
- O alerta original do CERT-UA não pôde ser lido (403): tudo vem do relato do The Record.
- Não é falha nova: as CVEs são de 2021 e já têm correção; o problema é dispositivo desatualizado e exposto.
- Não misturar com os 14.500 dispositivos da campanha de agosto: são incidentes distintos até prova em contrário.
- Sem números, datas nem atribuição no alerta. "Casos identificados" é verdadeiro, mas vago.

Edição: [[2026-10-26-tech]]
