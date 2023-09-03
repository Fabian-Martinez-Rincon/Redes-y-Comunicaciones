<h1 align="center"> Práctica 2 Capa de Aplicación - HTTP</h1>

> Aclaracion: El dominio redes.unlp.edu.ar solo existe dentro de la VM provista por la cátedra, no es válido en Internet, lo que implica que todos los ejercicios de esta práctica y las siguientes en las que se utilice dicho domino solo podrán ser resueltos dentro dicha VM

- [El resto de las practicas](https://github.com/Fabian-Martinez-Rincon/Redes-y-Comunicaciones)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">


- [2) ¿Cuál es la función de la capa de aplicación?](#pregunta-2)
- [3) Si dos procesos deben comunicarse](#pregunta-3)
- [4) Explique brevemente cómo es el modelo Cliente/Servidor](#pregunta-4)
- [5) Describa la funcionalidad de la entidad genérica "Agente de usuario" o "User agent"](#pregunta-5)
- [6) Observe el indice de la RFC2616, busque el apartado donde se describe el requerimiento y la respuesta.](#pregunta-6)
- [7) Utilizando la VM, abra una terminal e investigue sobre el comando curl](#pregunta-7)
- [8) Ejecute el comando curl sin ningún parámetro adicional y acceda a www.redes.unlp.edu.ar](#pregunta-8)
- [9) Ejecute a continuación los siguientes comandos](#pregunta-9)
- [10) Investigue cómo define las cabeceras la RFC](#pregunta-10)
- [11) Utilizando curl, realice un requerimiento con el método HEAD al sitio www.redes.unlp.edu.ar e indique](#pregunta-11)
- [12) En HTTP/1.0, ¿cómo sabe el cliente que ya recibió todo el objeto solicitado completamente?](#pregunta-12)
- [13) Investigue los distintos tipos de códigos de retorno de un servidor web y su significado en la RFC](#pregunta-13)
- [14) Utilizando curl, acceda al sitio www.redes.unlp.edu.ar/restringido/index.php ](#pregunta-14)
- [15) Utilizando la VM, realice las siguientes pruebas](#pregunta-15)
- [16) En base a lo obtenido en el ejercicio anterior, responda](#pregunta-16)
- [17) En el siguiente ejercicio veremos la diferencia entre los métodos POST y GET.](#pregunta-17)
- [18) HTTP es un protocolo stateless, para sortear esta carencia muchos servicios](#pregunta-18)
- [19) ¿Cuál es la diferencia entre un protocolo binario y uno basado en texto? ](#pregunta-19)
- [20) nalice de que se tratan las siguientes características de HTTP/2:]()
- [21) Responder las siguientes preguntas](#pregunta-21)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">


#### Pregunta 2

***¿Cuál es la función de la capa de aplicación?***

La capa de aplicación es donde las aplicaciones de red y sus protocolos residen, es la capa que hace de interfaz entre los ususarios finales y el resto de la red.


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 3

Si dos procesos deben comunicarse:

***¿Cómo podrían hacerlo si están en diferentes máquinas?***

Si están en diferentes máquinas, ambos procesos usan sockets que se asocia a un puerto, el cual sirve para enviar o recibir datos entre las máquinas correspondientes.

***Y si están en la misma máquina, ¿qué alternativas existen?***

Si están en la misma máquina, pueden usar los mecanismos provistos por sistema operativo basandose en su pid para identificarse

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 4

***Explique brevemente cómo es el modelo Cliente/Servidor***

El modelo Cliente/Servidor tiene dos participantes. Un cliente hace peticiones a un servidor quien es el que va a responder a esas peticiones. Dichas peticiones pueden ser tanto de envío como de recpción de información. Generalmente si bien un servidor puede responder a multiples clientes, los clientes no interactuan entre sí.

***De un ejemplo de un sistema Cliente/Servidor en la “vida cotidiana”*** 

Un ejemplo de eso sería Netflix, al cual nuestro cliente web o browser le realizará peticiones como, el catálogo de películas, la imagen y el video de las películas, etc.

***Un ejemplo de un sistema informático que siga el modelo Cliente/Servidor.***

Si nos referimos a sistemas específicos, por ejemplo, el email sería un buen caso de estudio, ya que tenemos un servidor de mails que almacena la bandeja de los clientes y envía los mails a sus destinatarios.

Otros ejemplos de modelos serían el peer to peer, en el cual tenemos dos usuarios en un mismo escalafón, comunicandosé y el bittorrent protocol, en el cual tendremos seeders(poseedores del archivo completo) y leechers(posdedores del archivo parcial), a los cuales nos conectaremos para poder descargar el archivo

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 5

Describa la funcionalidad de la entidad genérica **Agente de usuario** o **User agent**

Esta es una linea del header que indica el tipo de programa que hizo el pedido.
Por ejemplo: Mozilla/5.0. Esta línea nos sirve para poder diferenciar y enviar distinto contenido dependiendo de la aplicación, por ejemplo para distintos navegadores con distintas versiones o soporte de herramientas, con la misma URL.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 6

Observe el indice de la RFC2616, busque el apartado donde se describe el requerimiento y la respuesta.

***¿Qué son y en qué se diferencian HTML y HTTP?***

**HTML o HyperText Markup Language** es un lenguaje de marcas usado para dar estructura a las páginas web.

**HTTP o HyperText Tranfer Protocol** es un protocolo de capa de aplicaion utilizado para comunicar dos programas, un cliente y un servidor; HTTP define los mensajes http de la comunicación y como se intercambian.

***¿En que entidad ubicaría a HTML?***

El ámbito de las tecnologías web o de redes, HTML generalmente se ubicaría en la capa de aplicación si hablamos del modelo OSI.


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 7

Utilizando la VM, abra una terminal e investigue sobre el comando curl. Analice para qué sirven los siguientes parámetros (-I, -H, -X, -s)

***Comando `curl`***

`curl` es una herramienta de línea de comandos que permite hacer solicitudes a servidores usando diferentes protocolos, como HTTP, FTP y muchos más. Es muy útil para pruebas de APIs, descargas automatizadas de archivos y muchas otras tareas relacionadas con transferencia de datos a través de redes.

***Parámetros de `curl`***

**`-I`**: Este parámetro le dice a `curl` que realice una solicitud HTTP HEAD para obtener solamente los encabezados HTTP del recurso especificado. Es útil cuando quieres ver metadatos sobre un recurso web sin descargar todo el contenido.

```bash
curl -I http://example.com
```

**`-H`**: Se utiliza para añadir un encabezado personalizado a la solicitud HTTP. Esto es útil, por ejemplo, cuando se necesita pasar un token de autenticación.

```bash
curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" http://example.com
```

**`-X`**: Con este parámetro puedes especificar un método de solicitud HTTP personalizado, como GET, POST, PUT, DELETE, etc.


```bash
curl -X POST http://example.com
```

**`-s`**: Este es el modo "silencioso". Al usar este parámetro, `curl` no muestra ningún mensaje de error ni información sobre el progreso de la transferencia, haciendo que la salida sea más limpia si todo va bien.

```bash
curl -s http://example.com
```


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 8

Ejecute el comando curl sin ningún parámetro adicional y acceda a www.redes.unlp.edu.ar. Luego res- ponda:

a. ***¿Cuántos requerimientos realizó y qué recibió?*** 
Pruebe redirigiendo la salida(>)del comando curl a un archivo con extensión html y abrirlo con un navegador.

Se realizará un solo requerimiento `HTTP GET` para descargar el HTML de la página. No se descargarán recursos adicionales como imágenes, CSS o archivos JavaScript. Al redirigir la salida a un archivo HTML y abrirlo con un navegador, verás solo el HTML sin los recursos adicionales.

b. ***¿Cómo funcionan los atributos href de los tags link e img en html?***

Crea un enlace a otras páginas de internet, archivos o ubicaciones dentro de la misma página, direcciones de correo, o cualquier otra URL


c. ***Para visualizar la página completa con imágenes como en un navegador, ¿alcanza con realizar un único requerimiento?*** 

No, un solo requerimiento con `curl` solo obtendrá el HTML principal de la página. No descargarás otros recursos como imágenes, CSS y archivos JavaScript.

***¿Cuántos requerimientos serían necesarios para obtener una página que tiene dos CSS, dos Javascript y tres imágenes?*** 

Para una página que tiene dos CSS, dos JavaScript y tres imágenes, necesitarías realizar 8 requerimientos en total: uno para el HTML principal, dos para los archivos CSS, dos para los archivos JavaScript y tres para las imágenes.

***Diferencie como funcionaría un navegador respecto al comando curl ejecutado previamente***

<table><tr><td>Navegador</td><td>Curl</td></tr>
<tr><td>

Un navegador web generalmente realiza todos estos requerimientos automáticamente para renderizar la página completa. Esto incluye descargar todos los recursos vinculados en el HTML como imágenes, archivos CSS, y archivos JavaScript.
</td><td>

Por otro lado, con `curl` tendrías que hacer cada uno de estos requerimientos manualmente si quisieras obtener todos los recursos para visualizar la página de manera completa fuera de un navegador.
</td></tr>
</table>

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 9

Ejecute a continuación los siguientes comandos:

**Comando**

```shell
curl -v -s www.redes.unlp.edu.ar > /dev/null
```

**Salida**

```shell
*   Trying 172.28.0.50:80...
* Connected to www.redes.unlp.edu.ar (172.28.0.50) port 80 (#0)
> GET / HTTP/1.1
> Host: www.redes.unlp.edu.ar
> User-Agent: curl/7.74.0
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Date: Sun, 03 Sep 2023 15:20:27 GMT
< Server: Apache/2.4.56 (Unix)
< Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
< ETag: "1322-5f7457bd64f80"
< Accept-Ranges: bytes
< Content-Length: 4898
< Content-Type: text/html
< 
{ [4898 bytes data]
* Connection #0 to host www.redes.unlp.edu.ar left intact
```

**Comando**

```shell
curl -I -v -s www.redes.unlp.edu.ar
```

**Salida**

Quiero preguntar, porque es basicamente lo mismo pero con los datos duplicados abajo

```shell
*   Trying 172.28.0.50:80...
* Connected to www.redes.unlp.edu.ar (172.28.0.50) port 80 (#0)
> HEAD / HTTP/1.1
> Host: www.redes.unlp.edu.ar
> User-Agent: curl/7.74.0
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
HTTP/1.1 200 OK
< Date: Sun, 03 Sep 2023 15:23:45 GMT
Date: Sun, 03 Sep 2023 15:23:45 GMT
< Server: Apache/2.4.56 (Unix)
Server: Apache/2.4.56 (Unix)
< Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
< ETag: "1322-5f7457bd64f80"
ETag: "1322-5f7457bd64f80"
< Accept-Ranges: bytes
Accept-Ranges: bytes
< Content-Length: 4898
Content-Length: 4898
< Content-Type: text/html
Content-Type: text/html

< 
* Connection #0 to host www.redes.unlp.edu.ar left intact
```

***Explicación de los Comandos***

<table>
<tr><td>Primer Comando</td><td>Segundo Comando</td></tr>

<tr><td>

`-v`: Modo detallado (verbose). Muestra información detallada sobre la transferencia.
`-s`: Modo silencioso. Oculta el progreso y los mensajes de error.
`> /dev/null`: Redirige la salida al "agujero negro" `/dev/null`, básicamente descartando cualquier dato descargado.

</td><td>

`-I`: Recupera solo los encabezados HTTP.
`-v`: Modo detallado.
`-s`: Modo silencioso.
</td></tr>
</table>





Observe la salida y luego repita la prueba, pero previamente inicie una nueva captura en wireshark.

***Uso de Wireshark***

Si usas Wireshark para capturar el tráfico de red mientras ejecutas estos comandos, podrás ver todo el tráfico HTTP entre tu computadora y `www.redes.unlp.edu.ar`.

***Utilice la opción Follow Stream.***

Con la opción "Follow Stream" en Wireshark, puedes seguir una única conversación TCP entre tu máquina y el servidor.

***¿Qué se transmitió en cada caso?***

<table>
<tr><td>Primer Comando</td><td>Segundo comando</td></tr>

<tr><td>

En el primer comando, se transmitirá todo el contenido HTML de la página, aunque no lo verás en la terminal debido a `-s` y `> /dev/null`.
</td><td>

En el segundo comando, solo se transmitirán los encabezados HTTP debido a la opción `-I`.
</td></tr>
</table>


***¿A que se debió esta diferencia entre lo que se transmitió y lo que se mostró en pantalla?***

<table>
<tr><td>Primer Comando</td><td>Segundo Comando</td></tr>
<tr><td>

En el primer caso, aunque todo el contenido HTML se transmite, no ves nada en la terminal debido a la redirección a `/dev/null`.

</td><td>

En el segundo caso, aunque estás en modo silencioso y modo detallado al mismo tiempo, el comando está configurado para mostrar solo los encabezados HTTP, así que eso es lo que deberías ver.
</td></tr>
</table>

Si repites estos comandos mientras capturas el tráfico con Wireshark, verás la evidencia de esta actividad a nivel de paquete, lo cual puede ser muy instructivo para entender cómo funcionan las cosas "bajo el capó".


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 10

***Investigue cómo define las cabeceras la RFC.***

La RFC (Request for Comments) que define las cabeceras HTTP es la RFC 7231 para HTTP/1.1 y es parte de un conjunto de documentos que describen todo el protocolo HTTP. Esta RFC define las cabeceras estándar que se pueden usar en las peticiones y respuestas HTTP.

***a. ¿Establece todas las cabeceras posibles?.***

No, la RFC 7231 no establece todas las cabeceras posibles. Define un conjunto de cabeceras estándar, pero los desarrolladores y proveedores de servicios web pueden definir sus propias cabeceras personalizadas si es necesario. Las cabeceras personalizadas suelen empezar con "X-", aunque esta convención se está volviendo menos común.

***b. ¿Cuántas cabeceras viajaron en el requerimiento y en la respuesta del ejercicio anterior?***

Las siguientes cabeceras viajaron en el requerimiento:

1. Host
2. User-Agent
3. Accept

Y en la respuesta:

1. Date
2. Server
3. Last-Modified
4. ETag
5. Accept-Ranges
6. Content-Length
7. Content-Type

En el requerimiento viajaron 3 cabeceras y en la respuesta 7 cabeceras.

***c. ¿La cabecera Date es una de las definidas en la RFC? ¿Qué indica?***


Sí, la cabecera "Date" está definida en la RFC 7231. Esta cabecera representa la fecha y hora en que el mensaje fue enviado. La fecha y hora se presentan en un formato específico, como lo indica la RFC. Este campo es especialmente útil para el control de caché y para comprender cuándo se generó o modificó un recurso específico.


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 11

Utilizando curl, realice un requerimiento con el método HEAD al sitio www.redes.unlp.edu.ar e indique:

Tenemos que ejecutar el siguiente comando

```shell
curl -I www.redes.unlp.edu.ar
```

```shell
HTTP/1.1 200 OK
Date: Sun, 03 Sep 2023 16:02:57 GMT
Server: Apache/2.4.56 (Unix)
Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
ETag: "1322-5f7457bd64f80"
Accept-Ranges: bytes
Content-Length: 4898
Content-Type: text/html
```

***a. ¿Qué información brinda la primer línea de la respuesta?***

La primera línea "HTTP/1.1 200 OK" indica que se está utilizando el protocolo HTTP versión 1.1 y que la solicitud fue exitosa, representada por el código de estado 200 ("OK").

***b. ¿Cuántos encabezados muestra la respuesta?***

Hay 7 encabezados en la respuesta: Date, Server, Last-Modified, ETag, Accept-Ranges, Content-Length, y Content-Type.

***c. ¿Qué servidor web está sirviendo la página?***

El servidor web que sirve la página es Apache, versión 2.4.56, corriendo en Unix. Esto se puede ver en el encabezado "Server: Apache/2.4.56 (Unix)".


***d. ¿El acceso a la página solicitada fue exitoso o no?***

El acceso fue exitoso, como lo indica el código de estado 200 ("OK") en la primera línea de la respuesta.

***e. ¿Cuándo fue la última vez que se modificó la página?***

La última vez que se modificó la página fue el 19 de marzo de 2023, a las 19:04:46 GMT. Esto se puede ver en el encabezado "Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT".

***f. Solicite la página nuevamente con curl usando GET, pero esta vez indique que quiere obtenerla sólo si la misma fue modificada en una fecha posterior a la que efectivamente fue modificada.***

***¿Cómo lo hace?***

Para solicitar la página sólo si ha sido modificada después de una fecha específica, puedes utilizar el encabezado `If-Modified-Since` en tu solicitud `GET` con `curl`. Este encabezado le dice al servidor que sólo devuelva el recurso si ha sido modificado después de la fecha especificada.

Por ejemplo, la última vez que la página fue modificada, según la información que tienes, fue el "Sun, 19 Mar 2023 19:04:46 GMT". Puedes realizar una solicitud `GET` utilizando `curl` como sigue:

```bash
curl -H "If-Modified-Since: Sun, 19 Mar 2023 20:00:00 GMT" -v www.redes.unlp.edu.ar
```

***¿Qué resultado obtuvo?***

```shell
*   Trying 172.28.0.50:80...
* Connected to www.redes.unlp.edu.ar (172.28.0.50) port 80 (#0)
> GET / HTTP/1.1
> Host: www.redes.unlp.edu.ar
> User-Agent: curl/7.74.0
> Accept: */*
> If-Modified-Since: Sun, 19 Mar 2023 20:00:00 GMT
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 304 Not Modified
< Date: Sun, 03 Sep 2023 16:22:07 GMT
< Server: Apache/2.4.56 (Unix)
< Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
< ETag: "1322-5f7457bd64f80"
< Accept-Ranges: bytes
< 
* Connection #0 to host www.redes.unlp.edu.ar left intact
```

La respuesta del servidor fue "HTTP/1.1 304 Not Modified", lo cual indica que la página no ha sido modificada desde la fecha y hora que especificaste en el encabezado "If-Modified-Since". Esto es exactamente lo que esperaríamos si estamos usando el encabezado "If-Modified-Since" correctamente.

***¿Puede explicar para qué sirve?***

El encabezado **If-Modified-Since** es útil para optimizar el ancho de banda y mejorar la velocidad de la carga de la página. Si el recurso no ha sido modificado desde la última vez que fue solicitado, se puede cargar desde la caché del cliente en lugar de descargarse de nuevo desde el servidor, ahorrando tiempo y recursos tanto para el cliente como para el servidor.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 12

En HTTP/1.0, ¿cómo sabe el cliente que ya recibió todo el objeto solicitado completamente? ¿Y en HTTP/1.1?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 13

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 14

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 15

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 16

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 17

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 18

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 19

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 20

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 21