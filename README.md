# 2021-TP-Final-Redes

Informe Final TP REDES

Se agregan los dos routers designados para Córdoba y Bariloche, y se conectan mediante un enlace de fibra.

### CABA
    210.1.2.0/24
    Primero se divide en 2 subredes, una mitad contendrá los servidores, y la otra

    Se divide en 4 subredes, para contener a todos los host.
    Las subredes son a) b) c) d) que se dan en el enunciado.


    210.1.2.0 /25
    210.1.2.0~ 210.1.2.127 
    Esta es la primer mitad, la divido en 4 subredes
    210.1.2. 0 00 00000   (0) 
    210.1.2. 0 00  11111  (31)
    ------------------------------- #a /27 (224) Admin 
    210.1.2. 0 01 00000  (32)
    210.1.2. 0 01  11111  (63)
    ------------------------------- #b /27 Prod
    210.1.2. 0 1 000000  (64)
    210.1.2. 0 1 111111  (127)
    ------------------------------- #c /26 (192) Gerencia

    210.1.2.128~ 210.1.2.255
    Esta es la segunda mitad. Necesito una subred para los 20 host de Sistemas.
    210.1.2. 1 00 00000 (128)
    210.1.2. 1 00 11111 (159)
    El resto de las ips de este bloque va a ser para asignar a servidores y otros dispositivos.


Ahora ya se tienen todos los rangos de ip

Bloque CBA+BRC: 210.21.32.0/24
Se divide en 2 subredes :
    
### Bariloche
    210.21.32.0/25
    Se subnetea en /26

    La primera mitad es para los hosts
    210.21.32.0 0 000000 (0)
    210.21.32.0 0 111111 (63)
### Mini redes para punto a punto.
    La segunda mitad 
    210.21.32.0 1 000000 (64)
    210.21.32.0 1 111111 ()

    210.21.32.64 Se subnetea en /30 para enlaces pto a pto

El primero (CABA-BRC)
    210.21.32.0 1 0000 00 (64)
        Hosts: 65 (CABA),66(BRC)
    210.21.32.0 1 0000 11 (67)

El segundo(CABA-CBA)
    210.21.32.0 1 0001 00 (68)
        Hosts: 69(CABA),70(CBA)
    210.21.32.0 1 0001 11 (71)
    
### Córdoba
    210.21.32.128/25
    Es todo un mismo segmento.
