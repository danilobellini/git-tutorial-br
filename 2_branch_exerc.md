# Exercício

O objetivo é criar um novo repositório do zero
com a seguinte estrutura:

```
             @---L---M     b1
            /
           /   D---G---H   b2
          /   /
         C---F---I---K     b3
        /
   A---B---E---J           master
```

As letras de A a N representam commits,
e o commit à esquerda é o parent do commit à direita
sempre que há linhas unindo os mesmos.

As branches indicadas `b1`, `b2`, `b3` e `master`
apontam para o commit à direita de suas linhas.

Todos os commits inserem um único arquivo
com a própria letra do commit em minúsculo,
e.g. `a.py` para o A, `d.py` para o D,
exceto o commit @, que possui dois arquivos: `x.py` e `y.py`.

Cada arquivo `.py`, se chamado, deve ter uma mensagem diferente.
Guarde o resultado deste exercício,
ele será utilizado em breve.


## Exercício extra

O objetivo agora é
criar uma nova branch `merge-mastered` sem modificar as demais,
com novos commits N, O, P, Q, R e END que façam o grafo ficar da forma:

```
   O----------   --------R
              \ /       / \
   N-----------P-------Q   \
              /       /     \
             @---L---M       \
            /                 \
           /   D---G---H-------\
          /   /                \\
         C---F---I---K---------\\\
        /                       \\\
   A---B---E---J-----------------END   merge-mastered
```
