# Bandit
# Level 13 a 14
## Objetivo
Encontrar la contraseña para el siguiente nivel, la cual se almacena en **/etc/bandit_pass/bandit14 y solo puede ser leído por el usuario bandit14** . 
Para este nivel, no obtiene la siguiente contraseña, pero obtenga una clave SSH privada que se puede usar para iniciar sesión en el siguiente nivel. 
**Nota:** **localhost** es un nombre de host que se refiere a la máquina en la que estás trabajando.

## Datos de acceso
Username: bandit13
Contraseña: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit13@bandit.labs.overthewire.org -p 2220
bandit13@bandit:~$ ls                                                                                          sshkey.private                                                                                                 bandit13@bandit:~$ cat /etc/bandit_pass/bandit14                                                               cat: /etc/bandit_pass/bandit14: Permission denied                                                              bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost
bandit14@localhost: Permission denied (publickey).
bandit13@bandit:~$ ssh -i sshkey.private bandit14@localhost -p 2220
  Enjoy your stay!
bandit14@bandit:~$
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```
 
## Notas adicionales
Yo tuve que poner el puerto en el comando ``ssh -i sshkey.private bandit14@localhost`` porque no me daba el acceso al usuario bandit14, quedó así ``ssh -i sshkey.private bandit14@localhost -p 2220``.
Es posible entrar desde el nivel 13 al 14 directamente porque se tiene la llave privada.
 
## Referencias
- [SSH/OpenSSH/Keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)
