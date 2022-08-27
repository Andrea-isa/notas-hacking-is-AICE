# Bandit
# Level 1 a 2
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado **-** ubicado en el directorio de inicio.

## Datos de acceso
- Usuario: bandit1
- Contraseña: boJ9jbbUNNfktd78OOpsqOltutMc3MY1
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
	ssh bandit1@bandit.labs.overthewire.org -p 2220
	bandit1@bandit:~$ ls                                                                                       
    -                                                                                                          
    bandit1@bandit:~$ cat ./-                                                                                      
    CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
    bandit1@bandit:~$ cat <-
	CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9                                                                               
```

## Notas adicionales
Si usamos un "-" como nombre de un archivo en el comando cat, este no lo toma como su nombre, es por esto que debemos anteponer el *(./)* , *(<)* o su ruta absoluta, cualquiera para la solución.

## Referencias
- [Como abrir un archivo con un guion por nombre](https://stackoverflow.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal)
-   [Búsqueda en Google de "nombre de archivo discontinuo"](https://www.google.com/search?q=dashed+filename)
-   [Guía avanzada de secuencias de comandos Bash - Capítulo 3 - Caracteres especiales](http://tldp.org/LDP/abs/html/special-chars.html)