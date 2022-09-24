# Bandit
# Level 21 a 22
## Objetivo
Un programa se ejecuta automáticamente a intervalos regulares desde **cron**, el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y vea qué comando se está ejecutando.

## Datos de acceso
Username: bandit21
Contraseña: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit21@bandit.labs.overthewire.org -p 2220
bandit21@bandit:~$ ls
bandit21@bandit:~$ cat /etc/cron.d/
cat: /etc/cron.d/: Is a directory
bandit21@bandit:~$ ls -la /etc/cron.d/
total 48
drwxr-xr-x   2 root root 4096 Sep  1 06:30 .
drwxr-xr-x 110 root root 4096 Sep  8 12:09 ..
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit15_root
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit17_root
-rw-r--r--   1 root root  120 Sep  1 06:30 cronjob_bandit22
-rw-r--r--   1 root root  122 Sep  1 06:30 cronjob_bandit23
-rw-r--r--   1 root root  120 Sep  1 06:30 cronjob_bandit24
-rw-r--r--   1 root root   62 Sep  1 06:30 cronjob_bandit25_root
-rw-r--r--   1 root root  201 Jan  8  2022 e2scrub_all
-rwx------   1 root root   52 Sep  1 06:30 otw-tmp-dir
-rw-r--r--   1 root root  102 Mar 23 13:49 .placeholder
-rw-r--r--   1 root root  396 Feb  2  2021 sysstat

bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit21@bandit:~$


```
 
## Notas adicionales
Si se observa lo que se encuentra en el directorio indicado, podemos observar lo que se está ejecutando en el momento, entre ello el `cronjob_bandit22`, al hacerle un `cat` se observa el lugar donde se encuentra la contraseña. Además, vemos el comando `cron`  ayuda a controlar las tareas que se van ejecutando, podemos poner tiempos para que se puedan ejecutar esas tareas.

 
## Referencias
- [Referencia 1, Solución nivel 21 a 22](https://jwuk.files.wordpress.com/2016/05/writeup1.pdf)
- [Referencia 2, Solución nivel 21 a 22](https://medium.com/secttp/overthewire-bandit-level-21-f7856b84b1c1)