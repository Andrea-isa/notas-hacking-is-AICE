# Bandit
# Level 6 a 7
## Objetivo
La contraseña para el siguiente nivel se almacena **en algún lugar del servidor** (***somewhere on the server***) y tiene todas las siguientes propiedades:
	- Propiedad del usuario bandit7
	- Propiedad del grupo bandit6
	- 33 bytes de tamaño

## Datos de acceso
Username: bandit6
Contraseña: DXjZPULLxYr17uwoI01bNLQbtFemEgo7
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
```shell
ssh bandit6@bandit.labs.overthewire.org -p 2220
bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 May  7  2020 .
drwxr-xr-x 41 root root 4096 May  7  2020 ..
-rw-r--r--  1 root root  220 May 15  2017 .bash_logout
-rw-r--r--  1 root root 3526 May 15  2017 .bashrc
-rw-r--r--  1 root root  675 May 15  2017 .profile
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs  
```

## Notas adicionales
Para encontrar el archivo que estamos buscando usamos el comando ``find``, ``user`` para el usario al que pertenece, ``group`` para el grupo al que pertenece, ``size`` para el tamaño que tiene y ``2>`` para no mostrar aquello a lo que no tenemos permiso.

## Referencias