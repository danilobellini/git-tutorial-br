# Exercício

O py.test é um pacote em Python
voltado à realização de testes automatizados
que possui uma arquitetura baseada em introspecção e metaprogramação,
além de muitos plugins.
Alguns desses plugins são incluídos com o próprio py.test,
tais como:

- `monkeypatch`: para possibilitar mocks isoladamente entre testes;
- `recwarn`: para auxiliar no registro/captura de warnings;
- `tmpdir`: criação de diretórios/arquivos temporários;
- `doctest`: integração com o doctest, módulo built-in
             voltado ao uso de exemplos de documentação como testes.

Para realizar o exercício, selecione qualquer um desses 4 plugins.
O código do py.test está em <https://github.com/pytest-dev/pytest>,
e o código do plugin está no módulo homônimo
no diretório/package `_pytest` do repositório.

Questões sobre o py.test e o plugin escolhido
(`monkeypatch`, `recwarn`, `tmpdir` ou `doctest`):

1. Quando o plugin foi commitado no projeto?
   Nessa ocasião, quantos arquivos foram afetados?

2. Quem são os desenvolvedores envolvidos com a versão atual do plugin?
   Na história do plugin, há mais alguém envolvido?

3. Avaliando o repositório inteiro do py.test,
   qual é o commit com o maior assunto em sua mensagem?
   E com o menor assunto?
   Se você pudesse trocar essas mensagens, o que colocaria no lugar?

4. O status de desenvolvimento exibido no PyPI para o projeto
   é obtido a partir de um *classifier* no setup.py.
   Quais commits fizeram o py.test mudar esse status?
   Qual foi a primeira versão estável do py.test com esse status?

5. Desde a versão 3 do py.test, quantos foram os releases?
   Em quais desses releases houve mudança no plugin selecionado?

6. Um DAG (*Directed Acyclic Graph*) pode ter mais de uma raiz?
   Quantas o repositório do py.test possui?

7. Esse repositório já esteve em SVN (Subversion),
   já esteve em hg (Mercurial),
   e em algum instante foi convertido para git.
   Já esteve no BitBucket <https://bitbucket.org/hpk42/pytest>,
   e hoje está no GitHub.
   O hábito de fazer referência a alguma *issue* ou *pull request*
   usando números com prefixo `#` nas mensagens dos commits
   trouxe problemas com o auto-incremento do *issue tracking system*
   nessa mudanças, uma dificuldade para se referir à *issue* correta.
   Qual a solução adotada pelo projeto para manter
   a informação acessível mesmo com uma eventual mudança no *remote*
   e no *issue tracking system*?

Desafios:

8. Quantos merges há no projeto?
   Há algum merge com mais de 2 *parents*?

9. Quando aconteceram as transições SVN/hg/git e BitBucket/GitHub?

Perguntas abertas:

10. Qual é a documentação mais importante do projeto?
    E a mais abraangente?

11. O que você pode dizer sobre os whitespaces
    e sobre estilo da mensagem de commit?
