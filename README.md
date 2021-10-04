=================================================================================================================================
Instalação do git 

Windowns
Site oficial git 
https://git-scm.com/

Linux

https://git-scm.com/download/linux
add-apt-repository ppa:git-core/ppa # apt update; apt install git

==================================================================================================================================

Oque é o SHA1 ? 

O SHA1 é uma maneira de criptografar dados, é usada numa grande variedade de aplicações e protocolos de segurança, GIT, TLS, SSL, PGP, SSH e outros. É desta forma que o git sabe quando houve modificação em um arquivo.

exemplo 

echo "ola mundo" | openssl sha1
(stdin)= d9802fa01c4c1dfc4ddaf61f766d8d56ad8a8699

echo "ola mundo." | openssl sha1
(stdin)= d7f712d48514ff4866e83ad77999c46036d83747

Se a string mudar, muda a hash gerada. Se a string voltar a ser o que era, a hash volta.

===================================================================================================================================

Objetos do git 

BLOBS
TREES
COMMITS


===================================================================================================================================

Configuração chaves ssh

 $ ssh-keygen -t ed25519 -C luccasschardt@hotmail.com
 $ cd ~/.ssh
 $ ls
 $ cat id_ed25519.pub 
 $ eval $(ssh-agent -s)
 $ ssh-add id_ed25519

===================================================================================================================================

Criar um repositório 

mkdir curso_git
cd curso_git/
ls
git init 
git config --global user.email "luccasschardt@hotmail.com"
git config --global user.name luschardt
mkdir readme.md

.md é a extensão markdown nela é possivel formatar os textos utilizando as seguintes estruturas

https://support.typora.io/Markdown-Reference/

===================================================================================================================================










