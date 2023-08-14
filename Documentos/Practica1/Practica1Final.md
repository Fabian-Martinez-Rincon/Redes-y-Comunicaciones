<div align='center'>

# Practica 1 Introducción

</div>

### Pregunta 1
¿Qué es una red? ¿Cuál es el principal objetivo para construir una red?
- Una red es un conjunto de dispositivos (nodos) conectados entre sí mediante enlaces físicos y/o lógicos con el objetivo de compartir recursos e información. El principal objetivo para construir una red es facilitar la comunicación y el intercambio de datos entre dispositivos, así como compartir recursos como impresoras, archivos y servicios de internet.

### Pregunta 2
¿Qué es Internet? Describa los principales componentes que permiten su funcionamiento.
- Internet es una red global de redes interconectadas que utilizan el protocolo TCP/IP para comunicarse. Los principales componentes que permiten su funcionamiento incluyen servidores, routers, switches, líneas de transmisión y protocolos de comunicación.

### Pregunta 3
¿Qué son las RFCs?
- Las RFCs (Request for Comments) son documentos técnicos que describen los estándares y protocolos relacionados con Internet. Son publicados por la IETF (Internet Engineering Task Force) y sirven como referencia para el desarrollo y operación de tecnologías en la red.

### Pregunta 4
¿Qué es un protocolo?
- Un protocolo es un conjunto de reglas y convenciones que determinan cómo se transmiten, reciben y procesan los datos entre dispositivos en una red.

### Pregunta 5
¿Por qué dos máquinas con distintos sistemas operativos pueden formar parte de una misma red?
- Dos máquinas con distintos sistemas operativos pueden formar parte de una misma red porque los protocolos de comunicación, como TCP/IP, son estándares y están implementados en todos los sistemas operativos modernos, lo que permite la interoperabilidad entre diferentes dispositivos.

### Pregunta 6
¿Cuáles son las 2 categorías en las que pueden clasificarse a los sistemas finales o End Systems? Dé un ejemplo del rol de cada uno en alguna aplicación distribuida que corra sobre Internet.
- Las dos categorías son: clientes y servidores. En una aplicación distribuida como el correo electrónico, el cliente (tu aplicación de correo) solicita servicios al servidor (servidor de correo), que procesa la solicitud y envía la respuesta al cliente.

### Pregunta 7
¿Cuál es la diferencia entre una red conmutada de paquetes y una red conmutada de circuitos?
- En una red conmutada de circuitos, se establece un circuito dedicado para la comunicación entre dos puntos durante toda la duración de la llamada (como en la telefonía tradicional). En una red conmutada de paquetes, los datos se dividen en paquetes y se envían de forma independiente a través de la red, siendo reensamblados en el destino (como en Internet).

### Pregunta 8
Analice qué tipo de red es una red de telefonía y qué tipo de red es Internet.
- La red de telefonía es una red conmutada de circuitos, mientras que Internet es una red conmutada de paquetes.

### Pregunta 9
Describa brevemente las distintas alternativas que conoce para acceder a Internet en su hogar.
- Las alternativas incluyen: ADSL, fibra óptica, conexión por cable, conexión inalámbrica (Wi-Fi), conexión móvil (3G, 4G, 5G), y satélite.

### Pregunta 10
¿Qué ventajas tiene una implementación basada en capas o niveles?
- La implementación basada en capas permite modularidad, facilita el diseño, la implementación y la depuración. También permite la interoperabilidad entre diferentes fabricantes y tecnologías, ya que cada capa puede evolucionar de forma independiente.

### Pregunta 11
¿Cómo se llama la PDU (Unidad de Datos del Protocolo) de cada una de las siguientes capas: Aplicación, Transporte, Red y Enlace?
- Aplicación: Mensaje
  Transporte: Segmento (TCP) / Datagrama (UDP)
  Red: Paquete
  Enlace: Trama

### Pregunta 12
¿Qué es la encapsulación? Si una capa realiza la encapsulación de datos, ¿qué capa del nodo receptor realizará el proceso inverso?
- La encapsulación es el proceso de añadir encabezados y/o trailers a los datos a medida que descienden por las capas del modelo OSI o TCP/IP. Si una capa realiza la encapsulación de datos, la misma capa en el nodo receptor realizará el proceso inverso, que se llama desencapsulación.

### Pregunta 13
Describa cuáles son las funciones de cada una de las capas del stack TCP/IP o protocolo de Internet.
- Aplicación: Proporciona servicios de red a las aplicaciones del usuario.
  Transporte: Proporciona comunicación extremo a extremo y control de flujo.
  Red: Determina la mejor ruta para los datos y los envía de un nodo a otro.
  Enlace: Proporciona la transmisión de datos entre dispositivos en una red local.

### Pregunta 14
Compare el modelo OSI con la implementación TCP/IP.
- El modelo OSI tiene 7 capas (Aplicación, Presentación, Sesión, Transporte, Red, Enlace de Datos y Física) mientras que TCP/IP tiene 4 capas (Aplicación, Transporte, Red e Interfaz de Red). Aunque ambos modelos tienen el mismo objetivo de facilitar la comunicación entre dispositivos, el modelo OSI es más teórico y detallado, mientras que TCP/IP es más práctico y es el que se utiliza en la realidad de Internet.
