# Bandit
# Level 18 a 19
## Objetivo
La contraseña para el siguiente nivel se almacena en un arhivo ***README*** en el directorio de inicio. Desafortunadamente, alguien ha modificado **.bashrc** para cerrar la sesión con SSH.

## Datos de acceso
Username: bandit18
Contraseña: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit18@bandit.labs.overthewire.org -p 2220
Byebye !
Connection to bandit.labs.overthewire.org closed.


C:\Users\user>ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

C:\Users\user>

```
 
## Notas adicionales
En cuanto se entra se ejecuta un comando exit para salir sin poder hacer nada más, pero es posible indicar lo que queremos hacer justo antes de entrar, de este modo, podemos obtener la contrasea para el siguiente nivel antes de que nos saque de la seión. También, podemos ver los archivos antes de conectarnos poniendo de lado el comando (en este caso lo manejamos asi porque la sesión de este nivel nos sacaba cada que ingresabamos).
 
## Referencias
- No aplica

