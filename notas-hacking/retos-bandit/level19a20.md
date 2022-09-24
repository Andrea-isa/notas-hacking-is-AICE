# Bandit
# Level 19 a 20
## Objetivo
Para obtener aceso al siguiente nivel, debe usar el binario *setuid* en el directorio de inicio. Ejecutarlo sin argumentos para saber cómo usarlo. La contraseña para este nivel se puede encontrar en el lugar habitual (/etc/bandit_pass), después de haber utilizado el binario *setuid*.

## Datos de acceso
Username: bandit19
Contraseña: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit19@bandit.labs.overthewire.org -p 2220
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rwsr-x---  1 bandit20 bandit19 14872 Sep  1 06:30 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$

```
 
## Notas adicionales
Podemos usar el bandit20-do para ejecutar comandos como el usuario bandit20, por lo tanto podemos ver la contraseña que está almacenada en /etc/bandit_pass/bandit20 usando el comando `cat`.

## Referencias
- [setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)
