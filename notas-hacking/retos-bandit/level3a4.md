# Bandit
# Level 3 a 4
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo oculto en el **interno** *(**inhere**)*.

## Datos de acceso
- Username: bandit3
- Contraseña: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK 
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
	ssh bandit3@bandit.labs.overthewire.org -p 2220
	bandit3@bandit:~$ ls
	 inhere
	bandit3@bandit:~$ cd inhere
	bandit3@bandit:~/inhere$ ls
	bandit3@bandit:~/inhere$ ls -a
	 .  ..  .hidden
	bandit3@bandit:~/inhere$ cat .hidden
	 pIwrPrtPN36QITSp3EQaw936yaFoFgAB 
	bandit3@bandit:~/inhere$ ls -la
	 total 12
	 drwxr-xr-x 2 root    root    4096 May  7  2020 .
	 drwxr-xr-x 3 root    root    4096 May  7  2020 ..
	 -rw-r----- 1 bandit4 bandit3   33 May  7  2020 .hidden
```

## Notas adicionales
Con ``ls``  no nos muestra los archivos ocultos, es por esto que se utiliza la opcion ``-la`` o ``-a``
para ver el archivo oculto en este caso.

## Referencias
- [Listar archivos ocultos](https://docs.oracle.com/cd/E19620-01/805-7644/files-86384/index.html)
