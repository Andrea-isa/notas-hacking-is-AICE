exi# Bandit
# Level 30 a 31
## Objetivo
Hay un repositorio de git en ***ssh: //bandit30-git@localhost/home/bandit30-git/repo***. La contraseña para el usuario **bandit30-git** es la misma que para el usuario **bandit30**.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
Username: bandit30
Contraseña: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit30@bandit.labs.overthewire.org -p 2220
bandit30@bandit:~$ cd tmp
-bash: cd: tmp: No such file or directory
bandit30@bandit:~$ cd /tmp
bandit30@bandit:/tmp$ mkdir osito
bandit30@bandit:/tmp$ cd sosito
bandit30@bandit:/tmp/osito$ cd repo
bandit30@bandit:/tmp/osito/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/osito/repo$ git log
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md
bandit30@bandit:/tmp/osito/repo$ git show a325f29e1cc26b0f0dc5f89b4348e389b408cc87
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..029ba42
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+just an epmty file... muahaha
bandit30@bandit:/tmp/osito/repo$ git reflog
a325f29 (HEAD -> master, origin/master, origin/HEAD) HEAD@{0}: clone: from ssh://localhost:2220/home/bandit30-git/repo
bandit30@bandit:/tmp/osito/repo$ cd .git
bandit30@bandit:/tmp/osito/repo/.git$ ls
branches  config  description  HEAD  hooks  index  info  logs  objects  packed-refs  refs
bandit30@bandit:/tmp/osito/repo/.git$ cat packed-refs
# pack-refs with: peeled fully-peeled sorted
a325f29e1cc26b0f0dc5f89b4348e389b408cc87 refs/remotes/origin/master
831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret
bandit30@bandit:/tmp/osito/repo/.git$ git show 831aac2e2341f009e40e46392a4f5dd318483019
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```
 
## Notas adicionales
Hacemos el mismo proceso de los dos niveles anteriores, pero en este caso debemos hacer `git relog`  para tener acceso directo y luego usamos `cd .git` para entrar al repo, hacemos `cat` al packed-refs para ver los comits realizados y posteriormente checamos cada uno con `git show`.
 
## Referencias
- [Uso del comando git reflogs](https://www.atlassian.com/es/git/tutorials/rewriting-history/git-reflog)
