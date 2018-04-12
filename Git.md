### AJUDA

##### GERAL
	git help
	
##### COMANDO ESPECÍFICO
	git help add
	git help commit
	git help <qualquer_comando_git>
	

## CONFIGURAÇÃO

### GERAL

As configurações do GIT são armazenadas no arquivo .gitconfig localizado dentro do diretório do usuário do Sistema Operacional
(Ex.: Windows: C:\Users\Documents and Settings\Vinicius ou *nix /home/Vinicius).

As configurações realizadas através dos comandos abaixo serão incluídas no arquivo citado acima.

##### SETAR USUÁRIO
	git config --global user.name "Vinicius Von Ahn"

##### SETAR EMAIL
	git config --global user.email viniciusvonahn@gmail.com
	
##### SETAR EDITOR
	git config --global core.editor vim
	
##### SETAR FERRAMENTA DE MERGE
	git config --global merge.tool vimdiff

##### SETAR ARQUIVOS A SEREM IGNORADOS
	git config --global core.excludesfile ~/.gitignore

##### LISTAR CONFIGURAÇÃO
	git config --list

##### IGNORAR ARQUIVOS

Os nomes de arquivos/diretórios ou extensões de arquivos listados no arquivo .gitignore não serão adicionados em um repositório. 
Existem dois arquivos .gitignore, são eles:

* Geral: Normalmente armazenado no diretório do usuário do Sistema Operacional. O arquivo que possui a lista dos arquivos/diretórios 
a serem ignorados por todos os repositórios deverá ser declarado conforme citado acima. O arquivo não precisa ter o nome de 
.gitignore.

* Por repositório: Deve ser armazenado no diretório do repositório e deve conter a lista dos arquivos/diretórios que devem ser ignorados
apenas para o repositório específico.

### REPOSITÓRIO LOCAL

### CRIAR NOVO REPOSITÓRIO

	git init

### VERIFICAR ESTADO DOS ARQUIVOS/DIRETÓRIOS

	git status

#### ADICIONAR ARQUIVO/DIRETÓRIO (STAGED AREA)

#### ADICIONAR UM ARQUIVO EM ESPECÍFICO

	git add meu_arquivo.txt

##### ADICIONAR UM DIRETÓRIO EM ESPECÍFICO

	git add meu_diretorio

##### ADICIONAR TODOS OS ARQUIVOS/DIRETÓRIOS
	
	git add .	
	
##### ADICIONAR UM ARQUIVO QUE ESTÁ LISTADO NO .GITIGNORE (GERAL OU DO REPOSITÓRIO)
	
	git add -f arquivo_no_gitignore.txt
	
##### COMITAR ARQUIVO/DIRETÓRIO

##### COMITAR UM ARQUIVO
	
	git commit meu_arquivo.txt

##### COMITAR VÁRIOS ARQUIVOS

	git commit meu_arquivo.txt meu_outro_arquivo.txt
	
##### COMITAR INFORMANDO MENSAGEM

	git commit meuarquivo.txt -m "minha mensagem de commit"

##### REMOVER ARQUIVO/DIRETÓRIO

##### REMOVER ARQUIVO

	git rm meu_arquivo.txt

##### REMOVER DIRETÓRIO

	git rm -r diretorio

##### VISUALIZAR HISTÓRICO

##### EXIBIR HISTÓRICO
	
	git log
	
##### EXIBIR HISTÓRICO COM DIFF DAS DUAS ÚLTIMAS ALTERAÇÕES

	git log -p -2
	
##### EXIBIR RESUMO DO HISTÓRICO (hash completa, autor, data, comentário e qtde de alterações (+/-))

	git log --stat
	
##### EXIBIR INFORMAÇÕES RESUMIDAS EM UMA LINHA (hash completa e comentário)

	git log --pretty=oneline
	
##### EXIBIR HISTÓRICO COM FORMATAÇÃO ESPECÍFICA (hash abreviada, autor, data e comentário)

	git log --pretty=format:"%h - %an, %ar : %s"
	
* %h: Abreviação do hash;
* %an: Nome do autor;
* %ar: Data;
* %s: Comentário.

Mais opções de formatação no [Git Book](http://git-scm.com/book/en/Git-Basics-Viewing-the-Commit-History)

##### EXIBIR HISTÓRICO DE UM ARQUIVO ESPECÍFICO

	git log -- <caminho_do_arquivo>

##### EXIBIR HISTÓRICO DE UM ARQUIVO ESPECÍFICO QUE CONTÉM UMA DETERMINADA PALAVRA

	git log --summary -S<palavra> [<caminho_do_arquivo>]

##### EXIBIR HISTÓRICO MODIFICAÇÃO DE UM ARQUIVO

	git log --diff-filter=M -- <caminho_do_arquivo>

* O <M> pode ser substituido por: Adicionado (A), Copiado (C), Apagado (D), Modificado (M), Renomeado (R), entre outros.

##### EXIBIR HISTÓRICO DE UM DETERMINADO AUTOR

	git log --author=usuario

##### EXIBIR REVISÃO E AUTOR DA ÚLTIMA MODIFICAÇÃO DE UM BLOCO DE LINHAS

	git blame -L 12,22 meu_arquivo.txt 

##### DESFAZENDO OPERAÇÕES

##### DESFAZENDO ALTERAÇÃO LOCAL (working directory)
Este comando deve ser utilizando enquanto o arquivo não foi adicionado na staged area. 

	git checkout -- meu_arquivo.txt

##### DESFAZENDO ALTERAÇÃO LOCAL (staging area)
Este comando deve ser utilizando quando o arquivo já foi adicionado na staged area.

	git reset HEAD meu_arquivo.txt

Se o resultado abaixo for exibido, o comando reset não alterou o diretório de trabalho. 

	Unstaged changes after reset:
	M	meu_arquivo.txt

A alteração do diretório pode ser realizada através do comando abaixo:
	
	git checkout meu_arquivo.txt

### REPOSITÓRIO REMOTO

### EXIBIR OS REPOSITÓRIOS REMOTOS

	git remote
	
	git remote -v

### VINCULAR REPOSITÓRIO LOCAL COM UM REPOSITÓRIO REMOTO

	git remote add origin git@github.com:ViniciusVonAhn/projeto-git.git
	
### EXIBIR INFORMAÇÕES DOS REPOSITÓRIOS REMOTOS

	git remote show origin
	
### RENOMEAR UM REPOSITÓRIO REMOTO 

	git remote rename origin projeto-git
	
### DESVINCULAR UM REPOSITÓRIO REMOTO
	
	git remote rm projeto-git

### ENVIAR ARQUIVOS/DIRETÓRIOS PARA O REPOSITÓRIO REMOTO

O primeiro push de um repositório deve conter o nome do repositório remoto e o branch.

	git push -u origin master
	
Os demais pushes não precisam dessa informação

	git push
	

##### ATUALIZAR REPOSITÓRIO LOCAL DE ACORDO COM O REPOSITÓRIO REMOTO

##### ATUALIZAR OS ARQUIVOS NO BRANCH ATUAL

	git pull
	
##### BUSCAR AS ALTERAÇÕES, MAS NÃO APLICA-LAS NO BRANCH ATUAL

	git fecth
	
### CLONAR UM REPOSITÓRIO REMOTO JÁ EXISTENTE

	git clone git@github.com:ViniciusVonAhn/texugo.git
