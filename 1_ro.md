# Investigação de um repositório (somente leitura)

- Metadados
  - Mensagem de commit (título e corpo)
  - 2 UNIX Timestamps (autoria e commit) inteiros (precisão: segundos)
  - Nome/e-mail do autor
  - Nome/e-mail do committer
  - Parents (commits "pais/mães")
  - Anotações
- Conteúdo do arquivos
  - Deltas? Não!
- SHA1
- refs
  - HEAD
  - branches
  - tags
  - `^` / `~`
  - *Detached* HEAD
  - `.git/HEAD`
  - remote-tracking

```
gitk
  --all
```

```
git log
  -n
  --all
  --oneline
  --decorate
  --graph
  --format
    %h
    %p
  --follow
  --full-history
  --grep
```

```
git blame
```

```
git show
  --stat
  --numstat
```

```
git diff
  --cached (ou --staged)
  --name-only
  --check
  -b
```

```
git grep
  -P
  -A
  -B
```

```
git bisect
  start
  old
  new
  reset
```
