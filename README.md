# Comandos Básicos Git

## Chave SSH e documentação Git
 
 [Gerar nova chave ssh](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

 ## Criando o Primeiro Repósitorio

 ```console
 > git init PrimeiroRepo
```

* Será criado o diretorio configurado como repositorio **GIT**.

* Todas as configurações do repositorio ficam na pasta _.git_

* Crie um arquivo, edite e adicione ao repositorio:
 ```console
 > gedit PrimeiroArquivo

 > git add PrimeiroArquivo

 > git commit -m "Criado o primeiro arquivo."
 ```

 # Configurando

 * Configure seu nome e e-mail:
 ```console
 > git config --global user.name "Meu user Name"

 > git config --global user.email "meuemail@email.com"
 ```

 > o comando _--global_ configura localmente o usuario e email para todos os projetos Git criado em sua máquina se não colocar o _--global_ ele cria para apenas o projeto especidico.

 ## Editor View

 * editor padrão do git para editar mensagem commit

 INSERÇÃO :

 SAIR E SALVAR :WQ

 ## Git Status e Log

 * Comando para ver o status do repositório
```console
> git statua
```

* Ver último commits no repositório
```console
> git log
```

## Criar um repositório remoto

* Crie um repositorio no GitHub.

* Configure o repositório remoto.

* Crie um arquivo README.md

* Faça o upload das alterações.

```console
> git remote add origin <url>
```
* Comando para listar os remotes

```console
> git remote -v
```

## Git Add
```console
> git add <lista de arquivos>
```
* Adiciona os arquivos novos e modificados para o próximo commit.
```console
> git add .
```

## Git Commit

```console
> git commit [-m "menssage"]
```
* Registra o commit com todos os arquivos que usou _git add_

* Se o parâmetro de mensagem não for passado abrirá um editor de texto para escrever a mensagem.
```console
> git config --global core.editor gedit
```

## Git Push

* Envia alterações (commits) de uma branch para repositório remoto.

* A primeira vez:

```console
> git push -u origin master
```
* O envio é rejeitado se o repositório não estiver sincronizado.

```console
> git push <remote> <branch>
```
* Sincronizar a branch para repositorio remoto
```console
> git push --set-upstream origin master
```
* No proximo commit poderá utilizar somento o _git push_
```console
> git push
```

## Git Workflow

* Basicamente a maior parte do trabalho com o _git_ consiste nestas tarefas:

  - Editar
  - Commitar
  - Sincronizar com o repositório remoto

* Exercite estes comandos!  

## Status dos Arquivos

* Edite o arquivo criado anteriormenrte.

* Crie um novo arquivo e veja o seu status no repositorio

## Estados dos Arquivos

* Não monitorado (untracked)

    - Quando agente cria algum arquivo

* Modificado (modified)
    - Quando modifica um arquivo que já esteja no repositório.

* Preparado (staged)
    - Quando executamos o comando _git add ._

* Consolidado (commited)
    - Quando executamos o comando _git commit_

![imagem 01](img01.png)    

## Diff
* Exibe diferenças entre commits e branchs
```console
> git diff
```
* Deferença no diretório
```console
> git diff [path]
```
* Mostra o que foi alterado no último commit.
```console
> git diff HEAD~1
```
* Ver diff no GitHub

# Git Clone
* Baixa o repositório remoto.
* Outra forma de criar um repositório local.

* Já vem com o remoto configurado.
```console
> git clone <URL>
```

# Git Pull

* Baixa as alterações do repositorio remoto.

* Mantém o repositorio sincronizados com os últimos commits de uma branch.
```console
> git pull
```

## Navegar no Histórico

* Permite ver como um arquivo ou todo o repositorio estava em um determinado commit.
```console
> git checkout <commit> <file>
```

## Git Checkout
* Altera o repositório para o estado daquele commit.

* Útil para fazer testes antes e depois de alterações.
```console
> git checkout <commit>
```

* Para voltar o repositório no último commit.
```console
> git checkout master
```

## Desfazendo Alterações

* Irá desfazer todas as alterações que não estejam no Stage desde o último commit.
```console
> git checkout -- <path_or_file>
```

* Desfazer as alterações desde o último commit incluíndo o Stage.
```console
> git checkout HEAD  -- <path_file>
```

* Descartar as mudanças do arquivo
```console
> git checkout -- <name_of_file>
```

* Descarta todas as modificações de todos asquivos modificados.
```console
> git checkout -- .
```

* Descarta as modificações mesmo depois do _git add_
```console
> git checkout HEAD  -- <name_ile>
```

## Git Revert

* Irá criar um novo commit que desfaz as alterações do commit especificado.

* Útil para desfazer um commit antigo
```console
> git revert <commit>
```

## Git Reset

* Resetar o repositório para um determinado commit.
```console
> git reset <commit>
```

* Resetar e remover todas as alterações.
  - Cuidado ao usar! Não usar se já estiver publicado.

* Útil para desfazer últimos commits.  
```console
> git reset --hard <commit>

> git reset HEAD~1 // remove o ultimo commit, mas fica em stats os arquivos modificados permanecem

> git reset HEAD~1 --hard // remove o ultimo commit, e as modificações.
```