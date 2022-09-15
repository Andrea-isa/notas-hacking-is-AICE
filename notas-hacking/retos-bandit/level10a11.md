# Bandit
# Level 10 a 11
## Objetivo
Encontrar la contraseña para el siguiente nivel se almacena en el archivo **data.txt** , que contiene datos codificados en base64.

## Datos de acceso
Username: bandit10
Contraseña: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s 
Puerto: 2220
Host:  bandit.labs.overthewire.org
 
## Solución
```shell
ssh bandit10@bandit.labs.overthewire.org -p 2220
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ file data.txt
data.txt: ASCII text
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM 
```
 
## Notas adicionales
 Es fácil observar lo que se encuentra en el archivo data.txt, pero todo está codificado en base64, por lo tanto, si usamos el comando ``cat``  nos arroja el contenido, pero no es la contraseña que estamos buscando, por ende se usa el comando ``base64`` y ``-d`` para descodificar el contenido, así nos arroja la verdadera contraseña.
 
## Referencias
- [¿Qué es Base64, para qué sirve y cómo funciona](https://marquesfernandes.com/es/tecnologia-es/que-y-base64-para-que-serve-y-como-funciona/)
- [Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)

