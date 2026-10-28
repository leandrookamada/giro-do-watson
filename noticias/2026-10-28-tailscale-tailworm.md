---
titulo: "Tailscale corrige na 1.104.4 falhas do SSH embutido que deixam um nó autorizado virar root em outros servidores"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: CONFIRMADO
confianca: 88
contestado: false
checagem: simples
tags: [tech, vulnerabilidade, open-source, tailscale]
---
A Cyberdione Labs publicou entre 22 e 24/10 o relatório "Tailworm", com 11 achados no Tailscale 1.104.2, no headscale 0.29.5 e na biblioteca gliderlabs/ssh. Seis deles foram classificados como altos pelos próprios autores. O Tailscale publicou os boletins TS-2026-014 a 017 em 26/10, com correção na versão 1.104.4. O mais grave é o encaminhamento de socket Unix no Tailscale SSH, que alcança sockets só de root e permite executar ou apagar arquivos como root. Para isso, o nó precisa estar autorizado por uma regra de SSH e o encaminhamento precisa estar liberado. Os achados 4 e 6 estão só parcialmente corrigidos e o 9 segue aberto. Não há CVE nem relato de exploração ativa.

**Por que importa:** quem usa Tailscale SSH deve atualizar para 1.104.4 ou superior. Até lá, `TS_SSH_DISABLE_FORWARDING=1` desliga o encaminhamento. O headscale é outro produto e não é corrigido por essa versão.

## Evidências
- [Tailscale: boletins de segurança TS-2026-014 a 017](https://tailscale.com/security-bulletins)
- [Tailscale: atualização da investigação do SSH](https://tailscale.com/ssh-investigation-update)
- [Relatório Tailworm (Cyberdione Labs)](https://tailworm.com)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/tailscale-warns-of-serious-ssh-flaws-allowing-root-privilege-escalation/)
- [SecurityWeek](https://www.securityweek.com/tailscale-rushes-patches-after-uncoordinated-disclosure-of-tailworm-flaws/)

## Red flags
- "Quase uma dúzia de falhas que dão root" mistura componentes: só parte dos 11 achados é do SSH, e roubo de credenciais e DoS vêm de outros módulos (serve, DERP, headscale).
- Os detalhes saíram num fim de semana, antes do patch (SecurityWeek). O relatório não diz se o Tailscale foi avisado antes.
- Sem CVE nem CVSS: a gravidade vem só da classificação dos pesquisadores. O comportamento "wormable" foi demonstrado em laboratório.

Edição: [[2026-10-28-tech]]
