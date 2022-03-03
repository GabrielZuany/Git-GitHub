# Git: Comandos básicos

### Setar usuário
	git config --global user.name "GabrielZuany"
  
### Ignorar arquivos

	touch .gitignore
  
### Criar novo repositório

	git init
  
### Verificar estado dos arquivos/diretórios

	git status

### Adicionar arquivo/diretório (staged area)

##### Adicionar um arquivo em específico

	git add meu_arquivo.txt

##### Adicionar um diretório em específico

	git add meu_diretorio

##### Adicionar todos os arquivos/diretórios
	
	git add .
### Comitar arquivo/diretório

##### Comitar um arquivo
	
	git commit meu_arquivo.txt

##### Comitar vários arquivos

	git commit meu_arquivo.txt meu_outro_arquivo.txt
	
##### Comitar informando mensagem

	git commit meuarquivo.txt -m "minha mensagem de commit"

### Remover arquivo/diretório

##### Remover arquivo

	git rm meu_arquivo.txt

##### Remover diretório

	git rm -r diretorio
  
 ##### Apagar branch

	git branch -d branch 
  
 ### Visualizar histórico

##### Exibir histórico
	
	git log
  
  ##### Exibir versões anteriores do código
	
	git log
  
  ##### Volta nas versões anteriores do código
	
	git reset --hard id(codigo da branch desejada)
  
  ## Repositório Remoto

### Exibir os repositórios remotos

	git remote
	
	git remote -v

### Vincular repositório local com um repositório remoto

	git remote add origin git@github.com:user/diretorio.git
	
### Exibir informações dos repositórios remotos

	git remote show origin
	
### Renomear um repositório remoto 

	git remote rename origin curso-git
	
### Desvincular um repositório remoto
	
	git remote rm curso-git

### Enviar arquivos/diretórios para o repositório remoto

O primeiro **push** de um repositório deve conter o nome do repositório remoto e o branch.

	git push -u origin master
	
Os demais **pushes** não precisam dessa informação

	git push
	

### Atualizar repositório local de acordo com o repositório remoto

##### Atualizar os arquivos no branch atual

	git pull
	
##### Buscar as alterações, mas não aplica-las no branch atual

	git fetch
	
### Clonar um repositório remoto já existente

	git clone git@github.com:user/repositorio.git
### Branches

O **master** é o branch principal do GIT.

O **HEAD** é um ponteiro *especial* que indica qual é o branch atual. Por padrão, o **HEAD** aponta para o branch principal, o **master**.

##### Criando um novo branch

	git branch nome-da-branch
	
##### Trocando para um branch existente

	git checkout nome-da-branch
	
Neste caso, o ponteiro principal **HEAD** esta apontando para o branch chamado nome-da-branch
	
##### Voltar para o branch principal (master)

	git checkout master
	
##### Resolver merge entre os branches

	git merge nome-da-branch
	
Para realizar o *merge*, é necessário estar no branch que deverá receber as alterações.
O *merge* pode automático ou manual.
O merge automático será feito em arquivos textos que não sofreram alterações nas mesmas linhas, já o merge manual será feito em arquivos textos que sofreram alterações nas mesmas linhas.
A mensagem indicando um *merge* manual será:

	Automerging meu_arquivo.txt
	CONFLICT (content): Merge conflict in meu_arquivo.txt
	Automatic merge failed; fix conflicts and then commit the result.
  
  ##### Apagando um branch

	git branch -d nome-da-branch

##### Listar branches 

###### Listar branches

	git branch

###### Listar branches com informações dos últimos commits

	git branch -v

###### Listar branches que já foram fundidos (merged) com o **master**

	git branch --merged

###### Listar branches que não foram fundidos (merged) com o **master**

	git branch --no-merged
