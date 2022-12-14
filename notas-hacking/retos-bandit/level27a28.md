# Bandit
# Level 27 a 28
## Objetivo
Hay un repositorio de git en ***ssh: //bandit27-git@localhost/home/bandit27-git/repo***. La contraseña para el usuario **bandit27-git** es la misma que para el usuario **bandit27**.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
Username: bandit27
Contraseña: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit27@bandit.labs.overthewire.org -p 2220
bandit27@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Sep  1 06:29 .
drwxr-xr-x 49 root root 4096 Sep  1 06:30 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit27@bandit:~$ mkdir /tmp/andysgit
bandit27@bandit:~$ cd /tmp/andysgit
bandit27@bandit:/tmp/andysgit$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/andysgit$ ls -la
total 332
drwxrwxr-x    3 bandit27 bandit27   4096 Sep 24 02:15 .
drwxrwx-wt 1949 root     root     327680 Sep 24 02:15 ..
drwxrwxr-x    3 bandit27 bandit27   4096 Sep 24 02:16 repo
bandit27@bandit:/tmp/andysgit$ cd repo
bandit27@bandit:/tmp/andysgit/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/andysgit/repo$

```
 
## Notas adicionales
Usamos el comando `git clone` y la dirección ssh que se nos proporciona para copiar el repositorio.
 
## Referencias
- [Clonar un respositorio de git](https://docs.github.com/es/repositories/creating-and-managing-repositories/cloning-a-repository)
