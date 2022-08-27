# Bandit
# Level 0
## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado **espacios en este nombre de archivo** (**spaces in this filename**) ubicado en el directorio de inicio.

## Datos de acceso
- Usuario: bandit2
- Contraseña: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
	ssh bandit2@bandit.labs.overthewire.org -p 2220
	bandit2@bandit:~$ ls
    spaces in this filename
    bandit2@bandit:~$ cat spaces in this filename
     cat: spaces: No such file or directory
     cat: in: No such file or directory
     cat: this: No such file or directory
     cat: filename: No such file or directory
    bandit2@bandit:~$ cat "spaces in this filename"
    UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK 
```

## Notas adicionales
Para utlizar el nombre con espacios en el comando cat es posible poner el nombre del archivo entre comillas. 

## Referencias
- [Como leer un archivo con un nombre con espacios](https://linoxide.com/how-to-read-filename-with-spaces-in-linux/)