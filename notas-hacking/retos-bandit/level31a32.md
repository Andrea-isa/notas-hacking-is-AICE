# Bandit
# Level 31 a 32
## Objetivo
Hay un repositorio de git en ***ssh: //bandit31-git@localhost/home/bandit31-git/repo***. La contraseña para el usuario **bandit31-git** es la misma que para el usuario **bandit31**.
Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso
Username: bandit31
Contraseña: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit31@bandit.labs.overthewire.org -p 2220
bandit31@bandit:~$ mkdir /tmp/Andrea
bandit31@bandit:~$ cd /tmp/Andrea
bandit31@bandit:/tmp/Andrea$ git clone ssh://bandit31-git@loclhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
ssh: Could not resolve hostname loclhost: Temporary failure in name resolution
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
bandit31@bandit:/tmp/Andrea$ git clone ssh://bandit31-git@localhost:2220/home/band
Cloning into 'band'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
fatal: '/home/band' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
bandit31@bandit:/tmp/Andrea$ ls
repo
bandit31@bandit:/tmp/Andrea$ cd repo
bandit31@bandit:/tmp/Andrea/repo$ ls
README.md
bandit31@bandit:/tmp/Andrea/repo$ cat README.md
This time your task is to push a file to the remote repository.
Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
bandit31@bandit:/tmp/Andrea/repo$ echo ''May I come in?'' > key.txt
bandit31@bandit:/tmp/Andrea/repo$ cat key.txt
May I come in?
bandit31@bandit:/tmp/Andrea/repo$ git add -f key.txt
bandit31@bandit:/tmp/Andrea/repo$ git commit -m key.txt
[master 0c9a0b1] key.txt
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/sandiss/repo$ git push origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames
bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 322 bytes | 322.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/Andrea/repo$ rm -rf
```
 
## Notas adicionales

 
## Referencias
- No aplica
