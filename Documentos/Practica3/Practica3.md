<h1 align="center"> Práctica 3 Capa de Aplicación - DNS</h1>

- [El resto de las practicas](https://github.com/Fabian-Martinez-Rincon/Redes-y-Comunicaciones)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

- [Ejercicio 1 Investigue y describa cómo funciona el DNS. ¿Cuál es su objetivo?](#ejercicio-1)
- [Ejercicio 2 ¿Qué es un root server? ¿Qué es un generic top-level domain (gtld)?](#ejercicio-2)
- [Ejercicio 3 ¿Qué es una respuesta del tipo autoritativa?](#ejercicio-3)
- [Ejercicio 4 ¿Qué diferencia una consulta DNS recursiva de una iterativa?](#ejercicio-4)
- [Ejercicio 5 ¿Qué es el resolver?](#ejercicio-5)
- [Ejercicio 6 Describa para qué se utilizan los siguientes tipos de registros de DNS:](#ejercicio-6)
- [Ejercicio 7 En Internet, un dominio suele tener más de un servidor DNS. ¿Por qué cree que esto es así?](#ejercicio-7)
- [Ejercicio 8 Cuando un dominio cuenta con más de un servidor](#ejercicio-8)
- [Ejercicio 9 Explique brevemente en qué consiste el mecanismo de transferencia de zona y cuál es su finalidad.](#ejercicio-9)
- [Ejercicio 10 Imagine que usted es el administrador del dominio de DNS de la UNLP](#ejercicio-10)
- [Ejercicio 11 Responda y justifique los siguientes ejercicios](#ejercicio-11)
- [Ejercicio 12 Investigue los comando nslookup y host. ¿Para qué sirven?](#ejercicio-12)
- [Ejercicio 13 ¿Qué función cumple en Linux/Unix el archivo /etc/hosts](#ejercicio-13)
- [Ejercicio 14 Abra el programa Wireshark para comenzar a capturar el tráfico de red](#ejercicio-14)
- [Ejercicio 15 Dada la siguiente situación](#ejercicio-15)
- [Ejercicio 16 Relacione DNS con HTTP. ¿Se puede navegar si no hay servicio de DNS?](#ejercicio-16)
- [Ejercicio 17 Observar el siguiente gráfico y contestar](#ejercicio-17)
- [Ejercicio 18 ¿A quién debería consultar para que la respuesta sobre www.google.com sea autoritativa?](#ejercicio-18)
- [Ejercicio 19 ¿Qué sucede si al servidor elegido en el paso anterior se lo consulta por www.info.unlp.edu.ar?](#ejercicio-19)
- [Ejercicio 20 En base a la siguiente salida de dig, conteste las consignas.](#ejercicio-20-ejercicio-de-parcial)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 1

***Investigue y describa cómo funciona el DNS. ¿Cuál es su objetivo?***

El Sistema de Nombres de Dominio (DNS, por sus siglas en inglés) es un sistema jerárquico y descentralizado que se encarga de traducir nombres de dominio legibles por humanos en direcciones IP, que son legibles por máquinas. Este proceso facilita la navegación en la web, ya que los usuarios no tienen que recordar direcciones IP numéricas para acceder a sitios web y otros recursos en línea.


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 2
***¿Qué es un root server?***

Un servidor raíz (root server) en el contexto de DNS (Sistema de Nombres de Dominio) es un servidor que contiene la información básica y autoritativa necesaria para resolver nombres de dominio de nivel superior (como `.com`, `.org`, `.net`, etc.). 

Estos servidores no contienen toda la información para cada dominio, pero pueden dirigir las consultas del servidor DNS recursivo hacia el servidor de nombres de dominio de nivel superior (TLD) que tenga la información más específica.

***¿Qué es un generic top-level domain (gTLD)?***

Un dominio de nivel superior genérico (gTLD, por sus siglas en inglés) es una de las categorías de dominios de nivel superior (TLDs) mantenidas por la Corporación de Asignación de Nombres y Números de Internet (ICANN). Los gTLD son una de las varias clases de TLDs, que también incluyen dominios de nivel superior de código de país (ccTLDs), como `.uk` para el Reino Unido o `.de` para Alemania.

Los gTLD incluyen dominios como `.com`, `.org`, `.net`, así como dominios más nuevos y específicos como `.app`, `.blog`, `.guru`, etc. Originalmente, los gTLD se crearon para representar una función o un tipo de organización (por ejemplo, `.com` para empresas comerciales, `.org` para organizaciones sin fines de lucro), pero con la expansión del espacio de nombres de dominio, estos se han vuelto mucho más variados y menos restrictivos en su uso.


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 3

***¿Qué es una respuesta del tipo autoritativa?***

En el contexto del Sistema de Nombres de Dominio (DNS), una respuesta autoritativa es aquella que proviene de un servidor que tiene autoridad sobre el dominio consultado. En otras palabras, el servidor DNS tiene información directa y precisa sobre el recurso solicitado, y esa información se considera "autoritativa" o definitiva.

Cuando un servidor DNS recursivo realiza una consulta para resolver un nombre de dominio, puede recibir diferentes tipos de respuestas.

<table><tr><td>Autoritativo</td><td>No Autoritativo</td></tr><tr><td>

 Una respuesta autoritativa generalmente viene del servidor DNS que es autoridad para el dominio específico o subdominio en la consulta. Esta respuesta es el resultado final y se considera precisa y fiable. A menudo, el servidor DNS recursivo almacenará esta respuesta en su caché para acelerar futuras consultas del mismo recurso.
</td><td>

Por el contrario, una respuesta no autoritativa es aquella que ha sido obtenida de la caché de un servidor DNS o que ha sido reenviada desde otro servidor pero no proviene del servidor autoritativo para ese dominio. Aunque estas respuestas son generalmente precisas y se pueden usar para resolver consultas, no se consideran definitivas en la misma manera que una respuesta autoritativa.
</td>
</tr>
</table>

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 4

**¿Qué diferencia una consulta DNS recursiva de una iterativa?**

La diferencia principal entre una consulta DNS recursiva y una consulta DNS iterativa está en cómo se maneja la resolución del nombre de dominio a lo largo de la cadena de servidores DNS. A continuación, se describen ambas:

<table><tr><td>Consulta DNS Recursiva</td><td>Consulta DNS Iterativa</td></tr>
<tr><td>

1. **Cliente → Servidor DNS Recursivo:** El cliente envía una solicitud al servidor DNS recursivo para resolver un nombre de dominio.

2. **Servidor DNS Recursivo → Otros servidores DNS:** Si el servidor DNS recursivo no tiene la respuesta en su caché, toma la responsabilidad de consultar a otros servidores DNS (servidor raíz, TLD, servidor autoritativo, etc.) hasta obtener la respuesta.

3. **Servidor DNS Recursivo → Cliente:** Una vez que el servidor DNS recursivo tiene la respuesta, la devuelve al cliente.

En una consulta recursiva, el servidor DNS recursivo hace todo el trabajo pesado en nombre del cliente, y el cliente solo interactúa con este servidor.
</td><td>

1. **Cliente → Servidor DNS:** El cliente envía una solicitud al servidor DNS para resolver un nombre de dominio.

2. **Servidor DNS → Cliente:** Si el servidor DNS no tiene la respuesta, devuelve una referencia al servidor DNS que podría tenerla (por ejemplo, un servidor DNS de nivel superior o autoritativo).

3. **Cliente → Otro servidor DNS:** El cliente, luego, debe consultar al nuevo servidor DNS y repetir el proceso hasta obtener la respuesta.

En una consulta iterativa, el cliente tiene que hacer múltiples rondas de preguntas a diferentes servidores DNS hasta obtener la respuesta final. 
</td></tr>
</table>

**Resumen**

- **Recursiva:** El servidor DNS recursivo se encarga de todo y devuelve la respuesta final al cliente.
- **Iterativa:** El cliente tiene que seguir haciendo consultas a diferentes servidores DNS hasta obtener la respuesta final.

Ambas consultas tienen sus ventajas y desventajas, y se utilizan en diferentes escenarios según las necesidades.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 5

**¿Qué es el resolver?**

En el contexto de DNS (Sistema de Nombres de Dominio), el "resolver" o resolutor es una biblioteca de software o componente del sistema que inicia y recibe las consultas para traducir nombres de dominio en direcciones IP. Este es esencialmente el primer paso en el proceso de resolución de nombres DNS y generalmente es parte del sistema operativo de un equipo, aunque también puede ser implementado en aplicaciones específicas.

Cuando una aplicación necesita resolver un nombre de dominio (por ejemplo, cuando se accede a un sitio web a través de un navegador), la solicitud se envía al resolver del sistema. El resolver luego:

1. Verifica si la respuesta ya está almacenada en su caché local.
2. Si no se encuentra en la caché, el resolver envía una consulta a un servidor DNS para obtener la información necesaria.
3. Una vez que recibe la información, la almacena en la caché para futuras consultas y pasa la información a la aplicación que hizo la solicitud original.

El resolver es responsable de iniciar las consultas que pueden ser iterativas o recursivas, como se describió en la respuesta anterior. También maneja otros aspectos, como el tiempo de vida (TTL) de la información en la caché para asegurarse de que los datos estén relativamente actualizados.

En resumen, el resolver actúa como un cliente en el sistema de DNS, iniciando las consultas para obtener la información de resolución de nombres necesaria para las aplicaciones y servicios.



<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 6

Describa para qué se utilizan los siguientes tipos de registros de DNS:



***a. A (Address Record)***
Este registro se usa para traducir nombres de dominios en direcciones IP versión 4 (IPv4). Por ejemplo, si tienes un dominio como `ejemplo.com`, el registro A apuntaría a la dirección IPv4 donde se aloja el sitio web.

***b. MX (Mail Exchange)***
Estos registros son utilizados para definir los servidores de correo que son responsables de recibir mensajes de correo electrónico en nombre de un dominio. Generalmente apuntan a un dominio de un servidor de correo y utilizan una preferencia numérica para indicar el orden de uso.

***c. PTR (Pointer Record)***
Utilizado para realizar una búsqueda inversa de DNS. Es decir, traduce una dirección IP en un nombre de dominio. Este tipo de registros se utiliza comúnmente para actividades como verificación de correo electrónico para asegurarse de que la dirección IP esté realmente asociada con el dominio en cuestión.

***d. AAAA (IPv6 Address Record)***
Similar al registro A, pero para direcciones IPv6 en lugar de IPv4. Indica la dirección IPv6 a la que apunta un nombre de dominio.

***e. SRV (Service Record)***
Este registro especifica datos sobre servicios disponibles, lo que permite un control más detallado sobre el tráfico de red para aplicaciones como SIP y XMPP. Los registros SRV definen el protocolo, el puerto y el dominio de un servicio específico.

***f. NS (Name Server)***
Define qué servidores DNS son autoritativos para un dominio o subdominio. Estos son los servidores a los que se les pedirá información sobre el dominio en cuestión.

***g. CNAME (Canonical Name)***
Se utiliza para alias de nombres de dominio. Por ejemplo, `www.ejemplo.com` podría ser un CNAME que apunta a `ejemplo.com`.

***h. SOA (Start of Authority)***
Este registro contiene información administrativa sobre el dominio, incluido el servidor DNS autoritativo principal. También incluye detalles como cuándo se actualizó por última vez el dominio, cuánto tiempo deben esperar los otros servidores para actualizar sus registros en caché, etc.

***i. TXT (Text Record)***
Utilizado para almacenar información de texto que puede ser utilizada para varios propósitos, como la verificación de propiedad del dominio, registros SPF para correo electrónico y otros metadatos.

Cada uno de estos registros tiene su propio propósito específico y juega un papel en cómo funciona la red y cómo se resuelven los nombres de dominio.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 7

En Internet, un dominio suele tener más de un servidor DNS. ¿Por qué cree que esto es así?

Tener múltiples servidores DNS para un dominio es una práctica común y recomendada por varias razones:

***Redundancia y Alta Disponibilidad***
Si un servidor DNS falla o se cae por algún motivo, los servidores DNS adicionales pueden continuar resolviendo las solicitudes. Esto garantiza una alta disponibilidad y resistencia contra fallos.

***Balanceo de Carga***
Distribuir las solicitudes de resolución de nombres entre múltiples servidores puede ayudar a equilibrar la carga, asegurando que ninguno de los servidores DNS se sature de tráfico.

***Distribución Geográfica***
Los servidores DNS a menudo están distribuidos geográficamente. Esto permite que las solicitudes de los usuarios se dirijan al servidor más cercano, reduciendo la latencia y acelerando el tiempo de resolución.

***Mitigación de Ataques DDoS***
Tener múltiples servidores puede ayudar a mitigar los efectos de un ataque de Denegación de Servicio Distribuido (DDoS). Si un servidor se ve comprometido, los otros aún pueden continuar funcionando.

***Actualizaciones y Mantenimiento***
Con múltiples servidores, es más fácil realizar tareas de mantenimiento o actualizaciones en un servidor a la vez sin afectar la disponibilidad del servicio.

***Coherencia de Datos***
La replicación entre servidores DNS asegura que los datos estén sincronizados. Esto es especialmente importante para los grandes dominios que necesitan garantizar que la información más reciente esté disponible en todos los servidores de manera oportuna.

En resumen, tener múltiples servidores DNS mejora la resiliencia, el rendimiento y la seguridad del sistema de nombres de dominio.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 8

Cuando un dominio cuenta con más de un servidor, uno de ellos es el primario (o maestro) y todos los demás son los secundarios (o esclavos). ¿Cuál es la razón de que sea así?

La distinción entre un servidor DNS primario (o maestro) y servidores secundarios (o esclavos) se hace por diversas razones, principalmente relacionadas con la gestión de datos, la coherencia, la eficiencia y la seguridad. Aquí hay algunas razones por las que se hace esta distinción:

***Centralización del Control***
Tener un servidor primario permite un punto centralizado de administración. Los cambios en los registros DNS se realizan primero en el servidor primario, lo que facilita la gestión y minimiza la posibilidad de errores o inconsistencias que podrían surgir si se permitieran cambios en múltiples lugares.

***Coherencia de Datos***
Una vez que los cambios son realizados en el servidor primario, estos se replican a los servidores secundarios. Esto asegura la coherencia y uniformidad de los registros DNS a través de todos los servidores, y garantiza que todos los usuarios obtengan la misma información cuando realicen una consulta DNS.

***Carga de Trabajo y Eficiencia***
El servidor primario se encarga de gestionar los cambios y actualizaciones, mientras que los servidores secundarios se encargan principalmente de responder a las consultas DNS. Esta división de responsabilidades ayuda a distribuir la carga de trabajo y a hacer más eficiente la resolución de nombres.

***Seguridad***
Limitar las actualizaciones a un servidor primario puede mejorar la seguridad al restringir los puntos que podrían ser vulnerables a ataques o errores de configuración. Los servidores secundarios pueden ser configurados para que solo acepten actualizaciones del servidor primario, lo que añade una capa adicional de seguridad.

***Tolerancia a Fallos***
Si el servidor primario falla o necesita ser retirado para mantenimiento, los servidores secundarios pueden continuar proporcionando servicios de resolución de nombres. Además, muchas configuraciones permiten que un servidor secundario sea promovido a primario en caso de fallo del servidor primario original.

***Reducción de Latencia y Proximidad Geográfica***
Los servidores secundarios suelen estar distribuidos geográficamente y pueden ser optimizados para servir a usuarios en ubicaciones específicas más rápidamente que si todas las solicitudes tuvieran que ser dirigidas al servidor primario.

En resumen, la arquitectura de tener un servidor DNS primario y varios secundarios ofrece beneficios en términos de administración, coherencia de datos, eficiencia, seguridad y tolerancia a fallos.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 9

Explique brevemente en qué consiste el mecanismo de transferencia de zona y cuál es su finalidad.

El mecanismo de transferencia de zona en el sistema DNS (Sistema de Nombres de Dominio) es el proceso mediante el cual un servidor DNS secundario actualiza su base de datos de registros DNS al obtener una copia del servidor DNS primario o maestro. Este proceso asegura que todos los servidores involucrados en la resolución de nombres de un dominio tengan la misma información actualizada.

***Finalidad***

1. **Sincronización de Datos**: Este mecanismo permite que los servidores DNS secundarios tengan siempre la versión más actualizada de los registros, igual que el servidor DNS primario.
  
2. **Redundancia**: Al contar con varios servidores que contienen la misma información, se aumenta la disponibilidad del servicio. Si uno de los servidores falla, otros pueden tomar su lugar.

3. **Balanceo de Carga**: Al distribuir las consultas entre varios servidores, se optimiza la utilización de los recursos y se mejora la eficiencia del sistema.

En resumen, la transferencia de zona es esencial para mantener la coherencia de la información en los servidores DNS, mejorar la disponibilidad del servicio y permitir un balanceo de carga efectivo.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 10

Imagine que usted es el administrador del dominio de DNS de la UNLP (unlp.edu.ar). A su vez, cada facultad de la UNLP cuenta con un administrador que gestiona su propio dominio (por ejemplo, en el caso de la Facultad de Informática se trata de info.unlp.edu.ar). Suponga que se crea una nueva facultad, Facultad de Redes, cuyo dominio será redes.unlp.edu.ar, y el administrador le indica que quiere poder manejar su propio dominio. 

***¿Qué debe hacer usted para que el administrador de la Facultad de Redes pueda gestionar el dominio de forma independiente?***

> (Pista: investigue en qué consiste la delegación de dominios).

Para permitir que el administrador de la nueva Facultad de Redes pueda gestionar el dominio "redes.unlp.edu.ar" de forma independiente, lo que tendría que hacer es configurar una "delegación de dominio". La delegación de dominio en DNS es el proceso mediante el cual se asigna la autoridad para gestionar las configuraciones DNS de un subdominio a un servidor DNS diferente al del dominio principal. 

#### Pasos a seguir

1. **Registrar el subdominio**: En primer lugar, debería registrar el subdominio "redes.unlp.edu.ar" en el servidor DNS maestro (primario) de "unlp.edu.ar".

2. **Definir servidores autoritativos**: Especificar qué servidores DNS serán los autoritativos para el subdominio "redes.unlp.edu.ar". Estos servidores serán administrados por el equipo de IT de la Facultad de Redes.

3. **Crear Registros NS**: En el servidor DNS maestro de "unlp.edu.ar", debería crear registros NS (Name Server) para el subdominio "redes.unlp.edu.ar", apuntando a los servidores DNS que serán autoritativos para este subdominio.

4. **Traspaso de autoridad**: Al crear los registros NS, automáticamente se está delegando la autoridad de ese subdominio a los servidores DNS especificados. Ahora, cualquier consulta DNS relacionada con "redes.unlp.edu.ar" será redirigida a estos servidores.

5. **Informar al Administrador**: Una vez que la delegación esté completa, se deberá informar al administrador de la Facultad de Redes para que comience a configurar los registros DNS en su servidor autoritativo.

6. **Comprobación**: Finalmente, es recomendable verificar que la delegación se ha realizado correctamente, realizando consultas DNS para asegurarse de que se resuelven según lo esperado.

Siguiendo estos pasos, el administrador de la Facultad de Redes debería ser capaz de gestionar el dominio "redes.unlp.edu.ar" de manera independiente, sin afectar ni ser afectado por los demás dominios bajo "unlp.edu.ar".

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 11

Responda y justifique los siguientes ejercicios

**a. En la VM, utilice el comando dig para obtener la dirección IP del host www.redes.unlp.edu.ar y responda:**

```shell
dig www.redes.unlp.edu.ar
```

```shell

; <<>> DiG 9.16.27-Debian <<>> www.redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 36782
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 185dc42f85b63c9d0100000064fdcfac68c835c6fd358cc7 (good)
;; QUESTION SECTION:
;www.redes.unlp.edu.ar.		IN	A

;; ANSWER SECTION:
www.redes.unlp.edu.ar.	300	IN	A	172.28.0.50

;; Query time: 0 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 11:16:12 -03 2023
;; MSG SIZE  rcvd: 94
```

- El estado de la consulta (`status: NOERROR`) muestra que la operación se completó con éxito.
- Se realizó una única consulta (`QUERY: 1`) y se recibió una única respuesta (`ANSWER: 1`).
- La sección `ANSWER SECTION` proporciona la información más relevante: el dominio `www.redes.unlp.edu.ar` tiene asignada la dirección IP `172.28.0.50`.
- El tiempo de consulta (`Query time: 0 msec`) muestra que la consulta se completó en 0 milisegundos, lo cual es muy rápido. Este dato puede ser especialmente útil para diagnosticar problemas de rendimiento.
- La información del servidor (`SERVER: 172.28.0.29#53`) muestra el servidor DNS que proporcionó la respuesta.

En resumen, ahora sabes que la dirección IP para el dominio `www.redes.unlp.edu.ar` es `172.28.0.50`.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**b. ¿Cuáles son los servidores de DNS del dominio redes.unlp.edu.ar?**

```shell
dig NS redes.unlp.edu.ar
```

```shell
; <<>> DiG 9.16.27-Debian <<>> NS redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 65119
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 3

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: af458ba0aa5ecef00100000064fdd0ee9d21cca65848f141 (good)
;; QUESTION SECTION:
;redes.unlp.edu.ar.		IN	NS

;; ANSWER SECTION:
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-a.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-b.redes.unlp.edu.ar.

;; ADDITIONAL SECTION:
ns-sv-a.redes.unlp.edu.ar. 604800 IN	A	172.28.0.30
ns-sv-b.redes.unlp.edu.ar. 604800 IN	A	172.28.0.29

;; Query time: 0 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 11:21:34 -03 2023
;; MSG SIZE  rcvd: 150
```

La salida que obtuviste del comando `dig NS redes.unlp.edu.ar` indica que el dominio `redes.unlp.edu.ar` tiene dos servidores DNS:

1. `ns-sv-a.redes.unlp.edu.ar` con dirección IP `172.28.0.30`
2. `ns-sv-b.redes.unlp.edu.ar` con dirección IP `172.28.0.29`

Estos son los servidores de nombres (Name Servers, NS) responsables de resolver las consultas DNS para el dominio `redes.unlp.edu.ar`. Están listados en la sección "ANSWER SECTION" de la salida del comando `dig`.

Los números `86400` en la "ANSWER SECTION" representan el tiempo en segundos que se debe mantener en caché la información sobre estos servidores DNS.

La sección "ADDITIONAL SECTION" proporciona información adicional como las direcciones IP asociadas a cada uno de estos servidores de nombres.

Este tipo de configuración, donde hay más de un servidor DNS, es común para garantizar la alta disponibilidad y la tolerancia a fallos del servicio de DNS para el dominio.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**c. Repita la consulta anterior cuatro veces más. ¿Qué observa? ¿Puede explicar a qué se debe?**

<table>
<tr><td>

```shell
; <<>> DiG 9.16.27-Debian <<>> NS redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 61478
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 3

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 03573ddaf69749c70100000064fdd1ca14286dbfd0c51aca (good)
;; QUESTION SECTION:
;redes.unlp.edu.ar.		IN	NS

;; ANSWER SECTION:
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-a.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-b.redes.unlp.edu.ar.

;; ADDITIONAL SECTION:
ns-sv-a.redes.unlp.edu.ar. 604800 IN	A	172.28.0.30
ns-sv-b.redes.unlp.edu.ar. 604800 IN	A	172.28.0.29

;; Query time: 4 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 11:25:14 -03 2023
;; MSG SIZE  rcvd: 150
```

</td><td>

```shell
; <<>> DiG 9.16.27-Debian <<>> NS redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 49771
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 3

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 974a0db8ffccc0480100000064fdd1cbae941f1844e49f8b (good)
;; QUESTION SECTION:
;redes.unlp.edu.ar.		IN	NS

;; ANSWER SECTION:
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-a.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-b.redes.unlp.edu.ar.

;; ADDITIONAL SECTION:
ns-sv-a.redes.unlp.edu.ar. 604800 IN	A	172.28.0.30
ns-sv-b.redes.unlp.edu.ar. 604800 IN	A	172.28.0.29

;; Query time: 0 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 11:25:15 -03 2023
;; MSG SIZE  rcvd: 150
```

</td></tr>
<tr><td>

```shell
; <<>> DiG 9.16.27-Debian <<>> NS redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 14037
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 3

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: a0aee5d279f893700100000064fdd1cd531bce7bcec1152f (good)
;; QUESTION SECTION:
;redes.unlp.edu.ar.		IN	NS

;; ANSWER SECTION:
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-a.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-b.redes.unlp.edu.ar.

;; ADDITIONAL SECTION:
ns-sv-a.redes.unlp.edu.ar. 604800 IN	A	172.28.0.30
ns-sv-b.redes.unlp.edu.ar. 604800 IN	A	172.28.0.29

;; Query time: 0 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 11:25:17 -03 2023
;; MSG SIZE  rcvd: 150
```

</td><td>

```shell
; <<>> DiG 9.16.27-Debian <<>> NS redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 2317
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 3

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 5d27906fc8651c0f0100000064fdd1ce5d03b4ea2b6aeae3 (good)
;; QUESTION SECTION:
;redes.unlp.edu.ar.		IN	NS

;; ANSWER SECTION:
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-b.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-a.redes.unlp.edu.ar.

;; ADDITIONAL SECTION:
ns-sv-a.redes.unlp.edu.ar. 604800 IN	A	172.28.0.30
ns-sv-b.redes.unlp.edu.ar. 604800 IN	A	172.28.0.29

;; Query time: 4 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 11:25:18 -03 2023
;; MSG SIZE  rcvd: 150
```

</td></tr>
</table>


1. **Consistencia en los Servidores de Nombres**: Los servidores de nombres reportados son consistentes en todas las consultas. Se mantienen como `ns-sv-a.redes.unlp.edu.ar` y `ns-sv-b.redes.unlp.edu.ar`.

2. **Direcciones IP Adicionales**: La sección "ADDITIONAL SECTION" también muestra las direcciones IP de estos servidores de nombres, y estas también son consistentes (`172.28.0.30` y `172.28.0.29`).

3. **Tiempo de Consulta (Query time)**: El tiempo de consulta es muy bajo (0-4 msec), lo que indica que la respuesta se obtuvo muy rápidamente. Este tiempo puede variar un poco, como se muestra en los resultados.

4. **Flags y TTL**: Los flags y el TTL (Tiempo de vida) se mantienen constantes. Esto es normal para consultas repetidas en un corto periodo de tiempo.

5. **Orden de los servidores NS**: En la última consulta, el orden de los servidores NS es diferente al de las consultas anteriores. Esto podría deberse al balanceo de carga DNS o simplemente a cómo el software de DNS elige listar los servidores.

Por lo tanto, lo que observamos aquí es bastante normal y esperado. Las pequeñas diferencias en el tiempo de consulta son normales y podrían atribuirse a variaciones en la carga de la red o del servidor DNS.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**d. Observe la información que obtuvo al consultar por los servidores de DNS del dominio. En base a la salida, ¿es posible indicar cuál de ellos es el primario?**

La salida del comando `dig` para consultar los servidores de nombres (NS) del dominio `redes.unlp.edu.ar` no incluye información que permita determinar directamente cuál de los servidores es el servidor primario (o maestro) y cuál es el secundario (o esclavo).

Normalmente, la información sobre cuál es el servidor DNS primario y cuál es el secundario está confinada a la configuración interna de los servidores DNS involucrados y no se expone típicamente a clientes o a consultas DNS externas como las que se realizan con `dig`.

Para determinar cuál es el servidor DNS primario de un dominio, generalmente tendría que tener acceso a la configuración del servidor DNS en el dominio en cuestión o recibir esa información del administrador del sistema o de la red.

Por lo tanto, con la información proporcionada, no es posible indicar cuál de los servidores de DNS es el primario.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**e. Consulte por el registro SOA del dominio y responda.**

```shell
dig SOA redes.unlp.edu.ar
```

```shell
; <<>> DiG 9.16.27-Debian <<>> SOA redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 48401
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 6d457cfb63d145040100000064fdd61531d0de439ebbb74b (good)
;; QUESTION SECTION:
;redes.unlp.edu.ar.		IN	SOA

;; ANSWER SECTION:
redes.unlp.edu.ar.	86400	IN	SOA	ns-sv-b.redes.unlp.edu.ar. root.redes.unlp.edu.ar. 2020031700 604800 86400 2419200 86400

;; Query time: 0 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 11:43:33 -03 2023
;; MSG SIZE  rcvd: 123
```

***i. ¿Puede ahora determinar cuál es el servidor de DNS primario?***

El servidor de DNS primario para el dominio `redes.unlp.edu.ar` es `ns-sv-b.redes.unlp.edu.ar` según la sección "ANSWER" del resultado del comando.

***ii. ¿Cuál es el número de serie, qué convención sigue y en qué casos es importante actualizarlo?***

El número de serie es `2020031700`. Este número parece seguir la convención de la fecha, en el formato YYYYMMDDNN, donde "YYYYMMDD" es la fecha del último cambio y "NN" es un número de revisión para ese día. Este número de serie se incrementa cuando hay cambios en el dominio, lo que señala a los servidores DNS secundarios que necesitan actualizar su información.

***iii. ¿Qué valor tiene el segundo campo del registro? Investigue para qué se usa y cómo se interpreta el valor.***

El segundo campo del registro es `root.redes.unlp.edu.ar`, que generalmente se interpreta como la dirección de correo electrónico del administrador de DNS para el dominio, aunque el "@" se reemplaza por un punto. En este caso, el correo sería `root@redes.unlp.edu.ar`. Este campo se usa para saber quién es responsable del dominio.

***iv. ¿Qué valor tiene el TTL de caché negativa y qué significa?***

El último número en la sección "ANSWER" del registro SOA es `86400`, que es el TTL de caché negativa en segundos. Esto significa que si se realiza una consulta para un registro que no existe en este dominio, el resultado negativo se almacenará en caché durante 86400 segundos (o 24 horas) antes de que se realice otra consulta al servidor DNS primario.

Con esta información, debería tener una mejor comprensión del registro SOA y de cómo se configura y administra el dominio `redes.unlp.edu.ar`.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**f. Indique qué valor tiene el registro TXT para el nombre saludo.redes.unlp.edu.ar. Investigue para qué es usado este registro.**

```shell
dig TXT saludo.redes.unlp.edu.ar
```

```shell
; <<>> DiG 9.16.27-Debian <<>> TXT saludo.redes.unlp.edu.ar
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 61711
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 00ce47d146589e5e0100000064fddcede4e3cc53c37fe4ec (good)
;; QUESTION SECTION:
;saludo.redes.unlp.edu.ar.	IN	TXT

;; ANSWER SECTION:
saludo.redes.unlp.edu.ar. 86400	IN	TXT	"HOLA"

;; Query time: 0 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 12:12:45 -03 2023
;; MSG SIZE  rcvd: 98
```

Este es un ejemplo muy simple y no está claro inmediatamente para qué se usa este registro en este contexto específico. Generalmente, los registros TXT pueden usarse para una variedad de propósitos, como ya mencioné. En este caso, podría ser simplemente un ejemplo o una forma de demostrar cómo funcionan los registros TXT.

El valor "HOLA" no ofrece muchas pistas sobre su propósito específico, pero definitivamente es legible y entendible para los seres humanos, lo que a veces es el objetivo de un registro TXT: proporcionar información que pueda ser fácilmente interpretada. Sin embargo, sin un contexto adicional o documentación, es difícil determinar el propósito exacto de este registro en particular.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**g. Utilizando dig, solicite la transferencia de zona de redes.unlp.edu.ar, analice la salida y responda.**

- **i.** ¿Qué significan los números que aparecen antes de la palabra IN? ¿Cuál es su finalidad?
- **ii.** ¿Cuántos registros NS observa? Compare la respuesta con los servidores de DNS del dominio redes.unlp.edu.ar que dio anteriormente. ¿Puede explicar a qué se debe la diferencia y qué significa?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**h. Consulte por el registro A de www.redes.unlp.edu.ar y luego por el registro A de www.practica.redes.unlp.edu.ar.**
Observe los TTL de ambos. Repita la operación y compare el valor de los TTL de cada uno respecto de la respuesta anterior. ¿Puede explicar qué está ocurriendo? (Pista: observar los flags será de ayuda).

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**i. Consulte por el registro A de www.practica2.redes.unlp.edu.ar.**
¿Obtuvo alguna respuesta? Investigue sobre los codigos de respuesta de DNS. ¿Para qué son utilizados los mensajes NXDOMAIN y NOERROR?


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 12

Investigue los comando nslookup y host. ¿Para qué sirven? Intente con ambos comandos obtener:

- Dirección IP de www.redes.unlp.edu.ar.
- Servidores de correo del dominio redes.unlp.edu.ar.
- Servidores de DNS del dominio redes.unlp.edu.ar.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 13

¿Qué función cumple en Linux/Unix el archivo /etc/hosts o en Windows el archivo \WINDOWS\system32\drivers\etc\hosts?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 14

Abra el programa Wireshark para comenzar a capturar el tráfico de red en la interfaz con IP 172.28.0.1.

Una vez abierto realice una consulta DNS con el comando dig para averiguar el registro MX de redes.unlp.edu.ar y luego, otra para averiguar los registros NS correspondientes al dominio redes.unlp.edu.ar.

Analice la información proporcionada por dig y compárelo con la captura

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 15

Dada la siguiente situación: “Una PC en una red determinada, con acceso a Internet, utiliza los servicios de DNS de un servidor de la red”. Analice:
**a. ¿Qué tipo de consultas (iterativas o recursivas) realiza la PC a su servidor de DNS?**

**b. ¿Qué tipo de consultas (iterativas o recursivas) realiza el servidor de DNS para resolver requerimientos de usuario como el anterior? ¿A quién le realiza estas consultas?**


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 16

Relacione DNS con HTTP. ¿Se puede navegar si no hay servicio de DNS?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 17

Observar el siguiente gráfico y contestar:

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/72b0b1dc-5763-48e5-908f-01fd5549c5b8)

- **a.** Si la PC-A, que usa como servidor de DNS a "DNS Server", desea obtener la IP de www.unlp.edu.ar, cuáles serían, y en qué orden, los pasos que se ejecutarán para obtener la respuesta.
- **b.** ¿Dónde es recursiva la consulta? ¿Y dónde iterativa?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 18

¿A quién debería consultar para que la respuesta sobre www.google.com sea autoritativa?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 19

¿Qué sucede si al servidor elegido en el paso anterior se lo consulta por www.info.unlp.edu.ar? ¿Y si la consulta es al servidor 8.8.8.8?


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 20 Ejercicio de parcial

En base a la siguiente salida de dig, conteste las consignas. Justifique en todos los casos.

```bash
1 ;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 4, ADDITIONAL: 4
2
3 ;; QUESTION SECTION:
4 ;ejemplo.com. IN __
5
6 ;; ANSWER SECTION:
7 ejemplo.com. 1634 IN __ 10 srv01.ejemplo.com.
8 ejemplo.com. 1634 IN __ 5 srv00.ejemplo.com.
9
10 ;; AUTHORITY SECTION:
11 ejemplo.com. 92354 IN __ ss00.ejemplo.com.
12 ejemplo.com. 92354 IN __ ss02.ejemplo.com.
13 ejemplo.com. 92354 IN __ ss01.ejemplo.com.
14 ejemplo.com. 92354 IN __ ss03.ejemplo.com.
15
16 ;; ADDITIONAL SECTION:
17 srv01.ejemplo.com. 272 IN __ 64.233.186.26
18 srv01.ejemplo.com. 240 IN __ 2800:3f0:4003:c00::1a
19 srv00.ejemplo.com. 272 IN __ 74.125.133.26
20 srv00.ejemplo.com. 240 IN __ 2a00:1450:400c:c07::1b
```

Complete las líneas donde aparece __ con el registro correcto.

- ¿Es una respuesta autoritativa? En caso de no serlo, ¿a qué servidor le preguntaría para obtener una respuesta autoritativa?
- ¿La consulta fue recursiva? ¿Y la respuesta?
- ¿Qué representan los valores 10 y 5 en las líneas 7 y 8.