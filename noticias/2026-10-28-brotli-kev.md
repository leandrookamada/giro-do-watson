---
titulo: "CISA põe a falha do Brotli (CVE-2026-111497) no KEV; exploração vista até agora são duas tentativas em honeypots, uma com exploit quebrado"
data: 2026-10-28
area: tech
secao: Cybersecurity
veredito: PROVÁVEL
confianca: 79
contestado: false
checagem: dupla
tags: [tech, vulnerabilidade, exploracao-ativa, brotli, cisa]
---
A CISA adicionou a CVE-2026-111497, falha no decodificador do Google Brotli, ao catálogo KEV em 27/10, com prazo federal em 10/11. Segundo o KEV, um atacante remoto não autenticado pode corromper memória do decodificador, vazar memória, causar DoS ou possivelmente executar código. A falha afeta as versões 1.0.3 a 1.2.0 e foi corrigida em 21/10 (Brotli 1.2.1, 1.1.1 e 1.0.10; Node.js 22.23.4, 24.22.1 e 26.12.1). A exploração observada publicamente é pequena: a Previdian registrou uma tentativa de um IP nos EUA em 27/10, e a ELLIO viu uma em 26/10 com um exploit que não gerou shell em 50 testes.

**Por que importa:** quem ainda não atualizou Brotli e Node.js de 21/10 em diante deve atualizar agora. A entrada no KEV obriga órgãos federais dos EUA a corrigir até 10/11.

## Evidências
- [CISA KEV (JSON)](https://raw.githubusercontent.com/cisagov/kev-data/develop/known_exploited_vulnerabilities.json)
- [Registro CVE (CNA Google)](https://raw.githubusercontent.com/CVEProject/cvelistV5/main/cves/2026/111xxx/CVE-2026-111497.json)
- [GitHub Advisory GHSA-9v8h-qqgm-4m35](https://github.com/advisories/GHSA-9v8h-qqgm-4m35)
- [Brotli v1.2.1](https://github.com/google/brotli/releases/tag/v1.2.1)
- [Previdian: telemetria de honeypot](https://previdian.com/CVE-2026-111497)
- [SecurityWeek](https://www.securityweek.com/cisa-warns-of-node2shell-exploitation-as-honeypots-log-attack-attempts/)
- [BleepingComputer](https://www.bleepingcomputer.com/news/security/cisa-warns-of-hackers-now-exploiting-critical-node2shell-flaw/)

## Red flags
- A manchete do BleepingComputer ("hackers now exploiting") sugere onda de ataques; a evidência pública são duas tentativas, e a CISA não deu detalhes.
- O The Hacker News liga o tráfego do Brotli aos ataques PolyShell contra Adobe Commerce. Nenhuma fonte técnica sustenta esse vínculo: as duas CVEs só entraram no KEV no mesmo dia.
- Severidade divergente: CVSS 4.0 9.2 do Google, "High" para o Node.js. A execução de código depende de condições específicas.

Opinião externa: groq/openai/gpt-oss-120b · PROVÁVEL · KEV e exploração confirmados por fontes primárias; nada liga o Brotli aos ataques PolyShell.

Edição: [[2026-10-28-tech]]
