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
    ------------------------------- #a /27 Admin
    210.1.2. 0 01 00000  (32)
    210.1.2. 0 01  11111  (63)
    ------------------------------- #b /27 Prod
    210.1.2. 0 1 000000  (64)
    210.1.2. 0 1 111111  (127)
    ------------------------------- #c /26 Gerencia

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
    Se subnetea en /27 
    La primera mitad es para el laboratorio /27
    210.21.32.0 00 00000 (0)
    210.21.32.0 00 11111 (31)

    La segunda mitad 
    210.21.32.32
    Ahora esto se subnetea en 4 subredes diferentes (Administración, servers, Ensayos, Análisis). Para esto necesito que sea /29

    210.21.32.0 01 00 000 (32)
    210.21.32.0 01 00 111 (39)
    -----------------------------#Administración
    210.21.32.0 01 01 000 (40)
    210.21.32.0 01 01 111 (47)
    ------------------------------#Servidores
    210.21.32.0 01 10 000 (48)
    210.21.32.0 01 10 111 (55)
    -----------------------------#Ensayos
    210.21.32.0 01 11 000 (56)
    210.21.32.0 01 11 111 (63)
    -----------------------------#Análisis
### Mini redes para punto a punto.
    Vamos a sacar dos enlaces punto a punto /30
    Que los voy a sacar de la última parte del rango.
    210.21.32.0/25
    
    /30 CABA - Córdoba
    210.21.32.111111 00 (252)
    210.21.32.111111 11 (255)
    
    /30 CABA - Bariloche
    210.21.32.111110 00 (248)
    210.21.32.111110 11 (251)
    
    
### Córdoba
    210.21.32.128/25
    Necesito en total 25 IPS para esta oficina, entonces se subneteará con /27

    210.21.32.128/27
    Para el LABORATORIO
    210.21.32.1 00 00000 (128)
    210.21.32.1 00 11111 (159) --ESTE RANGO ES PARA LAB

    La otra mitad del rango es:
    210.21.32.1 01 00000 (160)
    210.21.32.1 01 11111 (191)

    Esta segunda mitad se subnetará en 4 subredes de /29
    210.21.32.1 01 00 000 (160)
    210.21.32.1 01 00 111 (167)
    -------------------------------------#Ensayos
    210.21.32.1 01 01 000 (168)
    210.21.32.1 01 01 111 (175)
    -------------------------------------#Administración
    210.21.32.1 01 10 000 (176)
    210.21.32.1 01 10 111 (183)
    -------------------------------------#Análisis
    210.21.32.1 01 11 000 (184)
    210.21.32.1 01 11 111 (191)
    -------------------------------------#Servers
