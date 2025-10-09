Averiguar como crear una tabla.


| TCP/IP         | OSI                 | PDU                  | Dispositivos                      | Protocolos                                                      | Direcciones                          | Ataques                         |
| -------------- | ------------------- | -------------------- | --------------------------------- | --------------------------------------------------------------- | ------------------------------------ | ------------------------------- |
| 4 - Aplicación | 7 - Aplicación      | Datos                | Gateway, Servidores, NGFW         | DNS, HTTP, IMAP, DHCP, SMTP, SSM, FTP, POP3                     |                                      | SQL Injection, XSS              |
|                | 6 - Presentación    |                      |                                   |                                                                 |                                      |                                 |
|                | 5 - Sesión          |                      |                                   |                                                                 |                                      |                                 |
|                | 4 - Transporte      | Segmento / Datagrama |                                   | TCP (seguro) UDP (rápido)                                       |                                      |                                 |
| 3 - Transporte | 3 - Red             | Paquete              | Router, Firewall                  | ICMP, IPv4, IPv6, ARP                                           | Puertos (65535 / 2^16)               | DDOS, IP spoofing, MITM         |
| 2 - Internet   | 2 - Enlace de datos | Trama                | Switch, AP                        | ARP Ethernet (IEEE 802.3)  Wifi (802.11) Bluetooh (IEEE 802.15) | Direcciones lógicas o direcciones IP | MITM, ARP Spoofing, MAC glading |
| 1 - Subred     | 1 - Física          | Bits                 | Hub, Cables (utp, fibra, coaxial) |                                                                 | Direcciones físicas o MAC            |                                 |
