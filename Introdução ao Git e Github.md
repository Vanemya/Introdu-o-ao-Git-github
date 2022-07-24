## INTRODUÇÃO AO GIT/GITHUB

### Conceito

O **Git**, é um sistema de gerenciamento e versionamento de código distribuído seguro, instalado na máquina local.

**GitHub** por sua vez é o local onde são hospedadas (na nuvem) as versões desse código, permitindo o seu compartilhamento com segurança.

Este conteúdo é direcionado para pessoas que estão iniciando as atividades no desenvolvimento de sistemas e estão buscando um breve resumo dos principais comandos utilizados para sincronização do Git com o Github até a sua completa memorização.   



### Pré -requisito

a) [Inst alar o Git](https://git-scm.com/) 

b) [Realizar o cadastro no Github](https://github.com/)

c) [Instalar Typora,  editor para  Markdown (linguagem simples do HTML)](https://typora.io/)



### Estabelecendo conexão  

Para estabelecer uma conexão segura entre o Git e Github, é necessário configurar o protocolo Secure Socket Shell (SSH) no Git.

1)  Digite "ssh-keygen -t ed25519 - C seuemail@no github.com "

2) Vá até o diretório infomado no resultado do comando item1. onde está localizada a pasta .ssh (utilize os comandos cd, cd .., ls ou pwd)

3) Ao listar os arquivos ocultos  com "ls -a"

4) Edite  o arquivo público que está na pasta .ssh 

   cat id_ed25519.pub

5) Copie a resposta a esse comando que inicia com "sha" e termina com o seu e-mail cadastrado no Github clicando na seta do seu perfil no site do Github (canto superior direito da tela) > Settings >SSH and GPG keys > clique  no botão "New SSh Key", Identifique qual máquina local será conectada diretamente com o Github e no outro cole a resposta ao comando  do item 4., conforme o item 5. clique em "commit" no final dos campos.

6) Novamente no Git digite o seguinte comando para dar o start no projeto:

   eval $(ssh-agent -s)

7)  Localize o diretório informado no item2.  para passar o Agent para a chave privada, digite :

   ssh-add id_ed25519         

8) Acerte a configuraçãao do Git na sua máquina local :

   git config --list

   git config  --global --unset user.email 

   git config  --global --unset user.name

   git config  --global user.email "seuemail@no github.com"

   git config  --global user.name "seu user name cadastrado no Github"

   git config --list   (vai verificar que agora aparece o user.email e o user.name na lista)

9) Você pode  criar um repositório no Github, com um nome que se aproxima da finalidade do código a ser desenvolvido, preencha o campo com uma breve descrição, deixando público , clique no botão "criar repositório ".

10) Volte no Git, no diretório que está o código que deseja sincronizar com o Github e digite o comando:

    git clone ( coloque aqui sem parênteses o link do SSH informado dentro do repositório criado no item9. no Github )

    

### Comandos

git init  ( Inicializa o repositório no Git)

git add (mover arquivos e inicia versionamento no Git)

git add * ou Git add -A  (adiciona todos os arquivos do diretório)

git  commit -m "nome do projeto"  (quando vai fazer o primeiro arquivo no repositório coloca uma breve descrição entre aspas")

git push origin master  (comando utilizado para empurrar oara o servidor o código )

  