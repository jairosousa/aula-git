# **Bem Vindo ao Curso de Git!**

## PRIMEIROS PASSOS
*Verificar se GIT está instalado*

```
> git
```
    
## PREPARANDO O AMBIENTE
> - Criar repositório (pasta que vai guardar todos os arquivos do projeto)
> - mkdir aulagit (cria pasta onde vai ficar arquivos do projeto)
> - cd aulagit (acessar a pasta)

## INCIALIZANDO OU CRIAR DIRETÓRIO _GIT_
    
```
> git init // Cria diretório .git
```

_criar arquivo qualquer um ".txt" no diretório "auldagit" e digite qualquer coisa no arquivo._

**Ajuda! :+1:**

**Criar arquivos pelo CMD ou Bash**

 > copy NUL arquivo-novobranch.php(cmd)
 > touch arquivo-novobranch.php (bach)

*Para editá-los podem usar **bloco de notas**.*

## **OS TRÊS ESTÁGIOS DE UM COMMIT**

** 1 - Untracked**
*O arquivo está no diretório mas não está no Git *

```
> git status
> git diff <<nome do arquivo>> // Verifica as diferenças do arquivo
```
*verifica o estágios dos arquivos*

## 2 - Changes to be commiterd

*Quando o arquivo é adicionado e começa a fazer parte de um controle de versão.*

```
> git add <<nome do arquivo>> 
> git add . // Adiciona todos os arquivos 
```
*Agora o arquivo está pronto para entrar no controle de versão.*

## 3 - Unstage

*Quando o arquivo passa para o controle de versão ou seja é dado o commit.


## Commit

```
> git commit -m “meu primeiro commit”  
```
*onde o **"-m"** é para colocar uma mensagem.*

## 1 - Verifica os commit's dados

```
> git log 
```

## 2 - Verifica em cada arquivo comitado o que foi mudado.

```
    > git log -p 
```

## 3 - Verifica nos dois últimos arquivo comitados o que foi mudado.

```
    > git log -p -2 
```
*2 é um índice que indica os últimos arquivos comitado*

## 4 - Mostra o git log e mais as estatísticas de todos os commits

```
> git log --stat
```

## 5 - Mostra todos os commits em uma linha só.

```
> git log --pretty=oneline
```

## 6 - Mostra o início do Rest, quem commitou, quanto tempo atrás, e a descrição do commit.
```
> git log --pretty=format:"%h - %an, %ar : %s"
```

## 7 - Mostra os logs de todos os commits feitos nos últimos dias .

```
> git log --since=2.days
```
*(no exemplo foi pedido 2 dias)*

## 8 Renomear um commit
```bash
> git commit -m "Nova mensagem que vai substituir a anterior" --amend
```

## FLUXO E VERSÕES

## 1. Desfazendo o ADD

*Quando você esta no segundo estagio e quer voltar para o primeiro, ou seja, tirar o arquivo de condições de ser commitado.*

```
> git reset HEAD <<nome do arquivo>>
```

## 2. Voltando versões

*Você deseja desfazer um commit dado.*

## 2.1 Primeiro verificar o ID do commit a ser desfeito, você pode verificar com o comando:

<pre> > git log *(deve pegar o ID da versão que voce quer voltar)*
    *commit* *f724b698a2c6ae3db03cd5c2ad86d0b4af8c32dd* <=**Este é ID**
    Author: Jairo Sousa <jaironsousa@gmail.com>
    Date:   Wed Jul 19 21:56:56 2017 -0300*
</pre>

```
    > git checkout f724b698a2c6ae3db03cd5c2ad86d0b4af8c32dd.
```

## 3. Voltando ao estado original

*Vamos imaginar que você possui um arquivo no controle de versão chamado exemplo.php.*

*Imagine agora que você fez diversas alterações nesse arquivo, porém, por qualquer motivo, você se arrependeu de fazê-las (lembrando     que você apenas fez as alterações, mas não as commitou).*

## Para você fazer o conteúdo do arquivo voltar ao estado original, digite:

```
> git checkout -- exemplo.php </pre>
```
*Rodando esse comando, todos as alterações realizadas serão perdidas e o arquivo voltará exatamente como estava antes.*
*Esse recurso é extremamente útil, porém deve ser usado com cuidado*

## BRANCHES

## 1. Entendendo os Branches

*Um desenvolvimento de software possui um linha do tempo principal **“master”** e os **branches** são ramificações dessa linha do    tempo que pode ser criando pedaços do software sem alterar a linha do tempo principal, existe também branches de branches.*

![imagem01](/img/img-01.PNG)

## 2. Criando o primeiro Branch

## 2.1. Verifica qual **branch** você está

```
  > git branch  // Exemplo master</pre>
```

## 2.2. Criar Branch

```
  > git checkout -b <<"nome do branch">> 
```

## 2.3. Para voltar branch *master*

```
 > git checkout master
```

## 3. Merge e Rebase

## 3.1. Merge

*Uni os branch e **cria um novo commit** no branch atual. *

```
 > git merge <<"nome branch">> que quer fazer o **merge**
```
<code><strong>console:<strong></code>
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

## 3.2. Rebase 
*Uni os branch mais **organiza os commits na ordem que eles foram realizados e não cria o commit do merge** *

```
 > git rebase <<"nome branch que quer fazer o rebase">>

*First, rewinding head to replay your work on top of it...
Applying: Adicionando o arquivo texto4.txt
**Ele acabou de re ordenar a Head (Cabeça) do branh atual**
```
### Verifique que os commits foram organizados pela ordem e não foi criado um novo commit

```
> git log
```

## 4. Removendo um branch

*Após uma funcionalidade ser desenvolvida e o merge realizado, você poderá optar por remover o branch. É isso mesmo =)*

*Remover um branch não significa que você removerá os commits que você realizou, pois o merge já foi feito.*

## 4.1 Para remover um branch

```
> git branch -D "nome-do-branch"
````
### *Teste isso agora mesmo em seu computador!*

# GITHUB

*É um serviço online de repositórios **Git** *

## Primeiro configurar o repositório remoto para **Git** saber para onde mandar os arquivos.
 
```
> git remote add origin https://github.com/jairosousa/aula-git.git
```

## Caso apareça erro de histories usar o comando

```
> git merge origin master --allow-unrelated-histories
```
### Pode ver as configurações no arquivo **.git/config**

### Agora você pode enviar seu arquivos locais para o remoto

```
> git push origin master
```

## Push em outra Branch

## 1. Verifique os branch's repositorio local

```
> git brunch
```
        
## 2. Verifique todos as branch's local e remoto

```
> git brunch -a
```

## 3. Mudar Entre as branch 

```
> git checkout "nome-branch"
```

## 4. Push para branch especifica
```
> git push origin "nome-branch"
```

<code><strong>console:<strong></code>
```
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 305 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/jairosousa/aula-git.git
* [new branch]      funcionalidade1 -> funcionalidade1
```

## Clonando
   *Fazer cópia do repositório em outra pasta ou máquina.*

```
> git clone https://github.com/jairosousa/aula-git.git
```
### Nesse caso foi clonado da branch **master**

## Para baixar o outro **branch** , primeiro verifique os branch no remoto.

```
> git branch -a
```

<code><strong>console:<strong></code>
```
*\*master*
*remotes/origin/funcionalidade1*
*remotes/origin/master*
 ```

## Você tem criar no seu remoto uma **branch** com o mesmo nome e coloque a referencia remoto depois

```
> git checkout -b <<"nome-branch-local">> origin/"nome-branch-remoto"
```

## Para verificar se todos os arquivos estão sincronizados:

```
> git pull
```

## Push e Pull com o novo branch

*Vamos simular dois usuário utilizando o repositório*
*Clonar o repositório em outra pasta exemplo aulagit-clone*
 
```
> git clone https://github.com/jairosousa/aula-git.git
```

## No primeiro repositório faça alteração em arquivo exemplo arquivo.txt e depois fazer um **pull** para repositório remoto.


### **NOTA**: use o branch _**master**_
 
## *Faça os procedimentos para enviar para o repositório remoto*

## No outro repositório (Clone) baixe as alterações feitas.

   _~/Documents/Cursos/Code-Education/Git/aulagit-clone (master)_

```
   > git **pull** origin master
```

## Agora vamos criar um novo **branch** no mesmo repositório.

```
> git checkout -b novoBranch
```
<code><strong>console:<strong></code>
   _Switched to a new branch 'novoBranch'+

Vamos criar novo arquivo nesse **branch**

```
> git status
```

```
> git add "arquivo-novobranch.txt"
```

```
> git commit -m "Adicionar arquivo - exemplo de novo branch"

```

Agora enviar para o repositório remoto

```
>git **push** origin novoBranch

```
   **[new branch]      novoBranch -> novoBranch*

   Agora no repositório original
   _~/Documents/Cursos/Code-Education/Git/aulagit (**master**)_

 ### Verifique os branch

```
> git branch
> master
```

## Se verificar os branch remotos 

```
> git branch -a    
```
                
### Observe que não apareceu ainda o novoBranch
### Para atualizar:

```
> git fatch
```

## Agora para ter acesso a esse __branch__ _(__Nota:__ lembre-se que você está no repositório local inicial no branch master)._ Crie um branch local com mesmo nome do remoto

```
> git checkout -b novoBranch origin/novoBranch
```
<code><strong>console:<strong></code>
    
**Branch novoBranch set up to track remote branch novoBranch from origin.**
**Switched to a new branch 'novoBranch'**

### Passa acessar esse nova branch
**~/Documents/Cursos/Code-Education/Git/aulagit(**novoBranch**)$**

### Removendo branch remoto
_**Dica para você!**_

   > Quando um branch local é removido, isso não significa que o branch remoto também será.
   > Nesse caso, há um comando específico para que possamos remover um ***branch*** remoto. Utilize o comando:
            
 ```
 > git branch -m old_branch new_branch         // Renomeia branch localmente    
 > git push origin :old_branch                 // Delete a old branch    
 > git push --set-upstream origin new_branch   // Push the new branch, set local branch to track the new remote

 ```

 **Não se esqueça de testar. Ok?**
 
 
# PULL REQUEST (Travis)

## 1 - Criar nova branch no repositorio a partir da master

```
> git push origin master:travis-test
```

## 2 - Mudar para nova branch

```
> git checkout travis-test
```

## 3 - Faça alterações no projeto

## 4 - Commit para nova branch

```
> git push origin nova-branch
``` 

## 5 - No repositorio remoto acesse a nova branch e click em new pull-request

## 6 - Escreva uma descrição da alteração e click em create pull request

## 7 - Após os teste no travis e estiver tudo ok, faça o **merge request** com o master click em Merge pull request

## Git Tag

* Útil para definir versões estáveis do projeto.
* Semelhante a Branch porém não recebe mais commits.
* Guarda um estado do repositório.
```
git tag [nome da tag]
```
```
git push <remote> <tag>
```
<remote> geralmente é igual ao `origin`

### Como baixar a versão de uma TAG

1. Faça checkout para tag
```
git checkout <tag>
```

2. Depois crie nova branch a partie da Tag
```
git checkout -b <nome-nova-branch>
```

## Fork

* Copia um repositório de outro usuário para o seu usuário no Github.
* É assim que começa a contribuição para outros projetos
* Você teria uma cópia independente do repositório original, podendo fazer quaisquer alterações.

## Issues

* Tradução: **Questões**.
* reportar bugs.
* Organizar tarefas a serem feitas.
* Permitir discursões entre os usuário.
* Pode ser referenciado por commits
  * Pode ser fechada acrescentando o comando na descrição do commit: `"Closes #3"`
  
## Pull Request

* O grande simbolo de colaboração.
* É quando você solicita que sua alterações sejam unidas a uma branch no mesmo repositório ou um repositório que sofreu o **fork**.
* Igual uma **Issue** porém com uma branch associada.
* Muito útil para o trabalho coloborativo.
    
### Links para ajudar nos recursos
[Understanding the GitHub flow](https://guides.github.com/introduction/flow/)

** Gitignore

* Configura arquivos que devem ser ignorados
* Contem arquivos, caminhos e pattherns

>
>.project
>
>node_modules/
>
>bower_components/
>
>**/*.css
>

## Git Commit Amend

```
git commit --amend
```

* Altera o último commit.
  * Mensagem de commit.
  * Adiciona arquivos
  
## Git Stash

```
git stash
```
* Guarda as alterações do *Working Directory*.
* Permite fazer rebase, merge, trocar de branch sem necessidade de fazer um commit.

### Lista os Stash
```
git stash list
```

### Aplica o ultimo Stash armazenado
```
git stash pop
```

## Git Brame

```
git brame <nome arquivo>
```

* Mostra as alterações feitas em um arquivo por linha.
* Mostra o autor e o commit que foi feito aquela linha.
* Útil para verificar quando as alterações foram feitas, por que e por quem.

<br/>
<br/>
<br/>
<br/>

*Create By:* ***Jairo Nascimento***

