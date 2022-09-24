# Bandit
# Level 28 a 29
## Objetivo
Hay un repositorio de git en ***ssh: //bandit28-git@localhost/home/bandit28-git/repo***. La contraseña para el usuario **bandit28-git** es la misma que para el usuario **bandit28**.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
Username: bandit28
Contraseña: AVanL161y9rsbcJIsFHuw35rjaOM19nR
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit28@bandit.labs.overthewire.org -p 2220
bandit28@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Sep  1 06:29 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit28@bandit:~$ mkdir /tmp/andys
bandit28@bandit:~$ cd /tmp/andys
bandit28@bandit:/tmp/andys$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password:
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/andys$ ls -la
total 332
drwxrwxr-x    3 bandit28 bandit28   4096 Sep 24 18:12 .
drwxrwx-wt 2437 root     root     327680 Sep 24 18:12 ..
drwxrwxr-x    3 bandit28 bandit28   4096 Sep 24 18:13 repo
bandit28@bandit:/tmp/andys$ cd repo
bandit28@bandit:/tmp/andys/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Sep 24 18:13 .
drwxrwxr-x 3 bandit28 bandit28 4096 Sep 24 18:12 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Sep 24 18:13 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Sep 24 18:13 README.md
bandit28@bandit:/tmp/andys/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/andys/repo$ git log
commit 43032edb2fb868dea2ceda9cb3882b2c336c09ec (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    fix info leak

commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    add missing data

commit 43d032b360b700e881e490fbbd2eee9eccd7919e
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:24 2022 +0000

    initial commit of README.md
bandit28@bandit:/tmp/andys/repo$ git show bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
commit bdf3099fb1fb05faa29e80ea79d9db1e29d6c9b9
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:25 2022 +0000

    add missing data

diff --git a/README.md b/README.md
index 7ba2d2f..b302105 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials

 - username: bandit29
-- password: <TBD>
+- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

bandit28@bandit:/tmp/andys/repo$

```
 
## Notas adicionales
Luego de entrar a bandit28 creamos una carpeta temporal con `mkdir` y accedemos a ella con `cd`. Dentro de esta carpeta usamos el comando `git clone` y la dirección ssh para clonar el repositorio. Ahora accedemos al repositorio clonado con `cd repo`, y si hacemos un `cat` al archivo README no podremos ver lo que contiene. Tendremos que usar el comando `git log` para ver el historial de modificaciones del repositorio que clonamos, así como otrso detalles, y porteriormente usamos `git show` para ver más detalles de cada commit que se hizo (estos los podemos ver gracias al git log), así obtendremos la contraseña del siguiente nivel.
 
## Referencias
- [Uso de git log](https://www.atlassian.com/es/git/tutorials/inspecting-a-repository)
- [Uso de git show](https://www.atlassian.com/git/tutorials/git-show)