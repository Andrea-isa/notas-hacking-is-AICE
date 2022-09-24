# Bandit
# Level 17 a 18
## Objetivo
Hay dos archivos en el directorio de inicio: **passords.old** y **passwords.new**. La contraseña para el siguiente nivel  está en **passwords.new** y es la única línea que se ha cambiado entre **passwods.old** y **password.new**.

**NOTA: si ha resuelto este nivel y ve "¡Adios!" al intentar iniciar sesión en bandi18, esto está relaicionado con el siguiente nivel, bandit19.**

## Datos de acceso
Username: bandit17
Contraseña: VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit17@bandit.labs.overthewire.org -p 2220
bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ wc passwords.new
 100  100 3300 passwords.new
bandit17@bandit:~$ wc passwords.old
 100  100 3300 passwords.old
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg                      

```
 
## Notas adicionales
 diff: Compara linea por linea entre archivos los archivos que le indicamos y nos marca las diferencias que hay entre ellos, así obtenemos el password.
 
## Referencias
-[Uso del comando diff en Liux](https://geekland.eu/comparar-directorios-y-archivos-comando-diff-linux/)
