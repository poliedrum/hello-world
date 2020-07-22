# hello-world
Repositorio para aprendizagem da ferramenta GIT

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
                                                            


git init                  # cria o repositorio local. Irá criar um dir. oculto chamado .git
                          # que será usado para fazer o controle do git. (stage)
git add .                 # preparou arquivos no stage para commit.
                          # para fazer unstage de um arquivo, use 'git reset HEAD nome_arq'

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
                                                                  # repo remoto

git remote -v            # verifica se ficou configurado corretamente 

git push origin master   # empurra os commits na branch master local para o repo remoto.
                         # observe que no site agora deve aparecer o arquivo a.txt 
```

git clone https://github.com/user/repositorio.git Pasta
Este comando clona um repositorio na maquina local, criando a Pasta e copiando para ela o conteúdo replicado. A
pasta é opcional, se não informada utiliza o nome do repositorio.



