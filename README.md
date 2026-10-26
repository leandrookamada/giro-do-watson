# O Giro do Watson 📰

Notícias de **tecnologia, cybersecurity e política** checadas antes de chegar aqui. Cada nota diz o que foi verificado, o veredito, a confiança, os links das evidências e as red flags da cobertura original.

Este repositório é o **cofre Obsidian** gerado pelo [Dr. Watsonews](https://github.com/leandrookamada/dr-watsonews), que roda dentro do Claude Code: Lestrade faz a triagem, Watson vai atrás das fontes primárias e Mycroft procura o que está errado. Aqui ficam só as notas; o código e o método estão no outro repositório.

## Estrutura

```
noticias/   uma nota por notícia verificada (AAAA-MM-DD-<slug>.md)
edicoes/    uma nota por dia e área, com destaques e o que foi descartado
dossies/    pesquisas direcionadas sobre um tema (ex.: uma CVE)
```

Abra esta pasta como vault no [Obsidian](https://obsidian.md) para navegar por tags, links e grafo. No GitHub, os arquivos são Markdown comum e se leem direto no navegador.

## Vereditos

`CONFIRMADO` > `PROVÁVEL` > `EXAGERADO` > `NÃO VERIFICÁVEL` > `BULLSHIT`

O veredito julga os **fatos**, não a manchete: manchete exagerada sobre fato verdadeiro vira red flag e ganha título reescrito. Na política, o rigor é o mesmo para qualquer lado, e o veredito nunca diz se uma posição é boa ou ruim.

## Aviso

Checagem feita por modelos de linguagem reduz erros, mas não os elimina. Os links de evidência estão em cada nota para você conferir o que importa. Cada nota registra a data da apuração; status de exploração, patches e investigações mudam depois disso.
