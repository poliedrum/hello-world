# hello-world
Repositorio para aprendizagem da ferramenta GIT

Este é apenas um repositório de teste, cujo objetivo é permitir a aprendizagem das ferramentas gits, e servir como 
material de apoio em futuros estudos.

## Passos executados

Após instalar o aplicativo GIT (git-scm.com) em meu desktop windows, utilizei os seguintes comandos a seguir para criar um repositorio local e depois replicar no repositorio remoto do [github](https://github.com/).

```
mkdir testegit                      # creando diretorio que será o repositorio local
cd testegit                         # tornando este dir. o diretorio corrente
touch a.txt                         # criando um arquivo para verificar sincronização remota

git init                # cria o repositorio local. Irá criar um dir. oculto chamado .git
                        # que será usado para fazer o controle do git. (stage)
```                        

git clone https://github.com/user/repositorio.git Pasta
Este comando clona um repositorio na maquina local, criando a Pasta e copiando para ela o conteúdo replicado. A
pasta é opcional, se não informada utiliza o nome do repositorio.



