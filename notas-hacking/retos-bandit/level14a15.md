# Bandit
# Level 14 a 15
## Objetivo
Encontrar la contraseña para el siguiente nivel, la cual se puede recuperar enviando la contraseña del nivel actual al **puerto 30000 en localhost** .

## Datos de acceso
Username: bandit14
Contraseña: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit14@bandit.labs.overthewire.org -p 2220
bandit14@bandit:~$ nc localhost 30000 -v
Connection to localhost (127.0.0.1) 30000 port [tcp/*] succeeded!
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt   

bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

bandit14@bandit:~$ nc -v localhost 30000
Connection to localhost (127.0.0.1) 30000 port [tcp/*] succeeded!
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
 
## Notas adicionales
Nos conectamos al localhost en el puerto 30000 y le damos la contraseña del nivel en el que estamos, que es el 14, como respuesta nos devuelve la contraseña del siguinete nivel, que es el 15.
Tenemos 3 soluciones:
- El comando ``nc localhost 30000 -v``
- El comando ``nc localhost 30000``
- Y el comando ``nc -v localhost 30000``
Los tres tenemos la misma respuesta.
 
## Referencias
-   [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc) (Not completely accurate, but good enough for beginners)
-   [IP Addresses](http://computer.howstuffworks.com/web-server5.htm)
-   [IP Address on Wikipedia](https://en.wikipedia.org/wiki/IP_address)
-   [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
-   [Ports](http://computer.howstuffworks.com/web-server8.htm)
-   [Port (computer networking) on Wikipedia](https://en.wikipedia.org/wiki/Port_(computer_networking))
