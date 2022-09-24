# Bandit
# Level 29 a 30
## Objetivo
Hay un repositorio de git en ***ssh: //bandit29-git@localhost/home/bandit29-git/repo***. La contraseña para el usuario **bandit29-git** es la misma que para el usuario **bandit29**.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
Username: bandit29
Contraseña: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit29@bandit.labs.overthewire.org -p 2220
bandit29@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Sep  1 06:29 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit29@bandit:~$ l
bandit29@bandit:~$ -l
-l: command not found
bandit29@bandit:~$ ls -l
total 0
bandit29@bandit:~$ cd /tmp
bandit29@bandit:/tmp$ mkdir andyss
bandit29@bandit:/tmp$ cd andyss
bandit29@bandit:/tmp/andyss$ ls
bandit29@bandit:/tmp/andyss$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/andyss$ ls -la
total 332
drwxrwxr-x    3 bandit29 bandit29   4096 Sep 24 18:32 .
drwxrwx-wt 2459 root     root     327680 Sep 24 18:32 ..
drwxrwxr-x    3 bandit29 bandit29   4096 Sep 24 18:32 repo
bandit29@bandit:/tmp/andyss$ cd repo
bandit29@bandit:/tmp/andyss/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 24 18:32 .
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 24 18:32 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Sep 24 18:32 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Sep 24 18:32 README.md
bandit29@bandit:/tmp/andyss/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/andyss/repo$ git log
commit 1748acec99ba66676acd551c2932fb9fc14a98a3 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    fix username

commit c27fff763003bb1d57d311e6763211110b94cc87
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    initial commit of README.md
bandit29@bandit:/tmp/andyss/repo$ git show 1748acec99ba66676acd551c2932fb9fc14a98a3
commit 1748acec99ba66676acd551c2932fb9fc14a98a3 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    fix username

diff --git a/README.md b/README.md
index 2da2f39..1af21d3 100644
--- a/README.md
+++ b/README.md
@@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.

 ## credentials

-- username: bandit29
+- username: bandit30
 - password: <no passwords in production!>

bandit29@bandit:/tmp/andyss/repo$ git show c27fff763003bb1d57d311e6763211110b94cc87
commit c27fff763003bb1d57d311e6763211110b94cc87
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..2da2f39
--- /dev/null
+++ b/README.md
@@ -0,0 +1,8 @@
+# Bandit Notes
+Some notes for bandit30 of bandit.
+
+## credentials
+
+- username: bandit29
+- password: <no passwords in production!>
+
bandit29@bandit:/tmp/andyss/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/andyss/repo$ git checkout remotes/origin/dev
Note: switching to 'remotes/origin/dev'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 2b1395f add data needed for development
bandit29@bandit:/tmp/andyss/repo$ git log
commit 2b1395f00cfb986163082c50100be5be8f249f64 (HEAD, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add data needed for development

commit 989df8073e16b5f7ec337f51bc1f60bd2f6b7e0b
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add gif2ascii

commit 1748acec99ba66676acd551c2932fb9fc14a98a3 (origin/master, origin/HEAD, master)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    fix username

commit c27fff763003bb1d57d311e6763211110b94cc87
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    initial commit of README.md
bandit29@bandit:/tmp/andyss/repo$ git show 2b1395f00cfb986163082c50100be5be8f249f64
commit 2b1395f00cfb986163082c50100be5be8f249f64 (HEAD, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials

 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/andyss/repo$

```
 
## Notas adicionales
Casi el mismo proceso del nivel anterior, pero camibia en que cuando queremos hacer el `git show` de cada uno de los commit realizados en el repositorio no nos da la contraseña, por lo que tenemos que hacer `git branch -a` descubrir el branch actual del repsitorio y ve si hay cambios recientes, después haremos `git checkout` para denegar la entrada a ramas creadas con git branch, y ahora sí hacemos `git log` y `git show`, despues de revisar cada uno de los commit obtendremos la contraseña dentro de alguno de ellos.
 
## Referencias
- [Uso del comando git branch](https://www.atlassian.com/git/tutorials/using-branches)
- [Uso del comando git checkout](https://www.atlassian.com/git/tutorials/using-branches/git-checkout)
