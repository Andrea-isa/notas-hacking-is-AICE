# Bandit
# Level 15 a 16
## Objetivo
La contraseña para el siguiente nivel se puede recuperar enviando el contraseña del nivel actual al **puerto 30001 en localhost** usando Cifrado SSL.

**Nota útil: ¿Obtienes "HEARTBEATING" y "Read R BLOCK"? Usar -ign_eof y lea la sección "COMANDOS CONECTADOS" en la página de manual. Junto a 'R' y 'Q', el comando 'B' también funciona en esta versión de ese comando…**

## Datos de acceso
Username: bandit15
Contraseña: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Puerto: 2220
Host:  bandit.labs.overthewire.org

## Solución
 ```shell
ssh bandit15@bandit.labs.overthewire.org -p 2220
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  4 18:37:55 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  4 18:37:55 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  4 18:36:55 2022 GMT; NotAfter: Sep  4 18:37:55 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEYDP0vjANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTA0MTgzNjU1WhcNMjIwOTA0MTgzNzU1WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCQ
/ecAx/OKFUlCbsf61Ct6r5/Tqwhrvx4ML+3ZIZasi3VxkIML98WN/YA6mH5O4RPl
cLyiVv7Beq0wduoVNafDIfd2koJ9Dk/jK1bW6C42TRw68Wz3yAtBamYEOZYGWjsY
nWEsBf9cMqhaUhB4PBlavIIHTLce4UiqBNHhwNIIMsreqVVa4iqnuwtC2fUeg7SW
2vuukaPVL79XPtQ0y9Pgomld2AWFqOoP9dsbWiDUHAsVUzkotSG3ONA/Ek6vQwZP
k7G7wnn5ueqsG1Wp2N9bH+TuWQ3leIpMahtBvsZVMnrSvO8xUlySkPQDZgIIKQKN
CS//HcXmu8xc/lkV6/8VAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAP
eizXylgfIah76jAW3iuO1yZCnKURd0nUkYDl/IQKAMEfKjBSER09rh3mlieAafsK
owmzERqMFLkVtxceP3MMERs1xTxOy5S7UB1YO0kUsuo/M9Ppq8c5PAn55W6xQugm
/83mcvY0Esau4Y/L7Fdl7rmp+AoG5+t+O2aduBrtQmW5je0E+A+x3957sWYkMFPo
9omhvqXeNpQEDMq6tJZM0ALKKEYDwk74+GAwAC5pWGyuFPQczC0QYrWC8htRwxZu
YEvD42mGIMSidG2PmQ1nxaZuSVJptvllDzmFfZj+cYFepRON0wNS1tifvSXoQGA5
1LTuXas9E0ZpeqJHKy8f
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 850A8B613FA2FF37BE9353D65FDABCF132FF5DCBBC7E3C8DE43F49E841242EC8
    Session-ID-ctx:
    Resumption PSK: 84A1080A6A4201C13FEAE550691FD51CED65AE7DB185F8C667302D4CDD3AC7F22372FDA21F2F5FEACAFDFAC236EF484F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 4f fd 49 c1 e9 89 ce a1-f9 a8 73 44 86 f7 e7 e0   O.I.......sD....
    0010 - 94 97 47 b2 35 43 e3 23-2d 6b 95 fb 28 55 cd dc   ..G.5C.#-k..(U..
    0020 - cd b4 f8 8e bb e7 ec da-26 04 e0 e3 1a c9 01 c9   ........&.......
    0030 - 8a 94 cf 9f d2 e6 6c aa-a6 1e 5f 2f c6 d2 07 97   ......l..._/....
    0040 - d4 55 34 86 ce 40 9c b7-b4 7c 7c c4 e3 36 1a 4e   .U4..@...||..6.N
    0050 - 38 b1 f1 7a b3 a5 38 9e-19 88 6d 8d 21 83 4e 00   8..z..8...m.!.N.
    0060 - 21 c4 c8 5e cc 56 3a a5-82 88 16 f2 ce f9 7f 28   !..^.V:........(
    0070 - e7 f6 13 07 91 ed 7d 25-14 81 c6 25 f4 1a 8d 51   ......}%...%...Q
    0080 - 4c 79 6d 80 e8 f4 ae 1c-14 9f c5 5d 08 95 01 ea   Lym........]....
    0090 - 99 31 28 da c9 c6 67 a2-1e b9 3b 27 c6 43 13 33   .1(...g...;'.C.3
    00a0 - 0e 29 2c 63 6f 3d 01 61-8b 54 bf 21 96 8b db f1   .),co=.a.T.!....
    00b0 - d3 96 6c 60 c7 4b cb 4e-99 ed 88 6f 0f b5 9f 67   ..l`.K.N...o...g
    00c0 - 8b ca fb 76 2d 46 88 3c-05 79 6b 01 44 ad 4e 25   ...v-F.<.yk.D.N%

    Start Time: 1662331728
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 643B3ED101CC4D3094A24269BA4C9C3887DC156081226A9DB09B95C563C39E1D
    Session-ID-ctx:
    Resumption PSK: 1EC315A8D33A8B019B357C6819A3413C80E0C62784A114B4E27CD81195678E8BCD091954470139733F93768A3E8F2800
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 4f fd 49 c1 e9 89 ce a1-f9 a8 73 44 86 f7 e7 e0   O.I.......sD....
    0010 - 7f 83 04 82 6f d9 b3 20-b9 27 5c 81 de 8e bd a0   ....o.. .'\.....
    0020 - 83 2c 72 1e ee 22 bd 53-2b 54 5e ef c2 eb 1b 6e   .,r..".S+T^....n
    0030 - 83 12 ba a6 82 62 63 ec-39 e6 5b 9b 97 58 57 fd   .....bc.9.[..XW.
    0040 - 22 88 31 d6 94 0d b2 83-90 8c fe 9d f3 ef f1 59   ".1............Y
    0050 - d8 52 1c 5e 82 bb 0b c9-7b 3e 80 c5 3d 4a bd d3   .R.^....{>..=J..
    0060 - f7 b4 e1 ba d9 3f 7a 42-e3 de e0 51 c6 7d 0c f8   .....?zB...Q.}..
    0070 - 6e 9a b3 a3 81 99 ee e2-48 d2 18 ac cc ee 80 12   n.......H.......
    0080 - b0 1e f3 8b 46 da c1 0c-c5 01 cf f9 bf 40 bf ec   ....F........@..
    0090 - 16 18 cd 4b 59 cf 03 d7-26 50 a4 a0 c1 7a 44 a2   ...KY...&P...zD.
    00a0 - a4 26 2d b1 4c 5c 37 7e-9c 0d 91 43 88 4a 19 8e   .&-.L\7~...C.J..
    00b0 - 93 5c e2 fd a8 27 96 fc-c2 ed d0 cd 71 97 51 a5   .\...'......q.Q.
    00c0 - 8a 12 30 c8 7b 61 d8 8b-3e 64 b8 c9 fb a1 67 41   ..0.{a..>d....gA

    Start Time: 1662331728
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
l
Wrong! Please enter the correct current password
closed
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  4 18:37:55 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  4 18:37:55 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  4 18:36:55 2022 GMT; NotAfter: Sep  4 18:37:55 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEYDP0vjANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTA0MTgzNjU1WhcNMjIwOTA0MTgzNzU1WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCQ
/ecAx/OKFUlCbsf61Ct6r5/Tqwhrvx4ML+3ZIZasi3VxkIML98WN/YA6mH5O4RPl
cLyiVv7Beq0wduoVNafDIfd2koJ9Dk/jK1bW6C42TRw68Wz3yAtBamYEOZYGWjsY
nWEsBf9cMqhaUhB4PBlavIIHTLce4UiqBNHhwNIIMsreqVVa4iqnuwtC2fUeg7SW
2vuukaPVL79XPtQ0y9Pgomld2AWFqOoP9dsbWiDUHAsVUzkotSG3ONA/Ek6vQwZP
k7G7wnn5ueqsG1Wp2N9bH+TuWQ3leIpMahtBvsZVMnrSvO8xUlySkPQDZgIIKQKN
CS//HcXmu8xc/lkV6/8VAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAP
eizXylgfIah76jAW3iuO1yZCnKURd0nUkYDl/IQKAMEfKjBSER09rh3mlieAafsK
owmzERqMFLkVtxceP3MMERs1xTxOy5S7UB1YO0kUsuo/M9Ppq8c5PAn55W6xQugm
/83mcvY0Esau4Y/L7Fdl7rmp+AoG5+t+O2aduBrtQmW5je0E+A+x3957sWYkMFPo
9omhvqXeNpQEDMq6tJZM0ALKKEYDwk74+GAwAC5pWGyuFPQczC0QYrWC8htRwxZu
YEvD42mGIMSidG2PmQ1nxaZuSVJptvllDzmFfZj+cYFepRON0wNS1tifvSXoQGA5
1LTuXas9E0ZpeqJHKy8f
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 1A43EE523C3A3D82FD2878AEE70A87DEC4EC58285CA31108D786D3BEF79AC2DB
    Session-ID-ctx:
    Resumption PSK: A0903F2396E966F60AEF8AC541C91FC8536ED3151960759171AD27998664F84FD6DA5C68B48024316C3FF5F585210EFD
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 4f fd 49 c1 e9 89 ce a1-f9 a8 73 44 86 f7 e7 e0   O.I.......sD....
    0010 - 4e 8e 74 27 7d 3f fb 0b-44 2a 09 35 4b c0 13 e3   N.t'}?..D*.5K...
    0020 - 7f 9b d0 db 88 4c 4f 79-f0 58 77 47 1b d0 9e 0c   .....LOy.XwG....
    0030 - cb ea 37 99 18 5d e7 62-b7 7a 17 47 3e ed e0 1f   ..7..].b.z.G>...
    0040 - 5e 73 f7 fc 14 69 01 c9-31 b9 53 9f c2 af 5c 80   ^s...i..1.S...\.
    0050 - 7f 75 66 94 5b d1 73 b7-99 1d ac 24 49 fa da db   .uf.[.s....$I...
    0060 - c6 b9 cc f1 49 c4 b0 5f-c4 6e 1d cd 97 c2 44 f0   ....I.._.n....D.
    0070 - 21 ff 04 61 50 46 68 d0-4d 15 38 14 ce 45 3a ea   !..aPFh.M.8..E:.
    0080 - 07 0d 03 8d ed 32 be 3f-fd 0b 6e 7f 82 52 02 b0   .....2.?..n..R..
    0090 - cd 26 e6 9b 6c 69 57 17-44 08 67 a8 06 e2 f8 07   .&..liW.D.g.....
    00a0 - 0d ec 63 9d c6 1d fa 8c-0f 89 55 da 3e d8 34 9e   ..c.......U.>.4.
    00b0 - 66 c4 88 ac 7e 61 f5 a1-80 c7 6d 49 17 15 ce 61   f...~a....mI...a
    00c0 - 05 45 2c 98 7f 64 ef c6-77 c4 55 c3 0f 6f 04 52   .E,..d..w.U..o.R

    Start Time: 1662331783
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 4776E33DCA6A8807243B36BBB09A49ED2076D4DB9B389171C39688996E1E3136
    Session-ID-ctx:
    Resumption PSK: 9CC3381139ADBB099D37EFBDB255D6D5735FBA67AF7E5E89B84C2A36F0C6339644DBA7652830243F7FD2C889384280BD
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 4f fd 49 c1 e9 89 ce a1-f9 a8 73 44 86 f7 e7 e0   O.I.......sD....
    0010 - 46 91 55 99 af 90 90 b6-c9 7b 52 af 91 f6 eb 24   F.U......{R....$
    0020 - 13 c6 19 be b7 d3 e1 c5-77 28 b9 eb d4 db 2f 5d   ........w(..../]
    0030 - 13 20 b9 b7 a4 ef 1b 6f-3d 89 58 d7 50 6f d7 66   . .....o=.X.Po.f
    0040 - 30 67 19 74 90 2e a1 bb-a2 32 14 bc 5e 4c 4a 48   0g.t.....2..^LJH
    0050 - 2c 5c a4 dc 35 ca 8f 7f-91 7b 7b 0b db e6 34 c4   ,\..5....{{...4.
    0060 - 45 77 02 b5 8b fa a6 91-0d 53 23 7b 5a 72 4b 9d   Ew.......S#{ZrK.
    0070 - b9 ec ef 70 70 c2 45 44-f3 1f 49 90 d9 38 54 92   ...pp.ED..I..8T.
    0080 - d0 1c b8 78 79 ea af fe-78 91 d0 c4 8a 1e 44 cd   ...xy...x.....D.
    0090 - 2c 01 40 0e 98 a7 86 41-00 f6 0a 0c 92 be a5 7c   ,.@....A.......|
    00a0 - 71 99 22 63 f3 c5 70 21-39 71 76 7f ce 55 cf 12   q."c..p!9qv..U..
    00b0 - ae 43 af 52 9d 68 a3 25-da 91 6f d6 19 ed 70 5e   .C.R.h.%..o...p^
    00c0 - 9a 3a a2 67 07 8e f7 34-e6 60 42 bf 6f 07 95 e7   .:.g...4.`B.o...

    Start Time: 1662331783
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$ 
```
 
## Notas adicionales
- openssl: Lo usamos para conectarnos de forma segura, despues pasamos la contraseña del nivel quince para que nos regrese la del siguiente nivel.
- Aunque me obtuve un Read R Block, al final solo puse la contraseña del nivel 15 y obtuve la constraseña del nivel 16.
 
## Referencias
-   [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
-   [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)
