# Exercício

Seja um projeto em git utilizando as seguintes branches:

```
             @---L---M     b1
            /
           /   D---G---H   b2
          /   /
         C---F---I---K     b3
        /
   A---B---E---J           master
```

1. Descreva o que você faria para obter uma branch `new-master`
   na qual os commits de A a M estariam em ordem alfabética,
   com o commit @ entre os commits K e L.
   Supondo que nenhum dos commits altera os mesmos trechos do código,
   quais commits teriam alterações, e quais seriam as alterações?

2. Admitindo que se deseja
   manter a história da branch `master` inalterada,
   descreva diferentes formas como o conteúdo das demais branches
   poderia ser inserido à branch `master`.

3. Suponha que o commit @ esteja fazendo duas coisas diferentes,
   uma no arquivos x.py e outra no y.py.
   Como você faria para dividir esse commit em 2,
   cada um contendo apenas as alterações de um dos arquivos?

4. Descreva como uma tal árvore poderia ser transformada em:

```
                       @L'---M'-----Z   fourth-master
                       /           /
                 C'---F'---IK'---DGH'
                /
   A---B---E---J
```
