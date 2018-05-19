# Rebase

## Rebase interativo

- Principal comando para manipulação de histórico
- Resulta em uma única sequência de commits "lista ligada linear"
- Casos de uso:
  - Trocar a ordem de commits
  - Remover commit na história recente
  - Editar commit na história recente
    (generalização do git commit --amend)
  - Inserir commit na história recente
  - Dividir commit (split)
  - "Linearizar" merges

"História recente" significa a partir do último merge.
Aplicar o rebase a conteúdo anterior a esse commit de merge
irá linearizar a história,
fazendo todos os commits terem um único *parent*

```
git rebase
  -i
    pick
    edit
    reword
    squash
  --root
  --continue
  --abort
```


## Rebase não-interativo

`git rebase --onto`
