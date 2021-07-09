# 2021-TP-Final-Redes

Informe Final TP REDES

Se agregan los dos routers designados para Córdoba y Bariloche, y se conectan mediante un enlaace de fibra.

Bloque CABA :  210.1.2.0/24
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


Bloque CBA+BAR: 210.21.32.0/24