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

En HTTP/1.0, 

¿cómo sabe el cliente que ya recibió todo el objeto solicitado completamente?¿Y en HTTP/1.1?

<table><tr><td>HTTP/1.0</td><td>HTTP/1.1</td></tr>

<tr><td>

el cliente generalmente sabe que ha recibido todo el objeto cuando el servidor cierra la conexión. También se puede utilizar el encabezado `Content-Length` si está presente.
</td><td>

el encabezado `Content-Length` o `Transfer-Encoding: chunked` se utilizan con más frecuencia para indicar cuándo se ha completado la transmisión del objeto, permitiendo que la conexión se mantenga abierta para solicitudes adicionales.
</td></tr>
</table>

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 13

Investigue los distintos tipos de códigos de retorno de un servidor web y su significado en la RFC.

Los códigos de estado HTTP están definidos en varias RFC, incluida la RFC 2616 para HTTP/1.1. Estos códigos se agrupan en varias clases, indicadas por el primer dígito del código:

1. **1xx**: Respuestas Informativas
2. **2xx**: Éxito (por ejemplo, 200 OK, 201 Created)
3. **3xx**: Redirección (por ejemplo, 301 Moved Permanently, 302 Found)
4. **4xx**: Errores del Cliente (por ejemplo, 400 Bad Request, 404 Not Found)
5. **5xx**: Errores del Servidor (por ejemplo, 500 Internal Server Error, 503 Service Unavailable)

***¿Qué parte se ve principalmente interesada de esta información, cliente o servidor?***

Los códigos de estado son más útiles para el cliente, ya que informan al cliente sobre el resultado de su solicitud. Un navegador web o una aplicación cliente pueden usar estos códigos para decidir cómo continuar.

***¿Es útil que esté detallado y clasificado en la RFC?.***

Sí, es muy útil que los códigos de estado estén bien definidos y clasificados en la RFC. Proporciona un estándar que todos los desarrolladores y administradores de sistemas pueden seguir. Esto ayuda a garantizar una interpretación coherente y permite una mejor depuración y registro.

***Dentro de la VM, ejecute los siguientes comandos y evalue el estado que recibe.***

**Primer Comando**

```shell
curl -I http://unlp.edu.ar
```

```shell
HTTP/1.1 301 Moved Permanently
Server: nginx/1.18.0
Date: Sun, 03 Sep 2023 17:40:18 GMT
Content-Type: text/html
Content-Length: 169
Connection: keep-alive
Location: https://unlp.edu.ar/
```

- `HTTP/1.1 301 Moved Permanently`: Este es un código de estado HTTP que significa que el recurso que estás intentando acceder se ha trasladado de forma permanente a una nueva URL. La nueva URL se especifica en el campo `Location`.
- `Server: nginx/1.18.0`: Indica que el servidor web que está sirviendo la página es Nginx versión 1.18.0.
- `Date: Sun, 03 Sep 2023 17:40:18 GMT`: Fecha y hora en la que se produjo la respuesta.
- `Content-Type: text/html`: Indica que el tipo de contenido es HTML.
- `Content-Length: 169`: Longitud del contenido en bytes.
- `Connection: keep-alive`: Sugiere que la conexión se mantenga abierta para futuras solicitudes.
- `Location: https://unlp.edu.ar/`: La nueva URL a la que se ha trasladado el recurso.

En resumen, si intentas acceder a `http://unlp.edu.ar`, serás redirigido de forma permanente a `https://unlp.edu.ar/`.

**Segundo Comando**

```shell
curl -I www.redes.unlp.edu.ar/restringido/index.php
```

```shell
HTTP/1.1 401 Unauthorized
Date: Sun, 03 Sep 2023 17:45:45 GMT
Server: Apache/2.4.56 (Unix)
WWW-Authenticate: Basic realm="Authentication Required"
Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
ETag: "cb-5f7457bd64f80"
Accept-Ranges: bytes
Content-Length: 203
Content-Type: text/html
```

- **HTTP/1.1 401 Unauthorized**: Esto es un código de estado HTTP que indica que el servidor espera que el cliente proporcione credenciales, o que las credenciales proporcionadas no son válidas.
- **Date**: La fecha y la hora en que se generó la respuesta.
- **Server**: Indica el software utilizado por el servidor HTTP de origen, en este caso, Apache versión 2.4.56 en Unix.
- **WWW-Authenticate: Basic realm="Authentication Required"**: Este es un desafío enviado al agente del usuario (el navegador, en la mayoría de los casos) que solicita al usuario un nombre de usuario y una contraseña. El "realm" es una descripción del área protegida. Si el usuario agente desea enviar las credenciales de autenticación, deberá hacerlo en el encabezado de autenticación correspondiente.
- **Last-Modified**: La última fecha en que se modificó el recurso solicitado.
- **ETag**: Un identificador único para una versión específica del recurso.
- **Accept-Ranges**: Indica si el servidor admite solicitudes de rango para el recurso.
- **Content-Length**: La longitud del cuerpo de la respuesta en bytes.
- **Content-Type**: El tipo de medio del recurso o datos.

En resumen, parece que estás intentando acceder a un recurso que requiere autenticación. El servidor espera que el cliente (normalmente, tu navegador) proporcione un nombre de usuario y una contraseña válidos para acceder a ese recurso.

**Tercer Comando**

```shell
curl -I www.redes.unlp.edu.ar/noexiste
```

```shell
HTTP/1.1 404 Not Found
Date: Sun, 03 Sep 2023 17:51:18 GMT
Server: Apache/2.4.56 (Unix)
Content-Type: text/html; charset=iso-8859-1
```

- **HTTP/1.1 404 Not Found**: Este es el código de estado HTTP que indica que el recurso solicitado no pudo ser encontrado en el servidor.
- **Date**: La fecha y la hora en que se generó la respuesta.
- **Server**: Indica el software utilizado por el servidor HTTP de origen, en este caso, Apache versión 2.4.56 en Unix.
- **Content-Type**: El tipo de medio del recurso o datos. Aquí, se indica que es un documento HTML con codificación de caracteres iso-8859-1.

En resumen, el recurso que estás intentando acceder no existe en el servidor, y por eso recibes un `404 Not Found`. Este es uno de los códigos de estado más comunes y se utiliza para indicar que el servidor no puede encontrar el recurso especificado en la URL.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 14

Utilizando curl, acceda al sitio www.redes.unlp.edu.ar/restringido/index.php y siga las instrucciones y las pistas que vaya recibiendo hasta obtener la respuesta final. Será de utilidad para resolver este ejercicio poder analizar tanto el contenido de cada página como los encabezados

**Paso 1**

```shell
curl http://www.redes.unlp.edu.ar/restringido/index.php
```

```html
<h1>Acceso restringido</h1>
<p>Para acceder al contenido es necesario autenticarse.
Para obtener los datos de acceso seguir las instrucciones
detalladas en www.redes.unlp.edu.ar/obtener-usuario.php</p>
```

**Paso 2**

```shell
curl www.redes.unlp.edu.ar/obtener-usuario.php
```
```html
<p>Para obtener el usuario y la contraseña haga un requerimiento
 a esta página seteando el encabezado 'Usuario-Redes' con el valor 'obtener'</p>
```

**Paso 3**

```shell
curl -H "Usuario-Redes:obtener" www.redes.unlp.edu.ar/obtener-usuario.php
```
```html
<p>Bien hecho! Los datos para ingresar son: 

Usuario: redes
Contraseña: RYC

Ahora vuelva a acceder a la página inicial con los datos anteriores.
PISTA: Investigue el uso del encabezado Authorization para el método Basic.
El comando base64 puede ser de ayuda!</p>
```

**Paso 4**

```shell
echo -n "redes:RYC" | base64
# Devuelve: cmVkZXM6UllD
```

**Paso 5**

```shell
curl -H "Authorization: Basic cmVkZXM6UllD" http://www.redes.unlp.edu.ar/restringido/index.php
```

```html
<h1>Excelente!</h1>

<p>Para terminar el ejercicio deberás agregar en la entrega 
los datos que se muestran en la siguiente página.</p>
<p>ACLARACIÓN: la URL de la siguiente página está contenida en esta misma respuesta.</p>
```

**Paso 6**

```shell
curl -I -H "Authorization: Basic cmVkZXM6UllD" http://www.redes.unlp.edu.ar/restringido/index.php
```

```shell
HTTP/1.1 302 Found
Date: Sun, 03 Sep 2023 18:27:18 GMT
Server: Apache/2.4.56 (Unix)
X-Powered-By: PHP/7.4.33
Location: http://www.redes.unlp.edu.ar/restringido/the-end.php
Content-Type: text/html; charset=UTF-8
```

**Paso 7**

```shell
curl -H "Authorization: Basic cmVkZXM6UllD" http://www.redes.unlp.edu.ar/restringido/the-end.php
```
```
¡Felicitaciones, llegaste al final del ejercicio! 

Fecha: 2023-09-03 18:30:11
```

Estuvo bastante entretenido el ejercicio :D

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 15

Utilizando la VM, realice las siguientes pruebas:

**a. Ejecute el comando ’curl www.redes.unlp.edu.ar/extras/prueba-http-1-0.txt’ y copie la salida completa (incluyendo los dos saltos de linea del final).**

```shell
curl -v www.redes.unlp.edu.ar/extras/prueba-http-1-0.txt
```

```shell
*   Trying 172.28.0.50:80...
* Connected to www.redes.unlp.edu.ar (172.28.0.50) port 80 (#0)
> GET /extras/prueba-http-1-0.txt HTTP/1.1
> Host: www.redes.unlp.edu.ar
> User-Agent: curl/7.74.0
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Date: Sun, 03 Sep 2023 18:42:59 GMT
< Server: Apache/2.4.56 (Unix)
< Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
< ETag: "60-5f7457bd64f80"
< Accept-Ranges: bytes
< Content-Length: 96
< Content-Type: text/plain
< 
GET /http/HTTP-1.1/ HTTP/1.0
User-Agent: curl/7.38.0
Host: www.redes.unlp.edu.ar
Accept: */*

* Connection #0 to host www.redes.unlp.edu.ar left intact
```

1. `HTTP/1.1 200 OK`: Indica que la solicitud fue exitosa.
2. `Server: Apache/2.4.56 (Unix)`: El servidor que sirve el recurso está utilizando Apache versión 2.4.56 en un sistema Unix.
3. `Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT`: La última vez que se modificó el recurso fue el 19 de marzo de 2023.
4. `Content-Length: 96`: El tamaño del contenido es de 96 bytes.
5. `Content-Type: text/plain`: El tipo de contenido es texto sin formato.

El cuerpo de la respuesta es un texto que parece una solicitud HTTP en sí misma:

```plaintext
GET /http/HTTP-1.1/ HTTP/1.0
User-Agent: curl/7.38.0
Host: www.redes.unlp.edu.ar
Accept: */*
```

Este contenido es probablemente parte del ejercicio, pero es confuso ver una "solicitud HTTP" como contenido en una respuesta a una solicitud HTTP.

**b. Desde la consola ejecute el comando telnet www.redes.unlp.edu.ar 80 y luego pegue el contenido que tiene almacenado en el portapapeles. ¿Qué ocurre luego de hacerlo?**

```shell
`telnet www.redes.unlp.edu.ar 80`
```

Una vez que la conexión esté establecida, pegue el contenido que obtuvo de la URL `/extras/prueba-http-1-0.txt` y presione Enter dos veces para enviar la solicitud.

Recuerde que `telnet` es muy sensible al formato, así que asegúrese de copiar y pegar la solicitud HTTP correctamente.

```html
Trying 172.28.0.50...
Connected to www.redes.unlp.edu.ar.
Escape character is '^]'.
GET /http/HTTP-1.1/ HTTP/1.0
User-Agent: curl/7.38.0
Host: www.redes.unlp.edu.ar
Accept: */*

HTTP/1.1 200 OK
Date: Sun, 03 Sep 2023 19:12:25 GMT
Server: Apache/2.4.56 (Unix)
Last-Modified: Sun, 19 Mar 2023 19:04:46 GMT
ETag: "760-5f7457bd64f80"
Accept-Ranges: bytes
Content-Length: 1888
Connection: close
Content-Type: text/html

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Protocolo HTTP: versiones</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="">
    <meta name="author" content="">

    <!-- Le styles -->
    <link href="../../bootstrap/css/bootstrap.css" rel="stylesheet">
    <link href="../../css/style.css" rel="stylesheet">
    <link href="../../bootstrap/css/bootstrap-responsive.css" rel="stylesheet">

    <!-- HTML5 shim, for IE6-8 support of HTML5 elements -->
    <!--[if lt IE 9]>
      <script src="./bootstrap/js/html5shiv.js"></script>
    <![endif]-->
  </head>

  <body>


    <div id="wrap">
        
    <div class="navbar navbar-inverse navbar-fixed-top">
      <div class="navbar-inner">
        <div class="container">
          <a class="brand" href="../../index.html"><i class="icon-home icon-white"></i></a>
          <a class="brand" href="https://catedras.info.unlp.edu.ar" target="_blank">Redes y Comunicaciones</a>
          <a class="brand" href="http://www.info.unlp.edu.ar" target="_blank">Facultad de Inform&aacute;tica</a>
          <a class="brand" href="http://www.unlp.edu.ar" target="_blank">UNLP</a>
        </div>
      </div>
    </div>

    <div class="container">
    <h1>Ejemplo del protocolo HTTP 1.1</h1>
    <p>
        Esta p&aacute;gina se visualiza utilizando HTTP 1.1. Utilizando el capturador
        de paquetes analice cuantos flujos utiliza el navegador para visualizar la p&
        aacute;gina con sus im&aacute;genes en contraposici&oacute;n con el protocolo 
        HTTP/1.0.
    </p>
    </p>
    <h2>Imagen de ejemplo</h2>
    <img src="13532-tuxkiller03green.png" width="800px"/>
    </div> 
    
    
    </div>
    <div id="footer">
      <div class="container">
        <p class="muted credit">Redes y Comunicaciones</p>
      </div>
    </div>
  </body>
</html>
Connection closed by foreign host.
```

El uso del comando `telnet` muestra cómo establecer una conexión manual con un servidor web y enviar una solicitud HTTP. En este caso, la conexión fue exitosa, como lo indica la respuesta `HTTP/1.1 200 OK` del servidor. La conexión se cerró después de completar la transacción, lo cual es típico del protocolo HTTP/1.0. Esta forma de interactuar con servidores web es básica y generalmente se utiliza para fines de diagnóstico o educativos.

**c. Repita el proceso anterior, pero copiando la salida del recurso /extras/prueba-http-1-1.txt. Verifique que debería poder pegar varias veces el mismo contenido sin tener que ejecutar telnet nuevamente.**

Es lo mismo perono se cierra de forma inmediata * preguntar

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 16

En base a lo obtenido en el ejercicio anterior, responda:

***¿Qué está haciendo al ejecutar el comando telnet? ¿Qué lo diferencia con curl?***

<table>
<tr><td>Telnet</td><td>Curl</td></tr>
<tr><td>

Cuando ejecutas el comando `telnet`, estás estableciendo una conexión de red cruda con el servidor en un puerto específico, en este caso, el puerto 80 para HTTP. Una vez que se establece la conexión, puedes enviar comandos de texto crudo y recibir respuestas del servidor. `telnet` es más bajo nivel y requiere que escribas manualmente las solicitudes HTTP.

</td><td>

`curl`, por otro lado, es una herramienta de línea de comandos que transfiere datos con URL y entiende HTTP. Realiza automáticamente muchas de las cosas que tendrías que hacer manualmente con `telnet`, como enviar el método GET, establecer encabezados, y más.
</td></tr>
</table>


***Observe la definición de método y recurso en la RFC. Luego responda, ¿Qué método HTTP utilizó?***

En los ejemplos anteriores, se utilizó el método HTTP `GET`, que es el método más común para solicitar un recurso del servidor.

***¿Qué recurso solicitó?***

Se solicitó el recurso `/extras/prueba-http-1-0.txt` en el primer caso y `/extras/prueba-http-1-1.txt` en el segundo caso, ambos desde el dominio `www.redes.unlp.edu.ar`.

***¿Qué diferencias notó entre los dos casos? ¿Puede explicar por qué?***

Uno de los principales cambios entre HTTP/1.0 y HTTP/1.1 es la persistencia de la conexión. En HTTP/1.0, la conexión generalmente se cierra después de una sola solicitud/resistencia. En HTTP/1.1, la conexión puede ser "persistente", permitiendo múltiples solicitudes y respuestas en la misma conexión. Esto a menudo hace que HTTP/1.1 sea más eficiente porque reutiliza la conexión existente, evitando el costo de tiempo y recursos para establecer una nueva conexión para cada solicitud.


***¿Cuál de los dos casos le parece más eficiente? Piense en el ejercicio donde analizó la cantidad de requerimientos necesarios para obtener una página con estilos, javascripts e imágenes.***

HTTP/1.1 generalmente es más eficiente debido a la persistencia de la conexión, lo cual es especialmente útil cuando se cargan páginas web con múltiples recursos como imágenes, hojas de estilo, y scripts de JavaScript.

***El caso elegido, ¿puede traer asociado algún problema?***

Si bien HTTP/1.1 es más eficiente en términos de recursos de red y tiempo debido a las conexiones persistentes, también podría llevar a problemas como el agotamiento de recursos si demasiadas conexiones se mantienen abiertas pero inactivas durante demasiado tiempo. Además, el uso de conexiones persistentes podría complicar el diseño del servidor, ya que necesita ser capaz de manejar múltiples solicitudes en una sola conexión de manera efectiva.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 17

En el siguiente ejercicio veremos la diferencia entre los métodos POST y GET. Para ello, será necesario utilizar la VM y la herramienta Wireshark. Antes de iniciar considere

- Capture los paquetes utilizando la interfaz con IP 172.28.0.1. (Menú “Capture ->Options”. Luego seleccione la interfaz correspondiente y presione Start).

- Para que el analizador de red sólo nos muestre los mensajes del protocolo http introduciremos la cadena ‘http’ (sin las comillas) en la ventana de especificación de filtros de visualización (display-filter). Si no hiciéramos esto veríamos todo el tráfico que es capaz de capturar nuestra placa de red. De los paquetes que son capturados, aquel que esté seleccionado será mostrado en forma detallada en la sección que está justo debajo. Como sólo estamos interesados en http ocultaremos toda la información que no es relevante para esta práctica (Información de trama, Ethernet, IP y TCP). Desplegar la información correspondiente al protocolo HTTP bajo la leyenda “Hypertext Transfer Protocol”.
- Para borrar la cache del navegador, deberá ir al menu “Herramientas->Borrar historial reciente”. Alternativamente puede utilizar Ctrl+F5 en el navegador para forzar la petición HTTP evitando el uso de caché del navegador.
- En caso de querer ver de forma simplificada el contenido de una comunicación http, utilice el botón derecho sobre un paquete HTTP perteneciente al flujo capturado y seleccione la opción Follow TCP Stream

**a. Abra un navegador e ingrese a la URL: www.redes.unlp.edu.ar e ingrese al link en la sección “Capa de Aplicación” llamado “Métodos HTTP”. En la página mostrada se visualizan dos nuevos links llamados: Método GET y Método POST. Ambos muestran un formulario como el siguiente:**

***b. Analice el código HTML.***

***c. Utilizando el analizador de paquetes Wireshark capture los paquetes enviados y recibidos al presionar el botón Enviar.***

***d. ¿Qué diferencias detectó en los mensajes enviados por el cliente?***

***e. ¿Observó alguna diferencia en el browser si se utiliza un mensaje u otro?***

> Este ejercicio me lo voy a guardar para hacer en clase

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 18

HTTP es un protocolo stateless, para sortear esta carencia muchos servicios se apoyan en el uso de Cookies. 

***¿En qué RFC se definió dicha funcionalidad?***

Las cookies en HTTP están definidas en varias RFC (Request for Comments), pero la más actual y pertinente es la RFC 6265, que se titula "HTTP State Management Mechanism". Esta RFC fue publicada en abril de 2011 y describe cómo los servidores web pueden establecer cookies y cómo se gestionan y almacenan en el navegador web.

***Investigue cuál es el principal uso que se le da a Set-Cookie y Cookie en HTTP.***

<table><tr><td>Set-Cookie</td><td>Cookie</td></tr>

<tr><td>

Cuando un servidor web responde a una solicitud HTTP, puede incluir un encabezado `Set-Cookie`. Este encabezado instruye al navegador para almacenar la cookie y el valor asignado. 
</td><td>

Una vez que el navegador ha almacenado una cookie, la enviará de vuelta al servidor cada vez que realice una nueva solicitud al mismo dominio, usando el encabezado `Cookie`. 
</td></tr>
</table>

Set Cookie ejemplo:

```shell
Set-Cookie: sessionId=abc123; Path=/; Expires=Wed, 09 Jun 2021 10:18:14 GMT
```

Aquí, el servidor le está diciendo al navegador que guarde una cookie llamada `sessionId` con el valor `abc123`. También se establecen atributos adicionales como el "Path" y "Expires".

Cookie ejemplo:

```shell
Cookie: sessionId=abc123
```

El servidor puede entonces utilizar esta cookie para recuperar el estado del cliente, como la información de inicio de sesión, preferencias, etc.

***¿Qué atributo de la RFC original fue en parte aprovechado para la implementación?***


La implementación de cookies se basa en gran parte en el atributo "SetCookie" de la RFC original (RFC 2109), que se centraba en establecer cookies y manejar su formato. Sin embargo, la RFC 6265 se introdujo para corregir algunas deficiencias y ambigüedades en el enfoque anterior y para mejorar la seguridad y la privacidad en el uso de cookies

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 19

***¿Cuál es la diferencia entre un protocolo binario y uno basado en texto?***

<table>
<tr><td>Protocolo Basado en Texto</td><td>Protocolo Binario</td></tr>

<tr><td>

**Legible por Humanos**: Los mensajes se codifican en un formato de texto que generalmente es legible para los humanos.

**Menos Eficiente**: Dado que los datos se transmiten como texto, suelen ser menos eficientes en términos de tamaño y velocidad en comparación con los protocolos binarios.

**Fácil de Depurar**: Los protocolos basados en texto son más fáciles de depurar y diagnosticar debido a su legibilidad.

**Ejemplos**: HTTP/1.0, HTTP/1.1, SMTP, FTP, etc.


</td><td>

**No Legible por Humanos**: Los mensajes se codifican en un formato binario que no es legible para los humanos.

**Más Eficiente**: Generalmente más eficiente en términos de tamaño y velocidad, ya que los datos son más compactos.

**Complejidad en Depuración**: Puede ser más difícil de depurar y diagnosticar problemas debido a su falta de legibilidad.

**Ejemplos**: Protocol Buffers, HTTP/2, WebSockets en modo binario, etc.

</td></tr>
</table>


***¿de que tipo de protocolo se trata HTTP/1.0, HTTP/1.1 y HTTP/2?***

<table>
<tr><td>HTTP/1.0</td><td>HTTP/1.1</td><td>HTTP/2</td><tr>

<tr><td>

Es un protocolo basado en texto. Fue uno de los primeros protocolos de la capa de aplicación diseñados para la World Wide Web.
</td><td>

También es un protocolo basado en texto y es una extensión de HTTP/1.0. Introduce varias mejoras como conexiones persistentes y chunked transfer encoding, pero sigue siendo fundamentalmente un protocolo basado en texto.
</td><td>

Este es un protocolo binario. Fue desarrollado para superar las deficiencias de rendimiento en HTTP/1.x al minimizar la latencia, permitiendo múltiples intercambios de mensajes simultáneos en la misma conexión.
</td><tr>
</table>


En resumen, tanto HTTP/1.0 como HTTP/1.1 son protocolos basados en texto, mientras que HTTP/2 es un protocolo binario. HTTP/2 ofrece varias ventajas de rendimiento sobre sus predecesores, pero la adopción de un formato binario hace que no sea directamente legible por humanos como las versiones anteriores.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 20

Analice de que se tratan las siguientes características de HTTP/2: stream, frame, server-push

- **Stream**: Permite múltiples interacciones cliente-servidor en una única conexión TCP, mejorando la eficiencia.
- **Frame**: Son las unidades básicas de comunicación en HTTP/2 y ayudan en la multiplexación de los streams.
- **Server-Push**: El servidor puede enviar recursos al cliente proactivamente, reduciendo la necesidad de múltiples solicitudes y mejorando la velocidad de carga.

Estas características hacen que HTTP/2 sea más rápido y eficiente en comparación con sus predecesores.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

#### Pregunta 21

Responder las siguientes preguntas:

***a. ¿Qué función cumple la cabecera Host en HTTP 1.1?***

La cabecera "Host" es utilizada en HTTP/1.1 para especificar el dominio al cual se está enviando la petición. Esto permite que múltiples dominios puedan compartir una única dirección IP.

***¿Existía en HTTP 1.0?***

No era obligatorio en HTTP/1.0, pero en HTTP/1.1 se hizo obligatorio para resolver el problema de alojar múltiples sitios web en una única dirección IP.

***¿Qué sucede en HTTP/2?***

En HTTP/2, el concepto de la cabecera "Host" se mantiene para la compatibilidad, pero generalmente se entrega una vez al establecer la conexión y se reutiliza para solicitudes adicionales.

b. ¿Cómo quedaría en HTTP/2 el siguiente pedido realizado en HTTP/1.1 si se está usando https?

```shell
GET /index.php HTTP/1.1
Host: www.info.unlp.edu.ar
```

En HTTP/2, la información de la solicitud se envía como un conjunto de "frames" dentro de un "stream". Estos "frames" pueden contener la misma información que las cabeceras en HTTP/1.1 pero en un formato más eficiente.

Si estuvieras haciendo la misma solicitud usando HTTP/2 sobre HTTPS, la petición `GET /index.php HTTP/1.1` se dividiría en un frame de cabecera en un stream específico. El "Host" se convertiría en una de las cabeceras en este frame y seguiría siendo `www.info.unlp.edu.ar`.

No hay una forma textual simple de representar esto como en HTTP/1.1, ya que HTTP/2 utiliza un formato binario. Sin embargo, conceptualmente, la petición es similar pero más eficiente en cuanto a la utilización de la red.