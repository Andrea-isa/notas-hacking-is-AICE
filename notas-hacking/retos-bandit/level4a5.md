# Bandit
# Level 4 a 5
## Objetivo
La contraseña para el siguiente nivel se encuentra en un archivo que solamente es legible por humanos, archivo en el **here** . Consejo: si tu terminal está desordenado arriba, intente con el comando "restablecer" *(**reset**)*.

## Datos de acceso
Username: bandit4
Contraseña: pIwrPrtPN36QITSp3EQaw936yaFoFgAB
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
```shell

	ssh bandit4@bandit.labs.overthewire.org -p 2220
	bandit4@bandit:~$ ls
	 inhere
	bandit4@bandit:~$ cd inhere
	bandit4@bandit:~/inhere$ ls -l
	 total 40
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file00
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file01
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file02
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file03
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file04
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file05
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file06
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file07
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file08
	 -rw-r----- 1 bandit5 bandit4 33 May  7  2020 -file09
	bandit4@bandit:~/inhere$ ls -la
	 total 48
	 drwxr-xr-x 2 root    root    4096 May  7  2020 .
	 drwxr-xr-x 3 root    root    4096 May  7  2020 ..
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file00
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file01
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file02
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file03
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file04
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file05
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file06
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file07
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file08
	 -rw-r----- 1 bandit5 bandit4   33 May  7  2020 -file09
	bandit4@bandit:~/inhere$ file ./*
	 ./-file00: data
	 ./-file01: data
	 ./-file02: data
	 ./-file03: data
	 ./-file04: data
	 ./-file05: data
	 ./-file06: data
	 ./-file07: ASCII text
	 ./-file08: data
	 ./-file09: data
	bandit4@bandit:~/inhere$ cat ./-file07
	 koReBOKuIDDepwhWk7jZC0RTdopnAYKh
	 bandit4@bandit:~/inhere$ file ./-file00
	 ./-file00: data
	bandit4@bandit:~/inhere$ file ./-file04
	 ./-file04: data
	bandit4@bandit:~/inhere$ file ./-file07
	 ./-file07: ASCII text
	bandit4@bandit:~/inhere$ file ./-file09
	 ./-file09: data
	bandit4@bandit:~/inhere$ cat ./-file07
	 koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

## Notas adicionales
Los archivos que pueden leerse son los que están en código ASCII, es decir los que son datos no  legibles, es por esto que se puede revisar uno por uno los archivos en la carpeta para ver su tipo de archivo con ``file ./-(nombre del archivo)``, o bien, podemos utilizar ``file ./*`` para ver una lista con el nombre de cada archivo junto a su tipo de archivo (este es la manera más rápida). Si usamos ``ls -l`` o ``ls -la`` podemos ver una lista de los archivos y sus nombres, pero no el tipo de archivo de cada uno.

## Referencias
- [Comando LS](https://www.freecodecamp.org/espanol/news/el-comando-linux-ls-como-listar-archivos-en-un-directorio-indicadores-de-opcion/)
- [Ver tipo de archivo con file](https://cambiatealinux.com/file-informacion-sobre-el-tipo-de-fichero)
- [Ver el tipo de archivo en Linux](https://noviello.it/es/como-ver-el-tipo-de-archivo-con-el-comando-archivo-en-linux/)