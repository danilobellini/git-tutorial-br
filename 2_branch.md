# Branching

```
git branch
  -d
  -D
  -Dr
  --all

git checkout
  (arquivo)
  -b
  -f
  --orphan

git tag
  -d
  -f
```

## Merge (mescla)

- Opções de merge:
  - *Fast forward*: padrão, equivalente ao rebase,
    aplicável somente quando não houve branching;
  - Novo commit: ao invés de mudar a história,
    cria um commit com 2 *parents*.

- Polêmica:
  <https://github.com/torvalds/linux/pull/17#issuecomment-5663780>

O merge permite múltiplos *parents*, passados como argumentos.
Algumas opções do `git merge`:

- `--no-ff`: Desabilita o fast forward;
- `--ff-only`: Não realiza o merge se isso for criar um novo commit;
- `--allow-unrelated-histories`: Unifica árvores separadas
  (criadas com `git checkout --orphan`).


## Exemplo

```
cria_commit() {
  printf "%s\n" '#!/usr/bin/env python' \
                "print('$1')" \
         > "$1".py
  chmod +x "$1".py
  git add "$1".py
  git commit -m "Add $1.py"
}

git init
cria_commit first
cria_commit x
git checkout -b alt master^
cria_commit y
git checkout -b alt2 master^
cria_commit z
git checkout -b alt3 master^
cria_commit w
git checkout master
git merge alt alt2 alt3 -m "Merge branches, x+y+z+w octupus"
git checkout --orphan new
git rm -f *.py
cria_commit new
git checkout master
git merge new --allow-unrelated-histories --no-edit
git branch -D alt alt2 alt3 new
```
