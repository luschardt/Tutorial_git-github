**Tutorial basico para uso das ferramentas git/github**
 
- **Instalação do git**

Windows :

Site oficial git 
https://git-scm.com/

Linux :

https://git-scm.com/download/linux

```sh
$ add-apt-repository ppa:git-core/ppa -y
$ apt update
$ apt install git
```

=================================================================================

- **Oque é o SHA1 ?**

O SHA1 é uma maneira de criptografar dados, é usada numa grande variedade de aplicações e protocolos de segurança, GIT, TLS, SSL, PGP, SSH e outros. É desta forma que o git sabe quando houve modificação em um arquivo.

exemplo:

```sh
echo "ola mundo" | openssl sha1
(stdin)= d9802fa01c4c1dfc4ddaf61f766d8d56ad8a8699

echo "ola mundo." | openssl sha1
(stdin)= d7f712d48514ff4866e83ad77999c46036d83747
```

Se a string mudar, muda a hash gerada. Se a string voltar a ser o que era, a hash volta.

=================================================================================

- **Objetos do git**

**BLOBS** - Bolhas são onde o git armazena os arquivos encriptados pelo SHA1, somados à alguns metadados como
Tipo (blob), Tamanho, \0 e o conteúdo do arquivo (texto, binario ou qualquer outro).

Exemplo:

```sh
$ echo 'conteudo' | git hash-object --stdin
fc31e91b26cf85a55e072476de7f263c89260eb1

$ echo -e 'blob 9\0conteudo' | openssl sha1
(stdin)= fc31e91b26cf85a55e072476de7f263c89260eb1

```

**TREES** - Arvores são obejetos que armazena/aponta para as bolhas(blobs) ou outras arvores. Assim como as bolhas elas contém metadados
Nome, tamanho, \0, blobs que por sua vez possuem seu sha1. 


**COMMITS** - É um objeto muito importante pois ele aponta consecutivamente para uma arvore, parente, autor e uma mensagem. Em poucas palavras os 
commits dão significancia para as alterações e é por ele que é possivel fazer o traking das modificações em um projeto. 


=================================================================================

- **Configuração das chaves ssh**

Forma de estabelecer uma conexão segura entre 2 máquinas, no nosso caso o servidor
do Github e nossa máquina. Após configurada essas chaves poderá ser feito uploads de 
arquivos, códigos tranquilamente sem senha e de forma extremamente segura.

```sh
 $ ssh-keygen -t ed25519 -C email@email.com
 $ cd ~/.ssh
 $ ls
 $ cat id_ed25519.pub 
 $ eval $(ssh-agent -s)
 $ ssh-add id_ed25519
```
=================================================================================

- **Criar um repositório**
```sh
$ mkdir curso_git
$ cd tutorial_git/
$ ls
$ git init 
$ git config --global user.email "email@email.com"
$ git config --global user.name nickname
$ nano README.md
```

.md é a extensão markdown nela é possivel formatar os textos utilizando as seguintes estruturas

https://support.typora.io/Markdown-Reference/

https://www.markdownguide.org/extended-syntax/

- Escreva o readme e salve o arquivo
```sh
$ git add *
#Esse comando adicionara todos arquivos a stage area, logo poderão ser comitados

#[Opcional] $ git add [pasta ou arquivo]
#Esse comando adicionará apenas a pasta ou arquivo para stage area, para seguir com o commit

$ git commit -m "Ex: Foi feito a seguinte mudança"
```
=================================================================================

- **Inicio git hub**

Verificar se as configurações de email e nickname estão de acordo com a conta do git hub

Caso não esteja, poderá alterar utilizando os seguintes comandos
```sh
$ git config --global --unset user.email
$ git config --global --unset user.name
$ git config --global user.email "email@email.com"
$ git config --global user.name "nickname"
```
**Proceguindo**
```sh
#Criar novo repositório no git hub

$ git remote add origin git@github.com:link_ssh_repositório
#origin é um apelido para o link, para minimizar o comando push, por exemplo.
$ git branch -M main
#Criar uma branch principal (main)
$ git push -u origin main
#Fazer upload dos arquivos e versionamento para o git hub.
```

Esse tutorial tem como base o curso introdutório de git/github oferecido gratuitamente pela plataforma Digital Innovation one.



