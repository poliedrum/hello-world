# hello-world

Repositorio para aprendizagem da ferramenta GIT com foco no Github.com <img src="https://github.com/poliedrum/hello-world/blob/master/git.png?raw=true" width="32" height="32">

Imagem via MarkDown com endereço relativo:
![Github](git.png?raw=true&s=10 "Git")

Este é apenas um repositório de teste, cujo objetivo é permitir a aprendizagem das ferramentas gits, e servir como 
material de apoio em futuros estudos.

## Passos executados

Após instalar o aplicativo GIT (git-scm.com) em meu desktop windows, utilizei os seguintes comandos a seguir para criar um repositorio local e depois replicar no repositorio remoto do [github](https://github.com/).

```
mkdir testegit            # creando diretorio que será o repositorio local
cd testegit               # tornando este dir. o diretorio corrente
touch a.txt               # criando um arquivo para verificar sincronização remota

git config --global user.name "Nome Usuario"     # configura o nome do usuario para todos
                                                 # projetos deste usuario devido ao flag
                                                 # --global. Salva no windows
                                                 # em %HOME%/.gitconfig
git config --global user.email "user@host.com"   # configura o email da mesma forma.

git config --global --list    # visualiza as config. globais do usuario. Valem para todos
                              # projetos deste usuario.
                              #
git config --system --list    # visualiza as config. git do sistema. Valem para todos os
                              # usuários deste sistema. Fica armazenado no arquivo 
                              # "<drive>:\Program Files\Git\etc\gitconfig"
git config --local --list     # visualiza as config. git do repositorio atual. E preciso
                              # estar na pasta de um repo para funcionar. Le do arquivo
                              # ./.git/config
git config --list             # visualiza o conjunto de todas as config. para o repo.

git config user.name          # visualiza o valor final (precedencia local > global > system)
                              # de uma chave de config.

git help <verb>               # obtem ajuda para uma determinada ação do git

git status -vv                # lista as mudanças mostrando a diferença das versões
git status -z -u              # lista mudanças de forma simplificada

git init                  # cria o repositorio local. Irá criar um dir. oculto chamado .git
                          # que será usado para fazer o controle do git. (stage)
git add .                 # preparou arquivos no stage para commit.
                          # para fazer unstage de um arquivo, use 'git reset HEAD nome_arq'
git add *.html            # opção para adicionar ao index (stage) um tipo de arq. especifico


git commit -m "primeiro commit"    # faz um commit das mudanças até aqui. Os commits
                                   # depois devem ser empurrados no repositório remoto
                                   # com push.
                                   # para remover este commit 
                                   # use 'git reset --soft HEAD~1'
                                   # e entao faça novo commit e adicione arquivo novamente.
```                        

Agora é preciso criar o repositório no github usando as ferramentas do site, com mesmo nome
de nosso diretorio. Após criá-lo, abra no site o repositorio e copie a url do repo:
Ex: https://github.com/poliedrum/testegit.git

Agora com a url copiada, continuamos os comandos:
```
git remote add origin https://github.com/poliedrum/testegit.git   # adiciona referencia para o
                                                                  # repo remoto com apelido 
                                                                  # origin

git remote -v            # verifica se ficou configurado corretamente 

git push origin master   # empurra os commits na branch master local para o repo remoto.
                         # observe que no site agora deve aparecer o arquivo a.txt 
```
## Clonando um Repositório Existente

Para criar uma cópia local de um repositório existente no github, devemos utilizar a ação clone do comando git.
Esta ação irá fazer uma cópia completa do repositorio remoto, em um diretorio local com o mesmo nome. Dentro do diretório do repositório local, será criado um dir. .git que conterá toda a base do repo., ou seja, 
pelo repo. local é possível visualizar todo o histórico dos arquivos e suas versões. Além disso, replica no diretorio criado, uma copia de trabalho da ultima versão de cada arquivo no repo. (equivalente ao checkout de outros CVS).
Seguem os passos para clonar um repositório do github:
```
git clone https://github.com/poliedrum/testegit.git      # criará o diretorio testegit onde clonará o repo.


git clone https://github.com/poliedrum/testegit.git OutroDir  # opcionalmente, pode ser informado
                                                              # outro nome para o diretorio local. Assim,
                                                              # este comando clona um repositorio na maquina 
                                                              # local, criando a Pasta e copiando para ela o 
                                                              # conteúdo replicado. A pasta é opcional, se não 
                                                              # informada utiliza o nome do repositorio.

```

O git aceita outros protocolos, além do https. Uma opção é o 'git://' ou o SSH 'user@server:path/to/repo.git'

Quando é executado o comando clone, o repositório de origem já é configurado como repositório remoto com apelido origin.

## Criando Branch's e navegando entre elas

```
git log --oneline --decorate --graph --all   # visualizando as branchs
```

## Removendo arquivo via gitignore

Ao adicionar arquivos no .gitignore que já estão no repositório remoto, é preciso removê-los do cache para
excluí-los.
Siga os comandos abaixos para remover arquivos: (obs: eles permanecem no histórico dos commits)

```
# faça commit das alterações pendentes

# então rode estes comandos
# para remover tudo do stage (index) 
git rm -r --cached .

# adicione novamente
git add .

# faça commit
git commit -m ".gitignore agora está funcionando"



```

