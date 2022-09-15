# Bandit
# Level 11 a 12
## Objetivo
Encontrar la contraseña para el siguiente nivel, que se almacena en el archivo **data.txt** , donde todas las letras minúsculas (az) y mayúsculas (AZ) se han girado 13 posiciones.

## Datos de acceso
Username: bandit11
Contraseña: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
Puerto: 2220
Host:  bandit.labs.overthewire.org
 
## Solución
 ```shell
ssh bandit11@bandit.labs.overthewire.org -p 2220
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv 
```

 
## Notas adicionales
- tr: puede utilizarce para "rotar" un texto, se le indica el orden
 
## Referencias
- [Uso de tr](https://en.wikipedia.org/wiki/ROT13)
