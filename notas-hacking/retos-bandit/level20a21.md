# Bandit
# Level 20 a 21
## Objetivo
Hay un binario *setuid* en el directorio de inicio que hace los siguiente: establece una conexión con *localhost* en el puerto que especifique como argumento de la línea de comandos. Luego lee una línea de texto de la conexión y la compara con la contraseña del nivel anterior (*bandit20*). Si la contraseña es correcta, transmitirá la contraseña para el siguiente nivel (*bandit21*).
**NOTA:** intente coectarse a su propio demonio de red para ver si funiona como cree.

## Datos de acceso
Username: bandit20
Contraseña: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit20@bandit.labs.overthewire.org -p 2220
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15596 Sep  1 06:30 suconnect
bandit20@bandit:~$ ls -la ./suconnect
-rwsr-x--- 1 bandit21 bandit20 15596 Sep  1 06:30 ./suconnect
bandit20@bandit:~$ echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | nc -l localhost -p
nc: option requires an argument -- 'p'
usage: nc [-46CDdFhklNnrStUuvZz] [-I length] [-i interval] [-M ttl]
          [-m minttl] [-O length] [-P proxy_username] [-p source_port]
          [-q seconds] [-s sourceaddr] [-T keyword] [-V rtable] [-W recvlimit]
          [-w timeout] [-X proxy_protocol] [-x proxy_address[:port]]
          [destination] [port]
bandit20@bandit:~$ nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 2165332
bandit20@bandit:~$ Listening on 0.0.0.0 3030
bandit20@bandit:~$ ./suconnect 3030
Connection received on 127.0.0.1 36336
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lnvp 3030 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$


```
 
## Notas adicionales

Para abrir una conección usamos el comando  `nc -lnvp`  y el puerto, en este caso también mandamos la contraseña y para pasarlo a segundo plano usamos `&` , podemos usar `jobs` para ver una lista de procesos en segundo plano. También se utiliza `nc -l` para que Netcat abra un puerto y se mantenga a la escucha y `-p` para especificar a que puerto conectarse.


## Referencias
- [Solucion encontrada](https://medium.com/secttp/overthewire-bandit-level-20-a1af9a042c56)
- [TCP](https://es.adminsub.net/tcp-udp-port-finder/61337)
- [nc](https://www.neoguias.com/comando-nc/)
