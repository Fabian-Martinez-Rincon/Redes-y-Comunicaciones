## Practica 6

### Capa de Transporte - Parte 2

- [Ejercicio 1 ¿Cual es el puerto por defecto que se utiliza en los siguientes servicios?](#ejercicio-1)
- [Ejercicio 2 Investigue qué es multicast](#ejercicio-2)
- [Ejercicio 3 Investigue cómo funciona el protocolo de aplicación FTP](#ejercicio-3)
- [Ejercicio 4 Suponiendo Selective Repeat](#ejercicio-4)
- [Ejercicio 5 ¿Qué restricción existe sobre el tamaño de ventanas en el protocolo Selective Repeat?](#ejercicio-5)
- [Ejercicio 6 De acuerdo a la captura TCP de la siguiente figura](#practica-6)
- [Ejercicio 7 Dada la sesión TCP de la figura](#practica-7)
- [Ejercicio 8 ¿Qué es el RTT y cómo se calcula?](#ejercicio-8)
- [Ejercicio 9 Para la captura dada](#ejercicio-9)
- [Ejercicio 10 Responda las siguientes preguntas respecto del mecanismo de control de flujo](#ejercicio-10)
- [Ejercicio 11 Responda las siguientes preguntas respecto del mecanismo de control de congestión](#ejercicio-11)
- [Ejercicio 12 Para la captura dada, responder las siguientes preguntas](#ejercicio-12)

**Programación de sockets**
- [Ejercicio 13 Desarrolle un cliente y un servidor](#ejercicio-13)
- [Ejercicio 14 Compare ambas implementaciones](#ejercicio-14)

**Ejercicios de parcial**
- [Ejercicio 15 ](#ejercicio-15)
- [Ejercicio 16 ](#ejercicio-16)



<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 1

¿Cual es el puerto por defecto que se utiliza en los siguientes servicios?

Web / SSH/ DNS/WebSeguro / POP3 / IMAP / SMTP

Investigue en qué lugar en Linux y en Windows está descripta la asociación utilizada por defecto para cada servicio.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 2

Investigue qué es multicast. ¿Sobre cuál de los protocolos de capa de transporte funciona? ¿Se podría adaptar para que funcione sobre el otro protocolo de capa de transporte? ¿Por qué?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 3

Investigue cómo funciona el protocolo de aplicación FTP teniendo en cuenta las diferencias en su funcionamiento cuando se utiliza el modo activo de cuando se utiliza el modo pasivo ¿En qué se diferencian estos tipos de comunicaciones del resto de los protocolos de aplicación vistos?


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 4

Suponiendo Selective Repeat; tamaño de ventana 4 y sabiendo que E indica que el mensaje llegó con errores. Indique en el siguiente gráfico, la numeración de los ACK que el host B envía al Host A.

![image](https://github.com/Fabo-University/Redes-y-Comunicaciones/assets/55964635/59e988f8-8de1-49b4-ace9-54d0816f4f2e)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 5

¿Qué restricción existe sobre el tamaño de ventanas en el protocolo Selective Repeat?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 6

De acuerdo a la captura TCP de la siguiente figura, indique los valores de los campos borroneados.

![image](https://github.com/Fabo-University/Redes-y-Comunicaciones/assets/55964635/59fed271-c367-444e-b487-a604b6b145f9)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 7

Dada la sesión TCP de la figura, completar los valores marcados con un signo de interrogación


![image](https://github.com/Fabo-University/Redes-y-Comunicaciones/assets/55964635/ddce3aa5-4810-428c-a5fc-c962f39a48c5)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 8

¿Qué es el RTT y cómo se calcula? Investigue la opción TCP timestamp y los campos TSval y TSecr

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 9

Para la captura dada, responder las siguientes preguntas

#### Parte a

¿Cuántos intentos de conexiones TCP hay?

#### Parte b

¿Cuáles son la fuente y el destino (IP:port) para c/u?

#### Parte c

¿Cuántas conexiones TCP exitosas hay en la captura? Cómo diferencia las exitosas de las que no lo son? ¿Cuáles flags encuentra en cada una?

#### Parte d

Dada la primera conexión exitosa responder

i. ¿Quién inicia la conexión?


ii. ¿Quién es el servidor y quién el cliente?


iii. ¿En qué segmentos se ve el 3-way handshake?


iv. ¿Cuáles ISNs se intercambian?


v. ¿Cuál MSS se negoció?


vi. ¿Cuál de los dos hosts enva la mayor cantidad de datos (IP:port)?

#### Parte e

Identificar primer segmento de datos (origen, destino, tiempo, número de fila y número de secuencia TCP).

i. ¿Cuántos datos lleva?
 
ii. ¿Cuándo es confirmado (tiempo, número de fila y número de secuencia TCP)?
 
iii. La confirmación, ¿qué cantidad de bytes confirma?

#### Parte f

¿Quién inicia el cierre de la conexión? ¿Qué flags se utilizan? ¿En cuáles segmentos se ve (tiempo, número de fila y número de secuencia TCP)?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Ejercicio 10

Responda las siguientes preguntas respecto del mecanismo de control de flujo

- **a)** ¿Quién lo activa? ¿De qué forma lo hace?
- **b)** ¿Qué problema resuelve?
- **c)** ¿Cuánto tiempo dura activo y qué situación lo desactiva?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Ejercicio 11

Responda las siguientes preguntas respecto del mecanismo de control de congestión.

- **a)** ¿Quién lo activa el mecanismo de control de congestión? ¿Cuáles son los posibles disparadores?
- **b)** ¿Qué problema resuelve?
- **c)** Diferencie slow start de congestion-avoidance.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Ejercicio 12

Para la captura dada, responder las siguientes preguntas.

#### Parte a

¿Cuántas comunicaciones (srcIP,srcPort,dstIP,dstPort) UDP hay en la captura?

#### Parte b

¿Cómo se podrían identificar las exitosas de las que no lo son?

#### Parte c

¿UDP sigue el modelo cliente/servidor?

#### Parte d

¿Qué servicios o aplicaciones suelen utilizar este protocolo?

#### Parte e

¿Qué hace el protocolo UDP en relación al control de errores?

#### Parte f

Con respecto a los puertos vistos en las capturas, ¿observa algo particular que lo diferencie de TCP?

#### Parte g

Dada la primera comunicación en la cual se ven datos en ambos sentidos (identificar el primer datagrama):

i. ¿Quién envía el primer datagrama (srcIP,srcPort)?

ii. ¿Cuantos datos se envían en un sentido y en el otro?

#### Parte h

¿Se puede calcular un RTT?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

## Programación de sockets

#### Ejercicio 13

Resuelva los siguientes ejercicios utilizando el lenguaje de programación que prefiera (por simpleza, se recomiendan Python o Ruby).

#### Utilizando UDP

#### Utilizando TCP

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Ejercicio 14

Compare ambas implementaciones. ¿Qué diferencia nota entre la implementación de cada una? ¿Cuál le parece más simple?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">


## Ejercicios de parcial

#### Ejercicio 15

Dada la salida que se muestra en la imagen, responda los ítems debajo.

![image](https://github.com/Fabo-University/Redes-y-Comunicaciones/assets/55964635/14935f8d-003a-41e0-ad06-5c5cfbeedfdd)

Suponga que ejecuta los siguientes comandos desde un host con la IP 10.100.25.90. 

Responda qué devuelve la ejecución de los siguientes comandos y, en caso que corresponda, especifique los flags.

- **a)** hping3-p 3306–udp 10.100.25.135
- **b)** hping3-S-p 25 10.100.25.135
- **c)** hping3-S-p 22 10.100.25.135
- **d)** hping3-S-p 110 10.100.25.135

¿Cuántas conexiones distintas hay establecidas? Justifique.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Ejercicio 16

Complete en la columna Orden, el orden de aparición de los paquetes representados en cada fila

![image](https://github.com/Fabo-University/Redes-y-Comunicaciones/assets/55964635/66e99eff-0818-4127-8f80-1c4f5cd041e2)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">














