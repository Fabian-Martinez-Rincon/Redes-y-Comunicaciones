## Práctica 11

### Capa de Enlace- Parte 2

- [Ejercicio 1 Utilizando la máquina virtual provista por la cátedra](#ejercicio-1)
- [Ejercicio 2 ¿Qué es 802.11? Compare las direcciones MAC que contiene el encabezado de una trama 802.11](#ejercicio-2)
- [Ejercicio 3 Complete el siguiente cuadro y luego investigue qué estándar utilizan los dispositivos ](#ejercicio-3)
- [Ejercicio 4 Dada la siguiente topología, donde se pueden apreciar cuatro estaciones de trabajo](#ejercicio-4)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 1

**(Ejercicio de promoción) Utilizando la máquina virtual provista por la cátedra, arme una red como la siguiente, con un segmento de LAN usando un HUB y otro segmento de LAN usando un SWITCH.**

*NOTA: paraquienes haganla promoción, este será un ejercicio entregable. En la entrega deberán estar todas las preguntas respondidas y debidamente justificadas. En los puntos donde es necesario ejecutar comandos, los mismos deberán adjuntarse a la entrega.*

![image](https://github.com/Fabo-University/ISO/assets/55964635/de00a88b-aaf0-420e-a82b-e96dc8bfb6a0)

#### Parte a

Antes de empezar el ejercicio ejecute en una terminal el siguiente comando:

```bash
sudo iptables-P FORWARD ACCEPT
```

#### Parte b

Analizar el funcionamiento de ARP.

i. Indique para PC1_SW, PC2_SW y PC3_SW la IP y la dirección MAC de cada una.


ii. Verifique el contenido de la tabla ARP de cada una de ellas.


iii. Inicie Wireshark en PC2_SW y luego envíe un ping desde la PC1_SW a la PC2_SW. Analice los paquetes ARP e ICMP capturados e indique

- **Para ARP**: tipo de paquete, direcciones de capa 2 y datos específicos del protocolo.
- **Para ICMP**: tipo de paquete, direcciones de capa 2, de capa 3, tipo y código ICMP.

iv. Verifique nuevamente el contenido de la tabla ARP de las PCs ni bien termine de ejecutar el comando ping. ¿Qué entradas aparecen en cada tabla y por qué? ¿Qué estado tienen (ip neigh ls)?

v. Borre las entradas de las tablas ARP de ambas PC y agregue de forma estática en PC1_SW la entrada que corresponde a PC2_SW y en PC2_SW la que corresponde a PC1_SW. Si hiciera un ping de PC1_SWaPC2_SW,¿severíanpaquetesdeARP?Verifíqueloenlamáquinavirtual iniciando una captura de tráfico en PC2_SW. ¿Qué estado tienen ahora las entradas ARP?

vi. En PC1_SWmodifique la entrada ARP que agregó en el punto anterior poniendo una MAC que no exista en la red. Vuelva a intentar hacer el ping. ¿Qué ocurre y por qué?

#### Parte c

Analizar y comparar el funcionamiento de un HUB y de un SWITCH.

i. Antes de empezar asegúrese que todas las tablas estén vacías. Puede hacerlo deteniendo e iniciando la topología nuevamente.

ii. Inicie Wireshark en PC3_HUB y luego envíe un ping desde la PC1_HUB a PC2_HUB. Analice el origen y destino de cada uno de los paquetes ARP e ICMP capturados. ¿Alguno se origina en o va destinado a PC3_HUB? ¿Por qué observa cada uno de esos paquetes?

iii. Inicie Wireshark en PC3_SW y luego envíe un ping desde la PC1_SW a PC2_SW. Analice el origen y destino de cada uno de los paquetes ARP e ICMP capturados. ¿Alguno se origina en o va destinado a PC3_SW? ¿Por qué observa cada uno de esos paquetes?

iv. ¿Qué diferencia observa entre los dos casos anteriores? Explique por qué ocurre así.

v. Indique cómo queda la tabla CAM del SWITCH una vez realizado el ping. ¿Cómo se arma y en qué orden?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 2

¿Qué es 802.11? Compare las direcciones MAC que contiene el encabezado de una trama 802.11 con los de unatrama Ethernet, ¿cuál es la principal diferencia que encuentra? Investigue por qué cambian en 802.11 y para qué se usan.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 3

Complete el siguiente cuadro y luego investigue qué estándar utilizan los dispositivos inalámbricos que tiene en su poder (su celular, su computadora, etc.).

| Estándar | Año | Frecuencia | Velocidad máxima |
|----------|-----|------------|------------------|
| 802.11a  |     |            |                  |
| 802.11ac |     |            |                  |
| 802.11b  |     |            |                  |
| 802.11g  |     |            |                  |
| 802.11n  |     |            |                  |

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 4

Dada la siguiente topología, donde se pueden apreciar cuatro estaciones de trabajo, dos conectadas me diante un cable UTP y dos de forma inalámbrica, responda las siguientes preguntas.

![image](https://github.com/Fabo-University/ISO/assets/55964635/0a465124-27e5-43b9-93cb-af1c874b7dd5)

Suponiendo que las tablas ARP están completas y que STA A realiza un ping a STA B:


**Indique, entre STA A y el AP (1 azul) y entre el AP y STA B (2 azul):**

- Tipo de trama MAC (indicar si es 802.11 o Ethernet).
- Direcciones MAC de la trama. 
- IP origen e IP destino

Suponiendo que las tablas ARP están vacías y que STA A debe realizar un ARP Request para averiguar la MACdeSTAB:

**Indique, entre STA A y el AP (1 azul) y entre el AP y STA B (2 azul):**

- Tipo de trama MAC (indicar si es 802.11 o Ethernet).
- Direcciones MAC de la trama

¿Cómo sería el ARP Reply que va desde STA B hacia el AP? Indique las direcciones MAC de la trama.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">