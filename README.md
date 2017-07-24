Bem Vindo ao Curso de Git!
======================

#PRIMEIROS PASSOS

*Verificar se GIT est� instalado*

    > git

**<i class="icon-asterisk"> PREPARANDO O AMBIENTE**
> - Criar reposit�rio (pasta que vai guardar todos os arquivos do projeto)
> - mkdir aulagit (cria pasta onde vai ficar arquivos do projeto)
> - cd aulagit (acessar a pasta)

    > git init (cria diret�rio .git )

**<i class="icon-asterisk"> Agora j� tem diret�rio configurado pelo Git**
> - criar arquivo qualquer um ".txt" no diret�rio "auldagit" e digite qualquer coisa no arquivo.

**Ajuda! :+1:**
Criar arquivos pelo CMD ou Bash

    > copy NUL arquivo-novobranch.php(cmd)
    > touch arquivo-novobranch.php (bach)

Para edit�-los podem usar bloco de notas.

#OS TR�S EST�GIOS DE UM COMMIT

>1 - Untracked

O arquivo est� no diret�rio mas n�o est� no Git 

    >git status

verifica o est�gios dos arquivos

>2 - Changes to be commiterd

Quando o arquivo � adicionado e come�a a fazer parte de um controle de vers�o.

    > git add <<nome do arquivo>> 
    > git add .

Agora o arquivo est� pronto para entrar no controle de vers�o.

>3 - Unstage

quando o arquivo passa para o controle de vers�o ou seja � dado o commit.

**Commit**

    > git commit -m �meu primeiro commit�  

onde o **"-m"** � para colocar uma mensagem.

    > git log 

verifica os commit's dados

    > git log -p 

verifica em cada arquivo comitado o que foi mudado.

    > git log -p -2 

(2 � um �ndice que indica os �ltimos arquivos comitado) => verifica nos dois �ltimos arquivo comitados o que foi mudado.

    > git log --stat

mostra o git log e mais as estat�sticas de todos os commits

    > git log --pretty=oneline

Mostra todos os commits em uma linha s�.

    > git log --pretty=format:"%h - %an, %ar : %s"

Mostra o in�cio do Rest, quem commitou, quanto tempo atr�s, e a descri��o do commit.

    > git log --since=2.days

Mostra os logs de todos os commits feitos nos �ltimos dias (no exemplo foi pedido 2 dias).

#FLUXO E VERS�ES

**Desfazendo o ADD**
Quando voc� esta no segundo estagio e quer voltar para o primeiro, ou seja, tirar o arquivo de condi��es de ser commitado.

    >git reset HEAD <<nome do arquivo>>

**Voltando  vers�es**

Voc� desja desfazer um commit dado.

* primeiro verificar o ID do commit a ser desfeito, voc� pode verificar com o comando:

     <pre>> git log

*commit* *f724b698a2c6ae3db03cd5c2ad86d0b4af8c32dd* <=**Este � ID**
Author: Jairo Sousa <jaironsousa@gmail.com>
Date:   Wed Jul 19 21:56:56 2017 -0300*

    > git checkout f724b698a2c6ae3db03cd5c2ad86d0b4af8c32dd

