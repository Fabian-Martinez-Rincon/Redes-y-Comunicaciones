# Práctica 1 Introducción

- [1. ¿Qué es una red? ¿Cuál es el principal objetivo para construir una red?](#1-¿qué-es-una-red-¿cuál-es-el-principal-objetivo-para-construir-una-red)
- [2. ¿Qué es Internet? Describa los principales componentes que permiten su funcionamiento.](#2-¿qué-es-internet-describa-los-principales-componentes-que-permiten-su-funcionamiento)
- [3. ¿Qué son las RFCs?](#3-¿qué-son-las-rfcs)
- [4. ¿Qué es un protocolo?](#4-¿qué-es-un-protocolo)
- [5. ¿Por qué dos máquinas con distintos sistemas operativos pueden formar parte de una misma red?](#5-¿por-qué-dos-máquinas-con-distintos-sistemas-operativos-pueden-formar-parte-de-una-misma-red)
- [6. ¿Cuáles son las 2 categorías en las que pueden clasificarse a los sistemas finales o End Systems? Dé un ejemplo del rol de cada uno en alguna aplicación distribuida que corra sobre Internet.](#6-¿cuáles-son-las-2-categorías-en-las-que-pueden-clasificarse-a-los-sistemas-finales-o-end-systems-dé-un-ejemplo-del-rol-de-cada-uno-en-alguna-aplicación-distribuida-que-corra-sobre-internet)
- [7. ¿Cuál es la diferencia entre una red conmutada de paquetes de una red conmutada de circuitos?](#7-¿cuál-es-la-diferencia-entre-una-red-conmutada-de-paquetes-de-una-red-conmutada-de-circuitos)
- [8. Analice qué tipo de red es una red de telefonía y qué tipo de red es Internet.](#8-analice-qué-tipo-de-red-es-una-red-de-telefonía-y-qué-tipo-de-red-es-internet)
- [9. Describa brevemente las distintas alternativas que conoce para acceder a Internet en su hogar.](#9-describa-brevemente-las-distintas-alternativas-que-conoce-para-acceder-a-internet-en-su-hogar)
- [10. ¿Qué ventajas tiene una implementación basada en capas o niveles?](#10-¿qué-ventajas-tiene-una-implementación-basada-en-capas-o-niveles)
- [11. ¿Cómo se llama la PDU de cada una de las siguientes capas: Aplicación, Transporte, Red y Enlace?](#11-¿cómo-se-llama-la-pdu-de-cada-una-de-las-siguientes-capas-aplicación-transporte-red-y-enlace)
- [12. ¿Qué es la encapsulación? Si una capa realiza la encapsulación de datos, ¿qué capa del nodo receptor realizará el proceso inverso?](#12-¿qué-es-la-encapsulación-si-una-capa-realiza-la-encapsulación-de-datos-¿qué-capa-del-nodo-receptor-realizará-el-proceso-inverso)
- [13. Describa cuáles son las funciones de cada una de las capas del stack TCP/IP o protocolo de Internet.](#13-describa-cuáles-son-las-funciones-de-cada-una-de-las-capas-del-stack-tcpip-o-protocolo-de-internet)
- [14. Compare el modelo OSI con la implementación TCP/IP.](#14-compare-el-modelo-osi-con-la-implementación-tcpip)

### **1)** ¿Qué es una red? ¿Cuál es el principal objetivo para construir una red

Se refiere a un conjunto de dispositivos interconectados que pueden comunicarse entre sí para compartir recursos, información y servicios. Estos dispositivos pueden incluir computadoras, servidores, enrutadores, conmutadores, dispositivos móviles y más. El objetivo principal de construir una red es permitir la comunicación eficiente y la colaboración entre estos dispositivos, lo que a su vez posibilita varias funcionalidades esenciales:

- **1)** **Compartir recursos:** Una red permite compartir recursos como archivos, impresoras, escáneres y otros dispositivos periféricos, lo que facilita el acceso y la utilización conjunta de estos recursos por parte de múltiples usuarios.
- **2)** **Comunicación:** Las redes permiten la comunicación rápida y eficiente entre dispositivos, lo que puede incluir el intercambio de datos, mensajes, correos electrónicos, llamadas telefónicas y videoconferencias.
- **3)** **Acceso a información:** Una red permite acceder a información almacenada en diferentes dispositivos o servidores, independientemente de su ubicación física. Esto es fundamental en entornos donde la información debe estar disponible para múltiples usuarios.
- **4)** **Colaboración:** La interconexión de dispositivos a través de una red facilita la colaboración en proyectos y tareas, permitiendo a diferentes usuarios trabajar juntos en documentos compartidos, aplicaciones y proyectos.
- **5)** **Acceso a Internet:** La mayoría de las redes están conectadas a Internet, lo que brinda acceso a una amplia gama de recursos en línea, como sitios web, servicios en la nube, redes sociales, etc.
- **6)** **Centralización de servicios:** En redes más grandes, es común centralizar servicios y recursos en servidores dedicados. Esto permite una administración y mantenimiento más eficientes de estos servicios.
- **7)** **Seguridad y control:** Una red puede implementar medidas de seguridad para controlar quién tiene acceso a qué recursos y datos. Esto es crucial para proteger la información sensible y mantener la integridad de la red.
- **8)** **Escalabilidad:** Las redes se pueden diseñar para ser escalables, lo que significa que pueden crecer y adaptarse a medida que aumenta el número de dispositivos y usuarios.
- **9)** **Reducción de costos:** Compartir recursos a través de una red puede reducir los costos, ya que no es necesario tener dispositivos duplicados para cada usuario.


### **2)** ¿Qué es Internet? Describa los principales componentes que permiten su funcionamiento

Internet es una red global de redes interconectadas que permite la comunicación y el intercambio de información a nivel mundial. Se compone de una vasta infraestructura tecnológica que involucra varios componentes clave para su funcionamiento. 

***Principales componentes que permiten el funcionamiento de Internet:***

- **1)** **Dispositivos Terminales:** Estos son los dispositivos con los que las personas interactúan directamente, como computadoras personales, laptops, tabletas, teléfonos inteligentes y dispositivos IoT (Internet de las cosas). Estos dispositivos se conectan a Internet para acceder a recursos y servicios.
- **2)** **Proveedores de Servicios de Internet (ISP):** Los ISP son empresas que brindan acceso a Internet a los usuarios. Ofrecen conexiones a través de tecnologías como líneas de banda ancha, cable, fibra óptica, satélite y más. Los ISP actúan como intermediarios entre los usuarios finales y la infraestructura de Internet.
- **3)** **Redes de Comunicación:** Estas redes incluyen una amplia variedad de tecnologías, como líneas de comunicación por cable (fibra óptica, cable coaxial), líneas telefónicas (DSL), comunicaciones inalámbricas (Wi-Fi, redes celulares) y enlaces satelitales. Estas redes permiten la transmisión de datos entre los dispositivos.
- **4)** **Protocolos de Comunicación:** Los protocolos son conjuntos de reglas y estándares que permiten que los dispositivos se comuniquen de manera efectiva. El protocolo fundamental de Internet es el Protocolo de Internet (IP), que se encarga de direccionar y enrutar los paquetes de datos a través de la red.
- **5)** **Routers y Conmutadores:** Estos dispositivos son esenciales para el enrutamiento de datos en la red. Los routers dirigen los paquetes de datos entre redes diferentes, mientras que los conmutadores gestionan la comunicación dentro de una red local.
- **6)** **Servidores:** Los servidores son computadoras de alta potencia que almacenan y sirven contenido a los usuarios. Pueden alojar sitios web, aplicaciones en línea, servicios de correo electrónico, bases de datos y más. Los servidores están conectados continuamente a la red y responden a las solicitudes de los usuarios.
- **7)** **Protocolo HTTP/HTTPS:** El Protocolo de Transferencia de Hipertexto (HTTP) y su versión segura, HTTPS, son protocolos que permiten la transferencia de contenido web entre los servidores y los navegadores web. Son esenciales para la navegación y el acceso a sitios web.
- **8)** **Nombres de Dominio:** Los nombres de dominio son las direcciones legibles por humanos que utilizamos para acceder a sitios web. Estos nombres se traducen en direcciones IP a través de un sistema de resolución de nombres, siendo el DNS (Sistema de Nombres de Dominio) el protocolo clave para esto.
- **9)** **Infraestructura de DNS:** La infraestructura de DNS incluye servidores de nombres que almacenan y distribuyen información sobre nombres de dominio y sus correspondientes direcciones IP. Esto permite que los usuarios ingresen nombres de dominio en lugar de direcciones IP numéricas.
- **10)** **Backbones de Internet:** Los backbones son las principales redes de alta velocidad que conectan diferentes regiones y países. Estas redes de fibra óptica y enlaces de alta capacidad forman la columna vertebral de Internet y facilitan la transferencia rápida de datos a nivel global.


### **3)** ¿Qué son las RFCs

Las RFCs, o "Request for Comments" (en español, "Solicitud de Comentarios"), son documentos publicados por la "Internet Engineering Task Force" (IETF) que describen estándares, protocolos, procedimientos y conceptos relacionados con Internet y las redes en general. Aunque el nombre sugiere que se trata de solicitudes de comentarios, en realidad, las RFCs son documentos técnicos que establecen estándares y especificaciones para la implementación y operación de tecnologías de Internet.

Las RFCs abarcan una amplia gama de temas, desde los protocolos fundamentales de Internet, como el Protocolo de Internet (IP) y el Protocolo de Control de Transmisión (TCP), hasta estándares más específicos, como el protocolo de correo electrónico (SMTP), el protocolo de transferencia de archivos (FTP), el Protocolo de Resolución de Nombres de Dominio (DNS) y muchos otros.

Cada RFC es numerada de manera única y se utiliza como referencia técnica en la comunidad de desarrollo y operación de redes. Estos documentos son redactados por expertos en el campo y pasan por un proceso de revisión y aprobación antes de ser publicados. A lo largo del tiempo, las RFCs pueden ser actualizadas, reemplazadas por nuevas versiones o incluso obsoletas si se desarrolla una tecnología mejor.

### **4)** ¿Qué es un protocolo

Un protocolo, en el contexto de las redes y las comunicaciones, es un conjunto de reglas y estándares que definen cómo deben comunicarse dos o más dispositivos para intercambiar información de manera efectiva y comprensible. Los protocolos son esenciales para garantizar que la comunicación entre dispositivos sea coherente, confiable y comprensible, ya que establecen el formato, el orden y las acciones que deben llevar a cabo los dispositivos durante la comunicación.

Los protocolos pueden abordar diversos aspectos de la comunicación, como el formato de los mensajes, la secuencia de acciones que deben seguirse, la detección y corrección de errores, la autenticación y la seguridad, entre otros. Los protocolos son utilizados en diversas áreas, como las redes de computadoras, Internet, telecomunicaciones, sistemas operativos y más.

***Algunos ejemplos de protocolos incluyen:***

- **1)** **Protocolo de Internet (IP):** Define cómo los datos deben ser direccionados y enrutados en una red, como en el caso de Internet. El IPv4 e IPv6 son ejemplos de versiones de este protocolo.
- **2)** **Protocolo de Control de Transmisión (TCP):** Proporciona una comunicación confiable y orientada a la conexión entre dispositivos. Divide los datos en segmentos y se encarga de su entrega y reordenamiento.
- **3)** **Protocolo de Transferencia de Hipertexto (HTTP):** Define cómo se solicitan y entregan páginas web a través de Internet. Establece la estructura de las solicitudes y respuestas entre navegadores web y servidores.
- **4)** **Protocolo de Correo Electrónico (SMTP y POP/IMAP):** SMTP (Protocolo Simple de Transferencia de Correo) se utiliza para enviar correos electrónicos, mientras que POP (Protocolo de Oficina de Correo) e IMAP (Protocolo de Acceso a Mensajes de Internet) se usan para recibirlos.
- **5)** **Protocolo de Resolución de Nombres de Dominio (DNS):** Traduce nombres de dominio legibles por humanos en direcciones IP numéricas, permitiendo que los dispositivos encuentren los servidores correctos en Internet.
- **6)** **Protocolo de Transferencia de Archivos (FTP):** Define cómo los archivos se pueden transferir entre sistemas a través de una red.
- **7)** **Protocolo de Seguridad SSL/TLS:** Utilizado para cifrar y asegurar las comunicaciones en línea, como en el caso de las transacciones financieras o el acceso a información confidencial.



### **5)** ¿Por qué dos máquinas con distintos sistemas operativos pueden formar parte de una misma red?

Dos máquinas con diferentes sistemas operativos pueden formar parte de una misma red debido a que las redes de computadoras se basan en estándares y protocolos universales que permiten la comunicación entre dispositivos heterogéneos. Esto significa que, independientemente de las diferencias en los sistemas operativos, los dispositivos pueden interactuar y compartir recursos en la red gracias a los siguientes motivos:
- **1)** **Estándares y Protocolos Universales:** Las redes utilizan protocolos de comunicación estándar, como el Protocolo de Internet (IP) y el Protocolo de Control de Transmisión (TCP), que están diseñados para ser independientes del sistema operativo. Esto permite que los dispositivos con diferentes sistemas operativos puedan entenderse entre sí.
- **2)** **Capa de Red y Capa de Transporte:** Los protocolos en las capas de red y transporte, como el IP y el TCP, actúan como intermediarios para el intercambio de datos entre dispositivos. Estos protocolos se centran en la forma en que los datos se empaquetan, se direccionan y se entregan, lo que no depende directamente del sistema operativo.
- **3)** **Protocolos de Aplicación:** Los protocolos de nivel de aplicación, como el Protocolo de Transferencia de Hipertexto (HTTP) o el Protocolo de Correo Electrónico (SMTP), también son independientes del sistema operativo subyacente. Estos protocolos definen cómo las aplicaciones se comunican y cómo se presentan los datos a los usuarios.
- **4)** **Interoperabilidad:** Los fabricantes de sistemas operativos y proveedores de hardware están interesados en garantizar la interoperabilidad, lo que significa que sus productos pueden funcionar juntos en una red. Esto impulsa la adopción de estándares abiertos y la implementación coherente de protocolos.
- **5)** **Cumplimiento de Normas y Estándares:** Tanto los sistemas operativos como las aplicaciones deben cumplir con ciertos estándares y especificaciones para ser parte de la infraestructura de Internet. Esto asegura que, incluso si los sistemas operativos son diferentes, sigan ciertas reglas comunes para interactuar en la red.

### **6)** ¿Cuáles son las 2 categorías en las que pueden clasificarse a los sistemas finales o End Systems? Dé un ejemplo del rol de cada uno en alguna aplicación distribuida que corra sobre Internet

Los sistemas finales, también conocidos como sistemas terminales o end systems, son los dispositivos que se encuentran en los extremos de una red de comunicación. Estos sistemas se pueden clasificar en dos categorías principales: sistemas cliente y sistemas servidor.

#### 1) **Sistemas Cliente:**
Los sistemas cliente son aquellos que solicitan y utilizan los recursos o servicios proporcionados por otros sistemas en la red. Los sistemas cliente inician solicitudes de comunicación y reciben respuestas de los sistemas servidores. Estos sistemas tienden a ser más interactivos y están diseñados para satisfacer las necesidades de los usuarios.

**Ejemplo en una aplicación distribuida:** Navegador web (cliente) y servidor web (servidor).

**Rol en la aplicación:** Imagina que estás utilizando un navegador web (cliente) para acceder a un sitio web. El navegador envía una solicitud al servidor web (servidor) para obtener la página solicitada. El servidor procesa la solicitud y envía la página web de regreso al navegador, que luego la muestra al usuario. En este caso, el navegador es el sistema cliente que solicita el recurso (la página web) al servidor, que es el sistema servidor que proporciona el recurso solicitado.

#### 2) **Sistemas Servidor:**
Los sistemas servidores son aquellos que proporcionan recursos, servicios o información a los sistemas clientes. Estos sistemas están diseñados para escuchar y responder a las solicitudes de los sistemas clientes. Los sistemas servidores a menudo operan de manera más continua y están optimizados para entregar contenido o servicios eficientemente.

**Ejemplo en una aplicación distribuida:** Servidor de correo electrónico (servidor) y aplicación de correo electrónico (cliente).

**Rol en la aplicación:** Cuando envías un correo electrónico desde una aplicación de correo electrónico (cliente), tu aplicación se conecta al servidor de correo electrónico (servidor) para enviar el correo. El servidor de correo electrónico almacena y entrega el mensaje a su destinatario. En este caso, el cliente (aplicación de correo electrónico) interactúa con el servidor de correo electrónico para enviar y recibir mensajes.


### **7)** ¿Cuál es la diferencia entre una red conmutada de paquetes de una red conmutada de circuitos
### **8)** Analice qué tipo de red es una red de telefonía y qué tipo de red es Internet
### **9)** Describa brevemente las distintas alternativas que conoce para acceder a Internet en su hogar
### **10)** ¿Qué ventajas tiene una implementación basada en capas o niveles
### **11)** ¿Cómo se llama la PDU de cada una de las siguientes capas: Aplicación, Transporte, Red y Enlace
### **12)** ¿Qué es la encapsulación? Si una capa realiza la encapsulación de datos, ¿qué capa del nodo receptor realizará el proceso inverso
### **13)** Describa cuáles son las funciones de cada una de las capas del stack TCP/IP o protocolo de Internet
### **14)** Compare el modelo OSI con la implementación TCP/IP