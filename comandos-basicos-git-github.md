# Comandos Básicos de GIT
# GIT

## Ajuda

	git help

##### Comando específico
	git help add
	git help commit
	git help <qualquer_comando_git>

## Configuração

### Geral

As configurações do GIT são armazenadas no arquivo **.gitconfig** localizado dentro do diretório do usuário do Sistema Operacional (Ex.: Windows: C:\Users\Documents and Settings\Rafael.

As configurações realizadas através dos comandos abaixo serão incluídas no arquivo/diretório citado acima.

##### Setar usuário
	git config --global user.name "Rafael"

##### Setar email
	git config --global user.email Rafael@gmail.com.br

##### Setar editor
	git config --global core.editor vim

##### Setar ferramenta de merge
	git config --global merge.tool vimdiff

##### Setar arquivos a serem ignorados
	git config --global core.excludesfile ~/.gitignore

##### Listar configurações
	git config --list

## Repositório Local

### Criar novo repositório

	git init

### Verificar estado dos arquivos/diretórios

	git status

### Adicionar arquivo/diretório

##### Adicionar um arquivo em específico

	git add meu_arquivo.txt

##### Adicionar um diretório em específico

	git add meu_diretorio

##### Adicionar todos os arquivos/diretórios

	git add .	

##### Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)

	git add -f arquivo_no_gitignore.txt

### Comitar arquivo/diretório

##### Comitar um arquivo

	git commit meu_arquivo.txt

##### Comitar vários arquivos

	git commit meu_arquivo.txt meu_outro_arquivo.txt

##### Comitar informando mensagem

	git commit meuarquivo.txt -m "minha mensagem"

### Remover arquivo/diretório

##### Remover arquivo

	git rm meu_arquivo.txt

##### Remover diretório

	git rm -r diretorio

### Visualizar histórico

##### Exibir histórico

	git log

##### Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))

	git log --stat

## Repositório Remoto

### Exibir os repositórios remotos

	git remote
	
	git remote -v

### Vincular repositório local com um repositório remoto

	git remote add origin github.com/BLIMKE/desafio-git-github.git

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


​	
### Clonar um repositório remoto já existente

	git clone https://github.com/BLIMKE/desafio-git-github.git

### Reescrevendo o histórico

##### Alterando mensagens de commit

	git commit --amend -m "Minha nova mensagem"

##### Alterar últimos commits
Alterando os três últimos commits

	git rebase -i HEAD~3

O editor de texto será aberto com as linhas representando os três últimos commits.

	pick f7f3f6d changed my name a bit
	pick 310154e updated README formatting and added blame
	pick a5f4a0d added catfile

Altere para edit os commits que deseja realizar alterações.

	edit f7f3f6d changed my name a bit
	pick 310154e updated README formatting and added blame
	pick a5f4a0d added catfile

Feche o editor de texto.

Digite o comando para alterar a mensagem do commit que foi marcado como *edit*.

	git commit –amend -m “Nova mensagem”

Aplique a alteração

	git rebase --continue

**Atenção:** É possível alterar a ordem dos commits ou remover um commit apenas
mudando as linhas ou removendo.
	
##### Remover todo histórico de um arquivo

	git filter-branch --tree-filter 'rm -f passwords.txt' HEAD 	

# Contribuições

Sinta-se a vontade para  adicionar mais informações.
