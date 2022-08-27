# Bandit
# Level 9 a 10
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** en una de las pocas cadenas legibles por humanos, precedida por varios '=' caracteres.

## Datos de acceso
- Username: bandit9
- Contraseña: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR 
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
ssh bandit9@bandit.labs.overthewire.org -p 2220
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt|grep ==
========== the*2i"4
========== password
Z)========== is
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk                                                                   
```

## Notas adicionales
El comando `strings` imprime los caracteres legibles.

## Referencias
- [Como imprimir con el comando strings en linux](https://tecnonautas.net/como-mostrar-los-caracteres-imprimibles-de-un-archivo-con-el-comando-strings/)