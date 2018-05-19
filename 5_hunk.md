# Hunk patching e resolução de conflitos

*Hunks* são os blocos de alteração no código.
Se você alterou uma linha no início do arquivo,
três linhas adjacentes do final do arquivo e inseriu um outro arquivo,
então você têm 3 hunks de mudanças.


## Patching

Com o `-p` (de *patch*), é possível modificar seletivamente os hunks
tanto no workspace como na área de staging:

- `git add -p`: hunks de *workspace* p/ *staging*;
- `git reset -p`: hunks de *commit* p/ *staging*;
- `git checkout -p`: hunks de *commit* p/ *staging* e *workspace*.

Opções de *patch*:

- `y`: aplica o hunk (*yes*);
- `n`: ignora o hunk (*no*);
- `s`: tenta dividir em mais de um hunk (*split*);
- `a`: aplica todos os hunks deste arquivo (*all*);
- `d`: ignora todos os hunks deste arquivo (*delete*);
- `q`: ignora todos os demais hunks (*quit*);
- `e`: edita o hunk (*edit*).


## Conflitos

Os comandos `cherry-pick`, `rebase` e `merge`
podem resultar em conflito quando os diferentes caminhos
possuem hunks que modificam as mesmas linhas de código, ou adjacentes.

A resolução do conflito é sempre manual. Após resolver o conflito,
utiliza-se o `--continue` do respectivo comando para retomar o mesmo,
ou então o `--abort` para cancelar o processo em andamento,
assim como foi visto com o `rebase` interativo.

O conflito é marcado por regiões com blocos
delimitados por `<<<<<<`, `======` e `>>>>>>`,
os quais separam o hunk de cada uma das versões (HEAD e MERGE_HEAD)

Podemos usar o `git diff`
para visualizar a origem de cada parte depois das alterações
(*3-way diff*). Ou então o próprio `git show`:

- `git show :1:arquivo # Ancestral comum`
- `git show :2:arquivo # HEAD`
- `git show :3:arquivo # MERGE_HEAD`
