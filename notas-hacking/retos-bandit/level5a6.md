# Bandit
# Level 0
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo en algún lugar bajo el **inhere** y tiene todas las siguientes propiedades:
	- Legible por humanos
	- 1033 bytes de tamaño
	- No ejecutable

## Datos de acceso
- Username: bandit5
- Contraseña: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
	ssh bandit5@bandit.labs.overthewire.org -p 2220
	bandit5@bandit:~$ cd inhere
	bandit5@bandit:~/inhere$ find .-type f size 1033c
	 find: ‘.-type’: No such file or directory
	 find: ‘f’: No such file or directory
	 find: ‘size’: No such file or directory
	 find: ‘1033c’: No such file or directory
	bandit5@bandit:~/inhere$ find . -type f -size 1033c
	 ./maybehere07/.file2
	bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
	 DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

## Notas adicionales
Existen muchas partes donde puede encontrarse el documento que estamos buscando, es por esto que se utiliza el comando ``find``  nos ayuda a encontar el archivo con las caracteristicas que especificamos.

## Referencias
- [Como usar el comando find en linux](https://www.ionos.mx/digitalguide/servidores/configuracion/comando-linux-find/)