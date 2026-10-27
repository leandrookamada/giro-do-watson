---
titulo: "Dossiê: os três resultados que a OpenAI diz ter obtido com IA (ETH, local smoothing/Kakeya, Yang-Mills/QCD)"
data: 2026-10-26
area: ia
tags: [dossie, ia, raciocinio, avaliacao, openai]
---
# Dossiê: OpenAI, ETH, Kakeya e Yang-Mills

> Estado apurado em 27/10/2026, um dia após o anúncio. O post da OpenAI ("Working with academic communities to build scientific understanding", 26/10) deu 403 e não foi lido diretamente: o que ele diz vem de citações na imprensa. Manuscritos e arquivos Lean foram lidos direto no repositório `openai/math`.
> Pesquisa: 3 frentes Watson (ETH, local smoothing/Kakeya, Yang-Mills/QCD) + revisão do Mycroft. Nenhum resultado matemático foi julgado verdadeiro ou falso aqui: o dossiê descreve o que foi **afirmado**, o que está **publicado** e o que **falta**.

## Em 30 segundos
- **Três afirmações extraordinárias**, todas atribuídas a um modelo interno da OpenAI e sem revisão por pares:
  - um algoritmo que derrubaria a Exponential Time Hypothesis (ETH);
  - uma prova da conjectura de local smoothing em toda dimensão, que traria Kakeya junto;
  - uma prova de existência de teorias de gauge 4D, incluindo QCD.
- **ETH e local smoothing têm material público:** manuscrito em LaTeX/PDF e enunciados formais em Lean no GitHub. A OpenAI **diz** que as provas foram checadas em Lean; ninguém de fora confirmou publicamente.
- **Yang-Mills/QCD não tem nada público.** O grupo de David Gross segura o material e vai escrever o próprio texto. O post não menciona o gap de massa, então isso **não** é o Problema do Milênio.
- **Ninguém de fora validou nem achou erro até 27/10.** Os grupos de revisão foram escolhidos pela OpenAI, e os revisores da ETH escreveram que participar "não é certificação".
- **Como ler:** "a OpenAI afirma ter provado...", nunca "a ETH caiu" ou "Kakeya foi resolvida".

## Linha do tempo
| Data | Fato | Fonte |
|---|---|---|
| 06/10 | Primeiro lote do repositório `openai/math` (centenas de manuscritos), incluindo alegações de Kakeya maximal em 3D e Kakeya em 4D (entrada 074) | repositório (primária) |
| 09/09 e 18/09 | Datas em que, segundo a OpenAI, saíram as provas em linguagem natural de Yang-Mills e de QCD | imprensa citando o post |
| 15/10 | Simons Foundation anuncia US$ 15 milhões com Anthropic e OpenAI para avaliar resultados matemáticos feitos com IA | Simons Foundation (primária) |
| 16–17/10 | Segundo a OpenAI, a prova da ETH foi achada (16/10) e checada em Lean (17/10) | TNW citando a OpenAI |
| 24–25/10 | Posts convidados no blog de Terence Tao sobre o *processo* de liberação de material da OpenAI (não sobre estes resultados) | blog de Tao |
| 25/10 | Data dos dois manuscritos (ETH e local smoothing) | repositório (primária) |
| 26/10 | Commit dos manuscritos e do Lean; anúncio da OpenAI | GitHub API, `history.md` (primária) |

## 1. ETH (Exponential Time Hypothesis)

**O que é afirmado** (manuscrito "The Exponential Time Hypothesis is False", lido no LaTeX):
- Um algoritmo **determinístico**, de **espaço polinomial**, que **conta exatamente** as atribuições satisfatórias de uma fórmula k-CNF (k fixo ≥ 2).
- Tempo: (n+m)^{O_k(1)} · 2^{O_k(n·loglog n/√log n)}, que melhora para 2^{O(n/√log n)} quando o número de cláusulas é proporcional a n.
- O manuscrito afirma que isso refuta a ETH, a SETH, a Gap-ETH, a NSETH e a #ETH, e dá contagem subexponencial de conjuntos independentes, colorações e emparelhamentos perfeitos.
- **O próprio texto ressalva:** o resultado "não implica que problemas NP em geral tenham algoritmos subexponenciais". O limite não se transfere por qualquer redução polinomial.

**Tamanho do salto:**
- Os melhores algoritmos conhecidos para **decidir** 3-SAT rodam em torno de 1,307^n (família PPSZ), ou seja, 2^{cn} com c > 0. Esse número é conhecimento de fundo, não conferido em fonte primária neste dossiê.
- O resultado alegado é de **contagem** (#SAT), problema mais difícil que decidir, em tempo 2^{o(n)}.
- Passaria, portanto, de "exponencial com constante" para "subexponencial".

**O que o Lean cobre** (`lean/ComparatorChallenges/SubexponentialSAT.lean`, `lean/docs/378.md`):
- Só a parte **algorítmica**: uma máquina multi-fita fixa conta exatamente as atribuições em tempo com expoente n(loglog n)²/√log n. O limite é **mais fraco** que o do manuscrito, mas continua subexponencial.
- O passo "algoritmo ⇒ ETH é falsa" é argumento padrão, mas **fica fora** do Lean.
- O arquivo público de enunciado termina em `sorry` por design: é o formato "Comparator", que separa o enunciado da prova. A prova estaria em `lean/OAI/Algorithms/SubexponentialSAT/`. Não verificamos que compila sem `sorry`.
- Se a máquina e a codificação formais capturam o que se quer é julgamento humano, não algo que o Lean prova.

**Revisão:**
- Um grupo que a OpenAI descreve como independente, liderado por Russell Impagliazzo e Ramamohan Paturi (que propuseram a ETH) e Ryan Williams, vai "examinar e explicar" a prova.
- Eles escreveram que o envolvimento "não deve ser tomado como certificação". Não assinaram NDA e não são pagos.
- Williams é autor de um resultado usado no Apêndice C do próprio manuscrito.
- Nenhum parecer foi publicado.

**Reação externa:** Scott Aaronson mencionou em blog (26/10) que seus alunos lhe contaram do resultado, sem avaliar a correção. Não há preprint no arXiv ou no ECCC.

## 2. Local smoothing, Bochner–Riesz, restriction e Kakeya

**O que é afirmado** (manuscrito "Local smoothing for the Euclidean wave equation", lido no LaTeX):
- Prova da conjectura de local smoothing de Sogge para a equação de onda em **toda dimensão n ≥ 2**. O caso n = 2 já era conhecido (Guth–Wang–Zhang, 2019–2020), então o novo seria **n ≥ 3**.
- O teorema crítico vem com perda logarítmica.
- A partir da estimativa de onda, **em ramos paralelos** (não em cadeia), o manuscrito deduz:
  - Bochner–Riesz e a função quadrática de Stein;
  - estimativas de restriction/extensão **no interior** do intervalo conjecturado (desigualdades estritas, sem os extremos);
  - as conjecturas maximais de Kakeya e de Nikodym, e daí que todo conjunto de Kakeya em R^n tem dimensão de Hausdorff n.
- A ideia nova descrita é uma "equação auxiliar" do tipo Hessiano, com filtragem direcional ao longo de raios de luz.

**Atenção à frase-resumo:**
- Segundo citação do TNW, o post da OpenAI diz que o resultado "também resolveria as conjecturas de Kakeya e de restriction de Stein em todas as dimensões".
- O manuscrito é mais restrito: a restriction vale **só no interior** do intervalo.
- O exagero, portanto, começa na frase da própria OpenAI, e parte da imprensa o repetiu.

**Tamanho do salto:**
- Kakeya em R² é clássico. Kakeya em R³ foi provado por Wang e Zahl em 2025 (arXiv 2502.17655).
- Em n ≥ 3, o local smoothing só tinha resultados parciais.
- O alegado seria a conjectura completa em toda dimensão, o que tornaria redundantes as alegações de Kakeya 3D e 4D que a própria OpenAI publicou em 06/10.

**O que o Lean cobre** (`lean/ComparatorChallenges/LocalSmoothing.lean`, `lean/docs/079.md`):
- Seis enunciados formais: local smoothing, Bochner–Riesz, extensão esférica, Kakeya maximal (com perda δ^{-ε}), dimensão de Hausdorff e função quadrática de Stein. Há ainda um sétimo, sobre volume de tubos em 3D.
- Todos têm `sorry` no arquivo de enunciado, por design. A OpenAI diz que a prova foi checada; ninguém de fora confirmou.

**Revisão:**
- Nenhum revisor nomeado para este resultado: segundo a imprensa, a OpenAI deixou que os pesquisadores "se organizem".
- Não encontramos declaração de especialistas em análise harmônica (Tao, Guth, Wang, Zahl, Demeter). Os posts no blog de Tao em 24–25/10 são posts convidados sobre o processo de liberação, anteriores ao anúncio.
- Sem preprint no arXiv.

## 3. Yang-Mills e QCD

**O que é afirmado** (só por citações do post na imprensa):
- Uma prova "rigorosa", segundo a OpenAI, de que certas teorias quânticas de campo **existem** em 4 dimensões, com campos de gauge e férmions, incluindo QCD.
- "Como subproblema", a existência de Yang-Mills puro.
- Prova em linguagem natural; não se sabe se há formalização.

**O que NÃO é afirmado:**
- O post, segundo as citações, **não menciona** o gap de massa e não diz resolver o Problema do Milênio.
- O problema do Clay Institute exige existência **e** gap de massa para todo grupo de gauge compacto simples.
- Não foi divulgado qual grupo de gauge é coberto nem qual sistema de axiomas foi usado (Wightman ou Osterwalder–Schrader).

**Tamanho do salto:**
- Construções rigorosas só existiam em 2D e em casos abelianos ou com Higgs em 3D e 4D. Balaban fez trabalho parcial em 4D nos anos 1980.
- Nenhum limite contínuo 4D não abeliano estava construído.
- Uma prova de existência em 4D seria um avanço muito grande mesmo sem o gap.

**Artefatos e revisão:**
- **Nada público.** Não encontramos nada de física no repositório `openai/math`.
- O grupo de David Gross (com Michael Douglas, Arthur Jaffe, Igor Klebanov e Nikita Nekrasov) segura o material e vai escrever o próprio texto, sem data. A OpenAI diz ter deixado a decisão de publicação com eles.
- Um blog afirma que o Lean de Yang-Mills foi concluído em 16/10. Isso **não** foi incluído como fato: provavelmente é confusão com a data da ETH, e não há fonte primária.
- Não encontramos declaração de Gross, Jaffe, Witten ou do Clay. O problema continua listado como "não resolvido" no site do Clay.

## Dinheiro e contexto
- Em 15/10, a Simons Foundation anunciou US$ 15 milhões com Anthropic e OpenAI, cerca de US$ 5 milhões de cada empresa, para ajudar matemáticos a avaliar resultados feitos com IA e definir padrões. **Não é específico destes resultados nem de física.**
- Um blog diz que a OpenAI vai financiar uma conferência a pedido do grupo da ETH. A informação vem só desse blog e não foi confirmada.
- Contexto de credibilidade: o lote de 06/10 recebeu críticas fortes de parte de matemáticos sobre a qualidade dos textos ("incomprehensible slop", segundo um pesquisador citado pela Scientific American). O próprio README do repositório avisa que resultados não formalizados "podem ter problemas".

## Red flags
- **Fonte única e interessada:** tudo vem da OpenAI, e nenhum dos três resultados tem verificação externa publicada.
- **"Verificado em Lean" é afirmação da OpenAI:**
  - os arquivos públicos de enunciado estão em `sorry` por design;
  - na ETH, o Lean cobre só o algoritmo, com limite mais fraco;
  - a fidelidade dos enunciados formais é julgamento humano.
- **Revisores escolhidos pela empresa:** a OpenAI chama os grupos de independentes. Os revisores da ETH incluem os autores da hipótese e um autor citado no próprio paper. Não há revisor nomeado para Kakeya. O grupo de física segura o material.
- **Frase-resumo mais ampla que o manuscrito:** "Kakeya e restriction em todas as dimensões", contra a restriction só no interior do intervalo.
- **Yang-Mills sem nada para verificar:** existência sem gap, grupo de gauge não divulgado, axiomas não divulgados, sem Lean público.
- **Datas e números variam entre agregadores** que reescrevem o mesmo post. Contar fontes aqui não é corroboração.

## O que acompanhar
- Parecer do grupo Impagliazzo–Paturi–Williams sobre a ETH.
- Port independente do Lean da ETH (projeto `complexitylib`, issue 1226).
- Reação de especialistas em análise harmônica e a iniciativa comunitária `oai-math-revised`.
- O texto do grupo de Gross sobre Yang-Mills/QCD.
- Preprints no arXiv ou no ECCC.

## Não verificado
- O texto do post da OpenAI (403).
- A compilação completa do Lean sem `sorry`, nos dois casos.
- O PDF do enunciado oficial do Clay (lido via Wikipedia e MathWorld).
- Os últimos ~15 mil caracteres do manuscrito da ETH.
- O expoente atual exato do melhor algoritmo de 3-SAT.

## Fontes principais
- [history.md do repositório](https://raw.githubusercontent.com/openai/math/main/history.md) · [CONTENTS.md](https://raw.githubusercontent.com/openai/math/main/CONTENTS.md)
- [Manuscrito ETH](https://github.com/openai/math/tree/main/preprints/The-Exponential-Time-Hypothesis-is-False-October-25-2026) · [Lean ETH, documentação](https://raw.githubusercontent.com/openai/math/main/lean/docs/378.md) · [enunciado Lean ETH](https://raw.githubusercontent.com/openai/math/main/lean/ComparatorChallenges/SubexponentialSAT.lean)
- [Manuscrito local smoothing, introdução](https://raw.githubusercontent.com/openai/math/main/preprints/Local-smoothing-for-the-Euclidean-wave-equation-October-25-2026/build/sections/introduction.tex) · [Lean local smoothing, documentação](https://raw.githubusercontent.com/openai/math/main/lean/docs/079.md)
- [The Next Web](https://thenextweb.com/news/openai-exponential-time-hypothesis-false-kakeya-yang-mills) · [Scott Aaronson](https://scottaaronson.blog/?p=10239)
- [Wang–Zahl, Kakeya em R³](https://arxiv.org/abs/2502.17655) · [Guth–Wang–Zhang, local smoothing 2+1](https://arxiv.org/abs/1909.10693)
- [Clay: Yang–Mills](https://www.claymath.org/millennium/yang-mills-the-maths-gap/) · [Simons Foundation, 15/10](https://www.simonsfoundation.org/?p=61382)
- [Blog de Terence Tao (posts de 24–25/10)](https://terrytao.wordpress.com/2026/10/24/oai-math-revised-a-community-hub-for-revising-openais-math-write-ups/)

Edição: [[2026-10-26-ia]]
