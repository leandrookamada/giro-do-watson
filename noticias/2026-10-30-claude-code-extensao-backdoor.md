---
titulo: "Versão 2.1.313 maliciosa da extensão Claude Code ficou cerca de 11 horas em marketplaces com backdoor SSH; até 5 mil usuários, origem incerta"
data: 2026-10-30
area: tech
secao: Cybersecurity
veredito: EXAGERADO
confianca: 70
contestado: true
checagem: dupla
tags: [tech, incidente, malware, open-source, claude-code]
---
A versão 2.1.313 da extensão anthropic.claude-code para VS Code foi maliciosa em 29/10: adicionou uma chave SSH do atacante (`svc-telemetry`), abriu túnel reverso e criou persistência (LaunchAgent no macOS, tarefa agendada no Windows, cron); remover a extensão não elimina a persistência. A Cursor diz que a versão "não foi desenvolvida pela Anthropic", que a janela foi de cerca de 11 horas e que no máximo 5.000 usuários foram afetados. A versão limpa 2.1.314 saiu em 30/10. Quem publicou o pacote e como não está estabelecido; a tese de que "a Anthropic foi hackeada no mundo todo" não tem evidência pública.

**Por que importa:** extensões de agentes de código rodam com acesso ao ambiente do desenvolvedor; quem instalou a 2.1.313 deve remover chaves, túneis e tarefas persistentes, não só a extensão.

## Evidências
- [Cursor: aviso de segurança sobre a extensão](https://cursor.com/blog/claude-code-extension-security-notice)
- [StepSecurity: análise técnica da extensão trojanizada](https://www.stepsecurity.io/blog/claude-code-extension-trojanized)
- [Help Net Security: backdoor SSH na extensão](https://www.helpnetsecurity.com/2026/10/30/claude-code-extension-ssh-backdoor/)

## Red flags
- Manchete "extensão oficial distribuída"/"Anthropic hacked… worldwide" vai além do que as fontes sustentam.
- Comunicado da Cursor lido só em trecho de busca; não há comunicado da Anthropic nem da Microsoft.
- Open VSX: StepSecurity diz que o pacote também estava lá e outra fonte contesta.
- THN e doublepulsar devolveram 403; Beaumont (GossiTheDog) contesta a frase "não desenvolvido pela Anthropic", mas só o início do post foi lido.
**Contestado:** Watson deu CONFIRMADO (incidente e mecanismo comprovados); Mycroft deu EXAGERADO (enquadramento "Anthropic hackeada, mundial" e atribuição de publicador não sustentados). Fica o pior dos dois.

Opinião externa: groq/openai/gpt-oss-120b · CONFIRMADO · comunicado da Cursor e análises independentes confirmam a versão com backdoor e o teto de usuários, e descartam comprometimento da Anthropic

Edição: [[2026-10-30-tech]]
