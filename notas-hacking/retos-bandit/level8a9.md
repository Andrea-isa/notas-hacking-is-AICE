# Bandit
# Level 8 a 9
## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** y es la única línea de texto que aparece una sola vez.

## Datos de acceso
- Username: bandit8
- Contraseña: cvX2JJa4CFALtqS87jk27qwqGhBM9plV
- Puerto: 2220
- Host:  bandit.labs.overthewire.org

## Solución
```shell
ssh bandit8@bandit.labs.overthewire.org -p 2220
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
bandit8@bandit:~$ cat data.txt|sort|uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR   
```

## Notas adicionales
El comando ``sort`` ordena el documento, ``uniq`` muestra las veces que se repiten las líneas y con
`-u` se muestra la línea que se repite una única vez.

## Referencias
- [Como ordenar lineas en linux](https://www.ibidemgroup.com/edu/tutorial-sort-linux-unix/)
- [Uso del comando uniq en linux](https://victorhckinthefreeworld.com/2021/10/21/el-comando-uniq-de-gnu/)
