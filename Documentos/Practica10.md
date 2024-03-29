## Práctica 10

### Capa de Enlace- Parte 1

- [Ejercicio 1 ¿Qué función cumple la capa de enlace? Indique qué servicios presta esta capa](#ejercicio-1)
- [Ejercicio 2 Compare los servicios de la capa de enlace con los de la capa de transporte.](#ejercicio-2)
- [Ejercicio 3 Direccionamiento Ethernet](#ejercicio-3)
- [Ejercicio 4 Sobre los dispositivos de capa de enlace](#ejercicio-4)
- [Ejercicio 5 Describa el algoritmo de acceso al medio en Ethernet](#ejercicio-5)
- [Ejercicio 6 ¿Cuál es la finalidad del protocolo ARP?](#ejercicio-6)
- [Ejercicio 7 Investigue los comandos arp e ip neigh. Inicie una topología con CORE](#ejercicio-7)
- [Ejercicio 8 Dado el siguiente esquema de red, responda](#ejercicio-8)
- [Ejercicio 9 En la siguiente topología de red indique](#ejercicio-9)
- [Ejercicio 10 En la siguiente topología](#ejercicio-10)
- [Ejercicio 11 ¿Existe ARP en IPv6? ¿Por qué? ¿Quién cumple esa función?](#ejercicio-11)
- [Ejercicio 12 ¿Qué es la IEEE 802.3? ¿Existen diferencias con Ethernet?](#ejercicio-12)
- [Ejercicio 13 Nombre cinco protocolos de capa de enlace](#ejercicio-13)
- [Ejercicio 14 Ejercicio de parcial](#ejercicio-14)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 1

¿Qué función cumple la capa de enlace? Indique qué servicios presta esta capa.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 2

Compare los servicios de la capa de enlace con los de la capa de transporte.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 3

Direccionamiento Ethernet:

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 4

Sobre los dispositivos de capa de enlace

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 5

Describa el algoritmo de acceso al medio en Ethernet. ¿Es orientado a la conexión?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 6

¿Cuál es la finalidad del protocolo ARP?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 7

Investigue los comandos arp e ip neigh. Inicie una topología con CORE, cree una máquina y utilice en ella los comandos anteriores para:

 - Listar las entradas en la tabla ARP.
 - Borrar una entrada en la tabla de ARP.
 - Agregar una entrada estática en la tabla de ARP.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 8

Dado el siguiente esquema de red, responda

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/a71f8886-86e8-42bb-9cb7-4f590c854d4a)

#### Parte a

Suponiendo que las tablas de los switches están llenas con la información correcta, responda quién escucha el mensaje si:

- i. La estación 1 envía una trama al servidor 1.
- ii. La estación 1 envía una trama a la estación 11.
- iii. La estación 1 envía una trama a la estación 9.
- iv. La estación 4 envía una trama a la MAC de broadcast.
- v. La estación 6 envía una trama a la estación 7.
- vi. La estación 6 envía una trama a la estación 10.

#### Parte b

¿En qué situaciones se pueden producir colisiones?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 9

En la siguiente topología de red indique:

![image](https://github.com/Fabo-University/ISO/assets/55964635/32dab107-59fe-4d7c-a3ae-5207f3863f6c)

#### Parte a

¿Cuántos dominios de colisión hay?

#### Parte b

¿Cuántos dominios de broadcast hay?

#### Parte c

Indique cómo se va llenando la tabla de asociaciones MAC->PORT de los switches SW1 y SW2 durante el siguiente caso:

i. A envía una solicitud ARP consultando la MAC de C.

ii. C responde esta solicitud ARP.

iii. A envía una solicitud ARP consultando la MAC de B.

iv. B responde esta solicitud ARP.

#### Parte d

Si la PC E y la PC D hubiesen estado realizando un tcpdump para escuchar todo lo que pasa por su interfaz de red, ¿cuáles de los requerimientos/respuestas anteriores hubiesen escuchado cada una?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 10

En la siguiente topología:

![image](https://github.com/Fabo-University/ISO/assets/55964635/0bb25465-13ba-4377-a8b5-a896bbf2bd8d)

Suponiendo que todas las tablas ARP están vacías, tanto de PCs como de Routers. Si la PC_A le hace un ping a la PC_C, indique:

¿En qué dominios de broadcast hay tráfico ARP? ¿Con qué direcciones de origen y destino?

¿En qué dominios de broadcast hay tráfico ICMP?

- ¿Con qué direcciones de origen y destino de capa 2?
- ¿Con qué direcciones de origen y destino de capa 3?

¿Cuál es la secuencia correcta en la que se suceden los anteriores?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 11

¿Existe ARP en IPv6? ¿Por qué? ¿Quién cumple esa función?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 12

¿Qué es la IEEE 802.3? ¿Existen diferencias con Ethernet?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 13

Nombre cinco protocolos de capa de enlace. ¿Todos los protocolos en esta capa proveen los mismos servicios?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio de parcial

Si la PC A está en una red y se quiere comunicar con la PC B que está en otra red:

¿Como se da cuenta la PC A de esto?

Si la tabla ARP de la PCAestavacía, ¿que dirección MAC necesita la PC A para poder comunicarse con la PC B?

En base a lo anterior, ¿que dirección IP destino tiene el requerimiento ARP? ¿Es la dirección IP del default gateway o es la dirección IP de la PC B? De ser necesario, ejecute de nuevo el experimento de ser necesario y complete los campos:

```bash
 Trama Ethernet:    (mac origen: _________________ mac destino: _________________)
 Solicitud ARP:     (mac origen: _________________ ip origen: _________________)
                    (mac destino: _________________ ip destino: _________________)
```

En base a lo anterior, indique la información de capa 2 y 3 del ICMP ECHO REQUEST que la PC A le envía a la PC B cuando ejecuta un ping, en el segmento de LAN de la PC B.

