# Tutorial de git para quem já sabe commitar

Por *Danilo J. S. Bellini*

Este tutorial admite que o participante conheça
a diferença entre *workspace*, área de *staging* e *commits*,
e já tenha utilizado alguns recursos do git, incluindo:

- `git init`
- `git clone`
- `git commit`
- `git add`
- `git reset`
- `git push`
- `git pull`
- `git log`
- `git mv`
- `git rm`
- `git remote`
- `git config`

E que já tenha sido apresentado
a algum guia de estilo para mensagens de commit.
O blog post
<https://chris.beams.io/posts/git-commit/#seven-rules>
condensa e justifica 7 regras de estilo de outras fontes
(o *This has all been said before* possui uma referência por palavra),
regras estas traduzidas/adaptadas para o português neste tutorial,
e incrementadas para abranger outros cenários.

Caso você não tenha o domínio sobre os fundamentos acima expostos,
recomendo a leitura do capítulo *Git Basics* do livro *Pro Git*,
gratuitamente disponível em <https://git-scm.com/book>
em sua versão web (HTML, PDF).
O link para a primeira edição em português é
<https://git-scm.com/book/pt-br/v1>
e o capítulo citado teve o título traduzido como *Git Essencial*.

Há ainda sites que ensinam o básico de git de maneira interativa,
como o <https://try.github.io>.
O <https://learngitbranching.js.org> ensina a organização em branches
de forma interativa e bastante visual,
algo que pode auxiliar a compreensão deste material
(caso o leitor saiba inglês).
Outra opção seria o jogo <https://ohmygit.org/> que mostra as
estruturas internas de repositórios git em tempo real

O conteúdo deste tutorial está organizado da seguinte forma:

0. [Estilo](0_style.md)
1. [Visualização](1_ro.md)
2. [Branching](2_branch.md)
3. [Commit deltas (cherry-pick / stash)](3_pick_stash.md)
4. [Rebase](4_rebase.md)
5. [Hunk patching e resolução de conflitos](5_hunk.md)
6. [Exemplos de outros assuntos](6_extra.md)
