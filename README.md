Bem Vindo ao Curso de Git!
======================

## PRIMEIROS PASSOS

*Verificar se GIT está instalado*

    > git

**<i class="icon-asterisk"> PREPARANDO O AMBIENTE**
> - Criar repositório (pasta que vai guardar todos os arquivos do projeto)
> - mkdir aulagit (cria pasta onde vai ficar arquivos do projeto)
> - cd aulagit (acessar a pasta)

    > git init (cria diretório .git )

**<i class="icon-asterisk"> Agora já tem diretório configurado pelo Git**
> - criar arquivo qualquer um ".txt" no diretório "auldagit" e digite qualquer coisa no arquivo.

**Ajuda! :+1:**
Criar arquivos pelo CMD ou Bash

    > copy NUL arquivo-novobranch.php(cmd)
    > touch arquivo-novobranch.php (bach)

Para editá-los podem usar bloco de notas.

## OS TRÊS ESTÁGIOS DE UM COMMIT

>1 - Untracked

O arquivo está no diretório mas não está no Git 

    >git status

verifica o estágios dos arquivos

>2 - Changes to be commiterd

Quando o arquivo é adicionado e começa a fazer parte de um controle de versão.

    > git add <<nome do arquivo>> 
    > git add .

Agora o arquivo está pronto para entrar no controle de versão.

>3 - Unstage

quando o arquivo passa para o controle de versão ou seja é dado o commit.

**Commit**

    > git commit -m “meu primeiro commit”  

onde o **"-m"** é para colocar uma mensagem.

    > git log 

verifica os commit's dados

    > git log -p 

verifica em cada arquivo comitado o que foi mudado.

    > git log -p -2 

(2 é um índice que indica os últimos arquivos comitado) => verifica nos dois últimos arquivo comitados o que foi mudado.

    > git log --stat

mostra o git log e mais as estatísticas de todos os commits

    > git log --pretty=oneline

Mostra todos os commits em uma linha só.

    > git log --pretty=format:"%h - %an, %ar : %s"

Mostra o início do Rest, quem commitou, quanto tempo atrás, e a descrição do commit.

    > git log --since=2.days

Mostra os logs de todos os commits feitos nos últimos dias (no exemplo foi pedido 2 dias).

## FLUXO E VERSÕES

**Desfazendo o ADD**
Quando você esta no segundo estagio e quer voltar para o primeiro, ou seja, tirar o arquivo de condições de ser commitado.

    >git reset HEAD <<nome do arquivo>>

**Voltando  versões**

Você desja desfazer um commit dado.

* primeiro verificar o ID do commit a ser desfeito, você pode verificar com o comando:

     <pre>> git log
*commit* *f724b698a2c6ae3db03cd5c2ad86d0b4af8c32dd* <=**Este é ID**
Author: Jairo Sousa <jaironsousa@gmail.com>
Date:   Wed Jul 19 21:56:56 2017 -0300*

    <pre> > git checkout f724b698a2c6ae3db03cd5c2ad86d0b4af8c32dd

## BRANCHES

**Entendendo os Branches**

Um desenvolvimento de software possui um linha do tempo principal **“master”** e os **branches** são ramificações dessa linha do tempo que pode ser criando pedaços do software sem alterar a linha do tempo principal, existe também branches de branches.

![imagem01](/img/img-01.PNG)

**Criando o primeiro Branch**

 1. Verifica qual **branch** você está

    <pre> > git branch
    *master*

 2. Criar Branch

    <pre> > git checkout -b **"nome do branch"**

 3. Para voltar branch *master*

    <pre> > git checkout master

**Merge e Rebase**

 

 - **Merge**
uni os branch e **cria um novo commit ** no branch atual. 

<pre> > git merge "nome branch que quer fazer o merge"</pre>

<pre>Merge made by the 'recursive' strategy.
 funcionalidades.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 funcionalidades.txt
c:\cursos\Code-Education\cursogit (master)
? git log
commit 0a991602725ab938052dd2338cf88dbaf7852d64 (HEAD -> master)
Merge: ced6aad e94632d
Author: Jairo Sousa <jaironsousa@gmail.com>
Date:   Thu Jul 20 08:06:06 2017 -0300
</pre>

 - **Rebase** 
uni os branch mais **organiza os commits na ordem que eles foram realizados e não cria o commit do merge**

<pre> > git rebase "nome branch que quer fazer o rebase"</pre>

<pre> First, rewinding head to replay your work on top of it...
Applying: Adicionando o arquivo texto4.txt
**Ele acabou de re ordenar a Head (Cabeça) do branh atual**
</pre>

<pre> > git log

Verifique que os commits foram organizados pela oredem e não foi criado um novo commit

