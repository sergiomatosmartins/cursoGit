# cursoGit
cursoGit

Bem vindo ao meu primeiro repositório GIT Hub

Objetivo => Colocar em no arquivo README, as principais instruções utilizadas para conseguir fazer o push.
Segue as anotações dos comandos testados e seus resultados desde a criação do meu repositório local, até a realização de ter obtido exito de envio para o repositório remoto:

Criando um repositório  
$ mkdir cursoGit

Movimentando para o repositório
$ cd cursoGit

Iniciando git 
$ git init
Initialized empty Git repository in C:/Program Files/Git/cursoGit/.git/

Mostrando pastas ocultas 
$ ls -la
total 8
drwxr-xr-x 1 sergio 1049089 0 mai 25 10:55 ./
drwxr-xr-x 1 sergio 1049089 0 mai 25 10:52 ../
drwxr-xr-x 1 sergio 1049089 0 mai 25 10:55 .git/

Verificando Status 
$ git status
On branch master
Initial commit
nothing to commit (create/copy files and use "git add" to track)

Criando um arquivo  cursoGit.txt
$ vi cursoGit.txt
$ dir -l
total 1
-rw-r--r-- 1 sergio 1049089 22 mai 25 11:05 cursoGit.txt

Primeiro estagio git  -  Untracket

$ git status
On branch master
Initial commit
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        cursoGit.txt

nothing added to commit but untracked files present (use "git add" to track)


segundo estagio git  - warning 

$ git add cursoGit.txt
warning: LF will be replaced by CRLF in cursoGit.txt.
The file will have its original line endings in your working directory.
•	Arquivo esta preparado para commitd
$ git status

On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   cursoGit.txt

Terceiro estagio git – commit
$ git commit -m "Meu primeiro commit"
The file will have its original line endings in your working directory.
 1 file changed, 2 insertions(+)
 create mode 100644 cursoGit.txt

$ git status
On branch master
nothing to commit, working directory clean

$ git log
commit a13b8d4a1cb3b3bd3e63be18b6ce09a31d602964
Author: Sergio Martins <sergio@crea-sc.org.br>
Date:   Wed May 25 11:22:15 2016 -0300

    Meu primeiro commit

Alterando o arquivo cursoGit.txt, verificando status e executando as 3 fases git
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   cursoGit.txt

no changes added to commit (use "git add" and/or "git commit -a")

$ git log
commit 9fdcf3b8988d1b9da7fa030dce55c421d7b71d9c
Author: Sergio Matos Martins <sergiomatosmartins@gmail.com>
Date:   Wed May 25 11:44:32 2016 -0300

    segunda versão

commit a13b8d4a1cb3b3bd3e63be18b6ce09a31d602964
Author: Sergio Martins <sergio@crea-sc.org.br>
Date:   Wed May 25 11:22:15 2016 -0300

    Meu primeiro commit

Voltando estagio commit anterior

$ git reset HEAD cursoGit.txt
warning: LF will be replaced by CRLF in cursoGit.txt.
The file will have its original line endings in your working directory.
Unstaged changes after reset:
M       cursoGit.txt

$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   cursoGit.txt

no changes added to commit (use "git add" and/or "git commit -a")

BRANCH
Verificando em que branch estou:
$ git branch
* máster

Criando um branch
$ git checkout -b funcionalidade1
Switched to a new branch 'funcionalidade1'

sergio@DTI-SERGIO MINGW64 /cursoGit (funcionalidade1)

sergio@DTI-SERGIO MINGW64 /cursoGit (funcionalidade1)
$ dir
cursoGit.txt
obs: cria com o mesmo conteúdo do anterior

Criei um segundo arquivo e fiz gerei nova versão

Voltando ao branch anterior. (máster);
$ git checkout master
Switched to branch 'master'
Obs: O conteúdo de versões são diferentes

Pegando a partir do máster os commits de funcionalidade 1

$ git merge funcionalidade1
Updating d88ede1..41ed02c
Fast-forward
 cursoGit2.txt | 2 ++
 1 file changed, 2 insertions(+)
 create mode 100644 cursoGit2.txt

obs: Merge gera um commit para unificação 

Como remover o último commit gerado por MERGE

$ git reset HEAD~1 --hard
HEAD is now at d88ede1 terceiro commit



Unificando os commit, reorganizando sem gerar um novo commit

$ git rebase funcionalidade1
First, rewinding head to replay your work on top of it...
Fast-forwarded master to funcionalidade1.

Removendo um Branch
$ git branch
  funcionalidade1
  funcionalide2
* master

sergio@DTI-SERGIO MINGW64 /cursoGit (master)
$ git branch -d  funcionalide2
Deleted branch funcionalide2 (was 41ed02c).

Configuração GitHub
Criando chave pública
PUCH – Empurrando os arquivos para o repositório remoto
1 Passo – Detalhando a situação do meu repositório
Quanto aos Branch:
$ git branch
* funcionalidade1
 	 master
Formado por dois branch, máster e funcionalidade1;
Conteúdo Branch:
MASTER = > cursoGit.txt  cursoGit2.txt :
FUNCIONALIDADE1 = >  cursoGit.txt  cursoGit2.txt

2 Passo – Comando Push

	Após configurar ou identificar repositório remoto:
	- Subir os arquivos do Branch MASTER:

$ git push origin master

Username for 'https://github.com': sergiomatosmartins
Counting objects: 12, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (6/6), done.
Writing objects: 100% (12/12), 1.01 KiB | 0 bytes/s, done.
Total 12 (delta 0), reused 0 (delta 0)
To https://github.com/sergiomatosmartins/cursoGit.git
 * [new branch]      master -> master
 
	Para identificar a existência de outros branch (opcional)

	Ir para o branch desejado

$ git checkout funcionalidade1
Switched to branch 'funcionalidade1'

              Empurrar arquivos novo branch 

$ git push origin funcionalidade1
Username for 'https://github.com': sergiomatosmartins
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/sergiomatosmartins/cursoGit.git
 * [new branch]      funcionalidade1 -> funcionalidade1

3 Passo – Testando 
$ git branch -a

* funcionalidade1
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/funcionalidade1
  remotes/origin/master

4 Passo – Verificar se todos os arquivos estão atualizados

              $ git pull


Conclusão:
 
	Destacando a importância da ferramenta, posso concluir que o desafio e domina-la  com bastante exercício diário:

Abraços

Sergio Martins 
