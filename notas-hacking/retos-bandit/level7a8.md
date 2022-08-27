# Bandit
# Level 7 a 8
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** junto a la palabra **millionth***

## Datos de acceso
- Username: bandit7
- Contraseña: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs 
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
ssh bandit7@bandit.labs.overthewire.org -p 2220
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV 
```

## Notas adicionales
Con grep se puede buscar entre un archivo, en este caso el archivo en donde se encuentra la contraseña tiene demasiadas lineas como para revisar una por una, es por eso que se utiliza el comando ``grep`` seguido de la palabra clave que nos dan y enseguida el nombre del archivo.

## Referencias
- [Como usar el comando grep en liux](https://www.hostinger.mx/tutoriales/comando-grep-linux)
- [Como buscar patrones con grep](https://docs.oracle.com/cd/E19620-01/805-7644/6j76klop3/index.html)
