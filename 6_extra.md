# Extra!

Há inúmeros outros comandos no git, tais como,
`git submodule`, `git am`, `git format-patch`, `git svn`, etc.,
além de possibilidades de casos de uso.
Falar de git por si só poderia resultar em um curso de um ano inteiro!

Aqui consta algumas outras ações que podem ser realizadas com o git
que têm a ver com o que foi exposto neste tutorial.


## Git fetch VS Merge hell

Até agora, o único comando do `git` que envolveu algum servidor
foi o `git clone`.
Os outros comandos que se comunicam com o servidor são:

- `git fetch`: atualiza todas as branches *remote-tracking*
- `git push`: atualiza uma branch ou tag no servidor
- `git pull`: fetch + merge, basicamente

Usar o `git fetch` ao invés do `git pull` traz uma vantagem:
o controle sobre suas branches locais.
Você sempre pode fazer um `git merge --ff-only` depois,
talvez você queira usar o `git diff` antes.

Em cenários com merges desencontrados de código indo e voltando
(e.g. funcionalidades sendo habilitadas/desabilitadas),
o `git pull` pode ser um dos elementos que inicia o *merge hell*:
situação na qual o mesmo conteúdo é aplicado diversas vezes,
há commits desnecessários (do ponto de vista do fast forward),
além de commits "sujando" o blame,
e um visual de *Guitar Hero* (ou *Frets on Fire!*) no grafo.
Merges são úteis, mas às vezes precisamos remover conteúdo
ao invés de reverter.

Um simples `git commit --amend` pode ajudar a evitar o vai-e-volta,
a política de nunca sobreescrever (`git push -f`) o `master`
não se aplica àquela branch em que apenas você está trabalhando.


## Garbage collector

Se quisermos evitar que alguém recupere conteúdo de um histórico,
por exemplo por ter credenciais/senhas/tokens removidos,
apenas fazer o rebase do trecho pode não ser o suficiente.
Se alguém souber o hash (ou ver pelo `git reflog`),
poderá recuperar o commit que não faz parte da história
que leva aos branches/tags e demais refs salvos.

Para isso, podemos usar o `git gc`.
Podemos verificar os hashes dos commits que não são referenciados
com o `git fsck --unreachable`.


## Filter-branch

Para modificar o e-mail de todos os commits de uma história:

```
git filter-branch
  --commit-filter 'GIT_AUTHOR_EMAIL=novo@email.br \
                   GIT_COMMITTER_EMAIL=novo@email.br \
                   git commit-tree "$@"'
```

Esse `git commit-tree` tem um comportamento diferente do `git commit`,
por exemplo no que diz respeito ao timestamp de commit.

Normalmente ninguém quer mudar o repositório inteiro, mas somente os
commits que já estão atribuídos a uma pessoa em específico.

```
git filter-branch
  --commit-filter 'if [ "$GIT_AUTHOR_NAME" = "Someone" ] ; then \
                     export GIT_AUTHOR_EMAIL=novo@email.br ; \
                   fi ; \
                   if [ "$GIT_COMMITTER_NAME" = "Someone" ] ; then \
                     export GIT_COMMITTER_EMAIL=novo@email.br ; \
                   fi ; \
                   git commit-tree "$@"'
```

Esse é um exemplo clássico do `filter-branch`,
mas não é algo nem simples, nem comum.


## Git subtree

Podemos ter dois DAGs se unindo em um merge
se estávamos fazendo tudo em um único repositório do git,
com a separação iniciada pelo `git checkout --orphan`.

Mas e se quiséssemos fazer um merge de repositórios diferentes?
O comando que faz isso existe: é o `git subtree`.
Foi utilizado no repositório do <https://github.com/Dojo-SP/DojosiM>,
unindo os commits de repositórios novos de diferentes Coding Dojos.

Supondo que os diretórios "irmãos" `a` e `b` são repositórios `git`,
ambos com apenas a branch `master`,
e que se deseja unificá-los em `a`,
com o conteúdo de `b` inserido no diretório `other`.
O comando fica:

`git subtree add --prefix other ../a master`
