# Bandit
# Level 0 a 1
## Objetivo
Encontrar la contraseña del siguiente nivel que se encuentra dentro de un archivo llamado "readme", ubicado en el directorio de inicio.

## Datos de acceso
- Username: bandit0 
- Contraseña: bandit0
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
	ssh bandit0@bandit.labs.overthewire.org -p 2220
	bandit0@bandit:~$ ls
	readme
	bandit0@bandit:~$ cat readme
	boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

## Notas adicionales
El comando ls nos sirve para listar los archivos mientras que cat nos muestra el contenido de estos.

## Referencias
-   [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
-   [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)