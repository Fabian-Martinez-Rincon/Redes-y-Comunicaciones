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

Dado que los servidores DNS autoritativos para `redes.unlp.edu.ar` son `ns-sv-a.redes.unlp.edu.ar` y `ns-sv-b.redes.unlp.edu.ar`, puede intentar realizar una transferencia de zona con uno de ellos usando el comando `dig`.

Por ejemplo, con `ns-sv-a.redes.unlp.edu.ar`, el comando sería:

```bash
dig @ns-sv-a.redes.unlp.edu.ar redes.unlp.edu.ar AXFR
```

```shell
;; Connection to 172.28.0.30#53(172.28.0.30) for redes.unlp.edu.ar failed: host unreachable.
```

O con `ns-sv-b.redes.unlp.edu.ar`:

```bash
dig @ns-sv-b.redes.unlp.edu.ar redes.unlp.edu.ar AXFR
```

```shell
; <<>> DiG 9.16.27-Debian <<>> @ns-sv-b.redes.unlp.edu.ar redes.unlp.edu.ar AXFR
; (1 server found)
;; global options: +cmd
redes.unlp.edu.ar.	86400	IN	SOA	ns-sv-b.redes.unlp.edu.ar. root.redes.unlp.edu.ar. 2020031700 604800 86400 2419200 86400
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-a.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	NS	ns-sv-b.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	MX	5 mail.redes.unlp.edu.ar.
redes.unlp.edu.ar.	86400	IN	MX	10 mail2.redes.unlp.edu.ar.
ftp.redes.unlp.edu.ar.	86400	IN	CNAME	www.redes.unlp.edu.ar.
mail.redes.unlp.edu.ar.	86400	IN	A	172.28.0.90
mail2.redes.unlp.edu.ar. 86400	IN	A	172.28.0.91
ns-sv-a.redes.unlp.edu.ar. 604800 IN	A	172.28.0.30
ns-sv-b.redes.unlp.edu.ar. 604800 IN	A	172.28.0.29
practica.redes.unlp.edu.ar. 86400 IN	NS	ns1.practica.redes.unlp.edu.ar.
practica.redes.unlp.edu.ar. 86400 IN	NS	ns2.practica.redes.unlp.edu.ar.
ns1.practica.redes.unlp.edu.ar.	86400 IN A	172.28.0.120
ns2.practica.redes.unlp.edu.ar.	86400 IN A	172.28.0.121
saludo.redes.unlp.edu.ar. 86400	IN	TXT	"HOLA"
www.redes.unlp.edu.ar.	300	IN	A	172.28.0.50
redes.unlp.edu.ar.	86400	IN	SOA	ns-sv-b.redes.unlp.edu.ar. root.redes.unlp.edu.ar. 2020031700 604800 86400 2419200 86400
;; Query time: 4 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 14:09:16 -03 2023
;; XFR size: 17 records (messages 1, bytes 441)
```

Tenga en cuenta que la transferencia de zona a menudo está restringida por razones de seguridad. Si usted no tiene acceso permitido, la solicitud será denegada.

**i. ¿Qué significan los números que aparecen antes de la palabra IN? ¿Cuál es su finalidad?**

Los números antes de la palabra "IN" (que significa Internet) son los valores de "Time to Live" (TTL) en segundos. Estos números indican cuánto tiempo se mantendrá ese registro en la caché de un servidor DNS consultor antes de que se descarte y se requiera una nueva consulta para obtener información actualizada.

**ii. ¿Cuántos registros NS observa? Compare la respuesta con los servidores de DNS del dominio redes.unlp.edu.ar que dio anteriormente. ¿Puede explicar a qué se debe la diferencia y qué significa?**

**Hay dos registros NS en la salida:**

- `ns-sv-a.redes.unlp.edu.ar`
- `ns-sv-b.redes.unlp.edu.ar`

Estos coinciden con los servidores DNS que mencionó anteriormente. No hay diferencia en este caso, lo cual es esperado en una transferencia de zona exitosa.

**Sobre el comando que usó**
El comando `dig @ns-sv-b.redes.unlp.edu.ar redes.unlp.edu.ar AXFR` pide una transferencia de zona completa del dominio `redes.unlp.edu.ar` al servidor DNS `ns-sv-b.redes.unlp.edu.ar`. La bandera `AXFR` es la que solicita esta transferencia.


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**h. Consulte por el registro A de www.redes.unlp.edu.ar y luego por el registro A de www.practica.redes.unlp.edu.ar.**

```shell
dig www.redes.unlp.edu.ar A
```

```shell
; <<>> DiG 9.16.27-Debian <<>> www.redes.unlp.edu.ar A
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 1740
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: fa9ba4d5a50477c20100000064fdfb9afa2923b4597e3c3a (good)
;; QUESTION SECTION:
;www.redes.unlp.edu.ar.		IN	A

;; ANSWER SECTION:
www.redes.unlp.edu.ar.	300	IN	A	172.28.0.50

;; Query time: 4 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 14:23:38 -03 2023
;; MSG SIZE  rcvd: 94
```

- **TTL (Time to Live)**: El TTL es de 300 segundos, lo que significa que este registro se almacenará en la caché de los servidores DNS que lo consulten durante 300 segundos antes de que se considere "obsoleto" y deba volver a consultarse.
  
- **Dirección IP**: El registro A apunta a la dirección IP `172.28.0.50`.
  
- **Flags**: 
  - `qr`: Indica que la respuesta es una consulta.
  - `aa`: Indica que la respuesta viene de una autoridad en ese dominio.
  - `rd`: Recursion Desired, indica que el servidor debería intentar resolver la consulta consultando otros servidores si no tiene la información.
  - `ra`: Recursion Available, indica que el servidor puede realizar consultas recursivas.

Podría ser interesante realizar la misma consulta nuevamente después de un tiempo corto (pero menor a 300 segundos) para ver si el TTL ha disminuido, lo que indicaría que está en la caché.

---

```shell
dig www.practica.redes.unlp.edu.ar A
```

```shell
; <<>> DiG 9.16.27-Debian <<>> www.practica.redes.unlp.edu.ar A
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 31906
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: ace66a200fec22060100000064fdfc53656f8d705f2cb26f (good)
;; QUESTION SECTION:
;www.practica.redes.unlp.edu.ar.	IN	A

;; ANSWER SECTION:
www.practica.redes.unlp.edu.ar.	60 IN	A	172.28.0.10

;; Query time: 1852 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 14:26:43 -03 2023
;; MSG SIZE  rcvd: 103
```

- **TTL (Time to Live)**: En este caso, el TTL es de 60 segundos, mucho menor que los 300 segundos del registro para `www.redes.unlp.edu.ar`. Esto podría indicar una configuración más dinámica para este subdominio, permitiendo actualizaciones más frecuentes.

- **Dirección IP**: El registro A apunta a la dirección IP `172.28.0.10`.

- **Flags**: 
  - `qr`: Indica que la respuesta es una consulta.
  - `rd`: Recursion Desired, indica que el servidor debería intentar resolver la consulta consultando otros servidores si no tiene la información.
  - `ra`: Recursion Available, indica que el servidor puede realizar consultas recursivas.
  
  Nota: A diferencia del caso anterior, no vemos la bandera `aa` (Authoritative Answer), lo que significa que la respuesta podría venir de una caché o de otro servidor que no sea el principal para ese dominio.

- **Query Time**: El tiempo de consulta es notablemente más alto (1852 ms) en comparación con la primera consulta. Esto podría deberse a una variedad de factores, incluyendo la posibilidad de que el servidor haya tenido que realizar una búsqueda recursiva para obtener la respuesta.


**Observe los TTL de ambos. Repita la operación y compare el valor de los TTL de cada uno respecto de la respuesta anterior. ¿Puede explicar qué está ocurriendo? (Pista: observar los flags será de ayuda).**


***Comparación de TTL y Flags***

Si comparas los TTL de ambos registros A:

- `www.redes.unlp.edu.ar` tiene un TTL de 300 segundos.
- `www.practica.redes.unlp.edu.ar` tiene un TTL de 60 segundos.

Esto sugiere que la información relacionada con `www.practica.redes.unlp.edu.ar` es más volátil o se espera que cambie más frecuentemente que la información para `www.redes.unlp.edu.ar`.

Si repites las consultas antes de que expire el TTL, deberías ver que el TTL disminuye, lo cual es una indicación de que la respuesta está siendo servida desde la caché del servidor DNS.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

**i. Consulte por el registro A de www.practica2.redes.unlp.edu.ar.**
¿Obtuvo alguna respuesta? Investigue sobre los codigos de respuesta de DNS. 

```bash
dig www.practica2.redes.unlp.edu.ar A
```

```shell
; <<>> DiG 9.16.27-Debian <<>> www.practica2.redes.unlp.edu.ar A
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 41175
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: f1d40d72c26c7c9f0100000064fdfe467d22643c08e6b030 (good)
;; QUESTION SECTION:
;www.practica2.redes.unlp.edu.ar. IN	A

;; AUTHORITY SECTION:
redes.unlp.edu.ar.	86400	IN	SOA	ns-sv-b.redes.unlp.edu.ar. root.redes.unlp.edu.ar. 2020031700 604800 86400 2419200 86400

;; Query time: 0 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 14:35:02 -03 2023
;; MSG SIZE  rcvd: 154
```

Como puedes ver, el código de estado es `NXDOMAIN`, lo que significa que el subdominio `www.practica2.redes.unlp.edu.ar` no existe en el servidor DNS consultado. Esto es confirmado por el hecho de que la sección `ANSWER` está vacía (`ANSWER: 0`).

**Interpretación de la salida:**

- `opcode: QUERY, status: NXDOMAIN, id: 41175`: El estado `NXDOMAIN` indica que el dominio consultado no existe.

- `flags: qr aa rd ra`: Estas son las banderas de la respuesta. En este caso:
  - `qr` (Query Response): indica que este es un mensaje de respuesta.
  - `aa` (Authoritative Answer): indica que el servidor tiene una respuesta autorizada para la consulta.
  - `rd` (Recursion Desired): indica que se solicitó la recursión.
  - `ra` (Recursion Available): indica que el servidor DNS es capaz de realizar consultas recursivas.

- `QUESTION SECTION`: Muestra la consulta original que hiciste.
  
- `AUTHORITY SECTION`: Esta sección muestra información del registro SOA (Start of Authority) para el dominio `redes.unlp.edu.ar`. Esto básicamente indica qué servidor tiene la autoridad final sobre el dominio en cuestión.

Por lo tanto, podemos concluir que el subdominio `www.practica2.redes.unlp.edu.ar` no tiene un registro A, lo que significa que no está configurado para apuntar a ninguna dirección IP.

---

**¿Para qué son utilizados los mensajes NXDOMAIN y NOERROR?**

Si obtuviste una respuesta con un código de estado `NXDOMAIN`, esto significa que el dominio no existe según el servidor DNS consultado. En otras palabras, no hay un registro A (o cualquier otro tipo de registro que hayas solicitado) para `www.practica2.redes.unlp.edu.ar`.

Por otro lado, si recibes un código `NOERROR`, significa que la consulta DNS se realizó correctamente. Esto no necesariamente indica que se encontró un registro; por ejemplo, si consultas un dominio que existe pero no tiene un registro del tipo que buscas, recibirás un `NOERROR` sin un "ANSWER SECTION".

### Códigos de Respuesta de DNS:

- **NXDOMAIN**: Este código significa que el dominio consultado no existe. Es utilizado para informar a los clientes DNS que no hay registros DNS del tipo solicitado.

- **NOERROR**: Este código significa que la consulta DNS se realizó con éxito. Esto puede incluir no recibir un registro en la sección de respuesta si el dominio no tiene registros del tipo consultado pero sí existe.

Ambos códigos son cruciales para el funcionamiento de las aplicaciones de red, ya que permiten distinguir entre un dominio que no existe en absoluto y uno que simplemente no tiene el tipo de registro solicitado. Esto es particularmente importante para las búsquedas de servidores de correo, servidores web y otros servicios.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 12

Investigue los comando nslookup y host. ¿Para qué sirven? Intente con ambos comandos obtener:

- Dirección IP de www.redes.unlp.edu.ar.
- Servidores de correo del dominio redes.unlp.edu.ar.
- Servidores de DNS del dominio redes.unlp.edu.ar.

#### nslookup

El comando `nslookup` (Name Server Lookup) es una utilidad para realizar consultas al sistema de nombres de dominio (DNS). Puede obtener información variada, como direcciones IP asociadas a un nombre de dominio, servidores de correo, y mucho más.

**Ejemplos de uso para sus requerimientos:**

Dirección IP de `www.redes.unlp.edu.ar`:

```shell
nslookup www.redes.unlp.edu.ar
```

```shell
Server:		172.28.0.29
Address:	172.28.0.29#53

Name:	www.redes.unlp.edu.ar
Address: 172.28.0.50
```

Servidores de correo del dominio `redes.unlp.edu.ar`:

```shell
nslookup -query=MX redes.unlp.edu.ar
```

```shell
Server:		172.28.0.29
Address:	172.28.0.29#53

redes.unlp.edu.ar	mail exchanger = 5 mail.redes.unlp.edu.ar.
redes.unlp.edu.ar	mail exchanger = 10 mail2.redes.unlp.edu.ar.
```

Servidores de DNS del dominio `redes.unlp.edu.ar`:

```shell
nslookup -query=NS redes.unlp.edu.ar
```

```shell
Server:		172.28.0.29
Address:	172.28.0.29#53

redes.unlp.edu.ar	nameserver = ns-sv-b.redes.unlp.edu.ar.
redes.unlp.edu.ar	nameserver = ns-sv-a.redes.unlp.edu.ar.
```

#### host

El comando `host` es otra utilidad para realizar consultas DNS. Aunque similar a `nslookup`, es más sencillo y está diseñado para convertir nombres de dominio a direcciones IP y viceversa.

**Ejemplos de uso para sus requerimientos:**

Dirección IP de `www.redes.unlp.edu.ar`:

```shell
host www.redes.unlp.edu.ar
```

```shell
www.redes.unlp.edu.ar has address 172.28.0.50
```

Servidores de correo del dominio `redes.unlp.edu.ar`:

```shell
host -t MX redes.unlp.edu.ar
```

```shell
redes.unlp.edu.ar mail is handled by 5 mail.redes.unlp.edu.ar.
redes.unlp.edu.ar mail is handled by 10 mail2.redes.unlp.edu.ar.
```

Servidores de DNS del dominio `redes.unlp.edu.ar`:

```shell
host -t NS redes.unlp.edu.ar
```

```shell
redes.unlp.edu.ar name server ns-sv-b.redes.unlp.edu.ar.
redes.unlp.edu.ar name server ns-sv-a.redes.unlp.edu.ar.
```

Ambas utilidades, `nslookup` y `host`, son herramientas poderosas para la resolución de nombres y la depuración de problemas relacionados con DNS. Sin embargo, tenga en cuenta que `nslookup` está considerado como obsoleto por muchos en la comunidad de administración de sistemas, y se recomienda el uso de comandos como `dig` y `host` para nuevas implementaciones.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 13

**¿Qué función cumple en Linux/Unix el archivo /etc/hosts o en Windows el archivo \WINDOWS\system32\drivers\etc\hosts?**


El archivo `/etc/hosts` en sistemas Linux/Unix y el archivo `C:\WINDOWS\system32\drivers\etc\hosts` en sistemas Windows sirven para mapear direcciones IP a nombres de host en una computadora local. Este mapeo permite que el sistema traduzca nombres de host a direcciones IP sin tener que consultar un servidor DNS externo.

#### Usos comunes:

1. **Resolución de nombres local**: Puedes añadir nombres de dominio personalizados y su correspondiente dirección IP para que el sistema resuelva el nombre sin tener que ir a un servidor DNS. Por ejemplo, podrías mapear el dominio `mi-proyecto.local` a `127.0.0.1` para un entorno de desarrollo local.

2. **Bloqueo de sitios web**: Al asignar un nombre de dominio no deseado a la dirección IP `0.0.0.0` o `127.0.0.1`, puedes bloquear el acceso a ese sitio web.

3. **Redirección**: Puedes redirigir el tráfico destinado a un dominio específico a otra dirección IP.

4. **Pruebas y desarrollo**: Si estás desarrollando una aplicación que se conecta a un servidor, puedes redirigir temporalmente el nombre del servidor a una dirección IP local para realizar pruebas.

5. **Solución a problemas de red**: En algunos casos, puedes usar el archivo `hosts` para solucionar problemas temporales de resolución de nombres si el DNS no está disponible.

#### Formato:

El archivo generalmente contiene líneas con una dirección IP seguida de uno o varios nombres de host, separados por espacio o tabulación. Por ejemplo:

```
127.0.0.1       localhost
192.168.1.1     mi-router
203.0.113.10    ejemplo.com www.ejemplo.com
```

#### Notas:

- Las entradas en el archivo `hosts` tienen prioridad sobre las consultas DNS. Por lo tanto, si un nombre de host está en el archivo `hosts`, cualquier consulta DNS para ese nombre de host se resolverá usando la entrada en el archivo `hosts` en lugar de realizar una consulta DNS.
- Los cambios en el archivo `hosts` generalmente entran en vigor inmediatamente, pero algunos servicios o aplicaciones pueden requerir un reinicio o limpiar su caché DNS para reconocer los cambios.
  
Recuerda que modificar este archivo requiere permisos de administrador o superusuario.


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 14

Abra el programa Wireshark para comenzar a capturar el tráfico de red en la interfaz con IP 172.28.0.1.

Una vez abierto realice una consulta DNS con el comando dig para averiguar el registro MX de redes.unlp.edu.ar y luego, otra para averiguar los registros NS correspondientes al dominio redes.unlp.edu.ar.

Analice la información proporcionada por dig y compárelo con la captura

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 15

Dada la siguiente situación: “Una PC en una red determinada, con acceso a Internet, utiliza los servicios de DNS de un servidor de la red”. Analice:

**a. ¿Qué tipo de consultas (iterativas o recursivas) realiza la PC a su servidor de DNS?**

Por lo general, cuando una PC (cliente) necesita resolver un nombre de dominio, realiza una consulta recursiva a su servidor DNS asignado. En una consulta recursiva, el servidor DNS se compromete a proporcionar una respuesta definitiva al cliente. Si el servidor DNS no tiene la información en su caché, buscará la información necesaria consultando otros servidores DNS hasta obtener una respuesta definitiva para devolver al cliente. El cliente simplemente espera hasta recibir una respuesta.

**b. ¿Qué tipo de consultas (iterativas o recursivas) realiza el servidor de DNS para resolver requerimientos de usuario como el anterior? ¿A quién le realiza estas consultas?**

Cuando el servidor de DNS recibe una consulta recursiva de un cliente y no tiene la respuesta en su caché, realiza consultas iterativas a otros servidores DNS para resolver el nombre de dominio. En una consulta iterativa, el servidor DNS pregunta a otro servidor que puede saber más sobre el nombre de dominio. Ese servidor puede responder con una dirección IP si la tiene, o con una referencia a otro servidor DNS que esté más cerca de tener la respuesta.



<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 16

***Relacione DNS con HTTP.*** 

DNS (Sistema de Nombres de Dominio) y HTTP (Protocolo de Transferencia de Hipertexto) son dos componentes clave de la infraestructura de la web, pero sirven para propósitos muy diferentes:

<table>
<tr><td>DNS</td><td>HTTP</td></tr>
<tr><td>

Es el sistema que traduce nombres de dominio legibles por humanos en direcciones IP que las máquinas pueden entender. Cuando escribes un URL en tu navegador, DNS es el primer servicio que se consulta para determinar la dirección IP del servidor web asociado al nombre de dominio.

</td><td>

Es el protocolo utilizado para transferir datos sobre la web. Una vez que se obtiene la dirección IP del servidor mediante DNS, el navegador realiza una solicitud HTTP para recibir la página web que reside en esa dirección IP.
</td></tr>
</table>





En resumen, DNS se utiliza para resolver la dirección IP del servidor que aloja el contenido, y una vez que se conoce esa dirección IP, HTTP se encarga de la transferencia de ese contenido.


***¿Se puede navegar si no hay servicio de DNS?***

Técnicamente, sí, se puede navegar sin un servicio DNS, pero con algunas limitaciones importantes:

1. **Direcciones IP Directas**: Si conoces la dirección IP del servidor al que deseas acceder, puedes introducir esa dirección IP directamente en la barra de direcciones del navegador.

2. **Archivo Hosts**: Tanto en sistemas Windows como en Linux/Unix, puedes editar el archivo `hosts` para mapear nombres de dominio a direcciones IP específicas. Esto permitiría que tu sistema resuelva nombres de dominio sin necesidad de consultar un servidor DNS.

3. **Caché del Navegador o del Sistema**: Si un sitio web ha sido visitado recientemente, la correspondencia entre el nombre de dominio y la dirección IP puede estar almacenada en la caché local, permitiendo el acceso sin necesidad de una consulta DNS.

4. **Limitación en Navegación**: Sería difícil navegar por la web como lo hacemos normalmente, ya que muchos sitios web se alojan en servidores compartidos donde una única dirección IP se asocia con múltiples nombres de dominio, lo que hace necesario un servicio DNS para resolver al nombre correcto.

Por lo tanto, aunque es posible navegar en ciertas condiciones sin un servicio de DNS, la experiencia sería muy limitada y complicada. DNS es fundamental para el funcionamiento eficiente y amigable de la web tal como la conocemos hoy en día.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 17

Observar el siguiente gráfico y contestar:

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/72b0b1dc-5763-48e5-908f-01fd5549c5b8)

- **a.** Si la PC-A, que usa como servidor de DNS a "DNS Server", desea obtener la IP de www.unlp.edu.ar, cuáles serían, y en qué orden, los pasos que se ejecutarán para obtener la respuesta.
- **b.** ¿Dónde es recursiva la consulta? ¿Y dónde iterativa?

***Respuesta***

- PC-A se comunica con el switch para preguntarle al DNS por la dirección www.unlp.edu.ar, asumimos rd y ra. (la consulta es recursiva)
- El switch lleva la request al servidor DNS 192.168.10.2, en caso de no tenerla cacheada el DNS le dice al router que se comunique con el Root-Server mas cercano para empezar a hacer una consulta iterativa
- Se comunica con el Root-Server mas cercano (ANYCAST), en este caso el de la y este le devuelve la lista de servidores autoritativos para el siguiente nivel (.ar) en este caso 200.108.145.50
- El DNS se comunica con el servidor a cargo del dominio .ar y este le devuelve la lista de servidores autoritativos para el siguiente nivel (.edu.ar) en este caso 170.210.0.18
- El DNS se comunica con el que tiene el dominio .edu.ar y este le devuelve la lista de servidores autoritativos para el siguiente nivel (unlp.edu.ar) en este caso 163.10.0.67
- El DNS por ultimo se comunica con unlp.edu.ar que es el servidor autoritativo de www.unlp.edu.ar, devolviendo su direccion IP 163.10.0.54

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 18

¿A quién debería consultar para que la respuesta sobre www.google.com sea autoritativa?

```shell
dig google.com NS
```

```shell
; <<>> DiG 9.16.27-Debian <<>> google.com NS
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 51209
;; flags: qr rd ra; QUERY: 1, ANSWER: 4, AUTHORITY: 0, ADDITIONAL: 9

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 2a03d5bc739626bb0100000064fe21338b102d43f42ba191 (good)
;; QUESTION SECTION:
;google.com.			IN	NS

;; ANSWER SECTION:
google.com.		167692	IN	NS	ns3.google.com.
google.com.		167692	IN	NS	ns1.google.com.
google.com.		167692	IN	NS	ns2.google.com.
google.com.		167692	IN	NS	ns4.google.com.

;; ADDITIONAL SECTION:
ns1.google.com.		167692	IN	A	216.239.32.10
ns2.google.com.		167692	IN	A	216.239.34.10
ns3.google.com.		167692	IN	A	216.239.36.10
ns4.google.com.		167692	IN	A	216.239.38.10
ns1.google.com.		167692	IN	AAAA	2001:4860:4802:32::a
ns2.google.com.		167692	IN	AAAA	2001:4860:4802:34::a
ns3.google.com.		167692	IN	AAAA	2001:4860:4802:36::a
ns4.google.com.		167692	IN	AAAA	2001:4860:4802:38::a

;; Query time: 40 msec
;; SERVER: 172.28.0.29#53(172.28.0.29)
;; WHEN: Sun Sep 10 17:04:03 -03 2023
;; MSG SIZE  rcvd: 315
```

La salida del comando `dig` muestra que hay cuatro servidores DNS autoritativos para el dominio `google.com`: `ns1.google.com`, `ns2.google.com`, `ns3.google.com` y `ns4.google.com`. También muestra sus direcciones IP correspondientes en las secciones "A" y "AAAA".

Si quieres obtener una respuesta autoritativa sobre `www.google.com`, puedes dirigir tu consulta a uno de estos servidores DNS autoritativos. Puedes hacerlo con el siguiente comando `dig`:

```bash
dig @216.239.32.10 www.google.com A
```

O usando el nombre del servidor:

```bash
dig @ns1.google.com www.google.com A
```

```shell
; <<>> DiG 9.16.27-Debian <<>> @216.239.32.10 www.google.com A
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 54197
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;www.google.com.			IN	A

;; ANSWER SECTION:
www.google.com.		300	IN	A	142.251.134.68

;; Query time: 28 msec
;; SERVER: 216.239.32.10#53(216.239.32.10)
;; WHEN: Sun Sep 10 19:24:36 -03 2023
;; MSG SIZE  rcvd: 59
```

La salida de este comando `dig` muestra que has obtenido una respuesta autoritativa para la consulta del registro A de `www.google.com`. Puedes saber que es autoritativa por la bandera `aa` en la sección de "flags" de la respuesta. El registro A para `www.google.com` apunta a la dirección IP `142.251.134.68` y tiene un tiempo de vida (TTL) de 300 segundos.

La bandera `WARNING: recursion requested but not available` indica que aunque solicitaste una consulta recursiva (`rd` está presente en las banderas), el servidor te devolvió una respuesta sin ejecutar una búsqueda recursiva. Esto es lo que esperaríamos cuando consultamos directamente a un servidor autoritativo para el dominio; no necesita realizar más consultas para responder a la pregunta.

En resumen, has consultado con éxito uno de los servidores DNS autoritativos para `google.com` y has obtenido una respuesta autoritativa.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 19

***¿Qué sucede si al servidor elegido en el paso anterior se lo consulta por www.info.unlp.edu.ar?***

Para consultar al servidor de Google (autoritativo para google.com) sobre www.info.unlp.edu.ar:


```shell
dig @216.239.32.10 www.info.unlp.edu.ar A
```

```shell
; <<>> DiG 9.16.27-Debian <<>> @216.239.32.10 www.info.unlp.edu.ar A
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: REFUSED, id: 23768
;; flags: qr rd; QUERY: 1, ANSWER: 0, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;www.info.unlp.edu.ar.		IN	A

;; Query time: 36 msec
;; SERVER: 216.239.32.10#53(216.239.32.10)
;; WHEN: Sun Sep 10 19:30:27 -03 2023
;; MSG SIZE  rcvd: 49

```

La respuesta que obtuviste indica un estado de "REFUSED", lo cual significa que el servidor DNS ha rechazado tu consulta. Esto es lo esperado, dado que estás preguntando a un servidor que es autoritativo para el dominio `google.com` acerca de un dominio para el cual no tiene información ni autoridad (`www.info.unlp.edu.ar`).

El mensaje también incluye "WARNING: recursion requested but not available", lo que significa que, aunque solicitaste una consulta recursiva, el servidor DNS no la realizó porque no está configurado para proporcionar ese servicio para dominios para los cuales no es autoritativo.

En resumen, cuando preguntas a un servidor DNS autoritativo sobre un dominio que está fuera de su zona de autoridad, es probable que te encuentres con un rechazo o una falta de respuesta útil, como ha ocurrido en este caso. Este comportamiento destaca la importancia de usar servidores DNS recursivos para consultas generales, ya que están diseñados para manejar este tipo de situaciones y pueden realizar consultas a múltiples servidores DNS autoritativos para resolver una única consulta.

***¿Y si la consulta es al servidor 8.8.8.8?***

Para consultar al servidor DNS de Google (8.8.8.8):

```shell
dig @8.8.8.8 www.info.unlp.edu.ar A
```

```shell
; <<>> DiG 9.16.27-Debian <<>> @8.8.8.8 www.info.unlp.edu.ar A
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 36204
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;www.info.unlp.edu.ar.		IN	A

;; ANSWER SECTION:
www.info.unlp.edu.ar.	300	IN	A	163.10.5.71

;; Query time: 92 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Sun Sep 10 19:30:51 -03 2023
;; MSG SIZE  rcvd: 65
```

Cuando utilizas el servidor DNS 8.8.8.8 (que es un servidor DNS público de Google), obtienes una respuesta válida para la consulta sobre `www.info.unlp.edu.ar`. Esto se debe a que el servidor 8.8.8.8 es un servidor DNS recursivo, diseñado para resolver cualquier consulta DNS que se le haga, independientemente de si es autoritativo para ese dominio o no.

Aquí están los elementos clave de la respuesta:

- **Estado: NOERROR**: No hay errores; la consulta se resolvió con éxito.
  
- **FLAGS**: 
  - `qr`: indica que esta es una respuesta a una consulta.
  - `rd`: recursión deseada.
  - `ra`: recursión disponible.

- **ANSWER SECTION**: Aquí es donde se muestra la respuesta real a tu consulta. En este caso, la dirección IP para `www.info.unlp.edu.ar` es `163.10.5.71`.

- **TTL (Time to Live)**: Es de 300 segundos, lo que significa que esta información se mantendrá en la caché del servidor DNS durante 300 segundos antes de que se considere obsoleta y se deba volver a consultar.

- **Query time**: El tiempo que tardó en obtener una respuesta es de 92 milisegundos.

- **SERVER**: El servidor que proporcionó la respuesta es 8.8.8.8.

En resumen, el servidor DNS 8.8.8.8 pudo resolver con éxito tu consulta porque es un servidor recursivo que puede hacer consultas a otros servidores DNS hasta obtener la información que necesitas. Este es el comportamiento esperado de un servidor DNS recursivo y es en contraste con el comportamiento del servidor DNS autoritativo para `google.com` que recibió tu primera consulta.

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

Para completar las líneas donde aparece `__`, necesitamos entender qué tipos de registros DNS están siendo consultados y respondidos. Dado el contexto y los valores presentes, podemos hacer algunas suposiciones educadas:

1. La sección de preguntas generalmente especifica el tipo de registro que se está consultando. Aquí parece que se omite, pero dados los registros en la sección de respuestas, es probable que estemos hablando de registros MX (Mail Exchange). Entonces la línea 4 podría ser completada como `;ejemplo.com. IN MX`.

2. En la sección de respuestas, los servidores `srv01.ejemplo.com` y `srv00.ejemplo.com` se enumeran como servidores MX, por lo que las líneas 7 y 8 también deberían especificar el registro MX. Esto resulta en `ejemplo.com. 1634 IN MX 10 srv01.ejemplo.com.` y `ejemplo.com. 1634 IN MX 5 srv00.ejemplo.com.`.

3. En la sección de autoridades, parece que se están listando servidores NS (Name Server), por lo que las líneas 11-14 podrían especificar el registro NS, resultando en `IN NS ss00.ejemplo.com`, `IN NS ss02.ejemplo.com`, etc.

4. En la sección adicional, se proporcionan las direcciones IP para `srv01.ejemplo.com` y `srv00.ejemplo.com`. Aquí los registros son de tipo A para direcciones IPv4 y AAAA para direcciones IPv6. Por lo tanto, las líneas 17 y 19 podrían ser `IN A 64.233.186.26` y `IN A 74.125.133.26`, mientras que las líneas 18 y 20 podrían ser `IN AAAA 2800:3f0:4003:c00::1a` y `IN AAAA 2a00:1450:400c:c07::1b`.

Ahora para las preguntas:

- **¿Es una respuesta autoritativa?**  
  No, no es una respuesta autoritativa. No vemos el flag `aa` (authoritative answer) en la línea de los flags (`;; flags: qr rd ra`).

- **¿A qué servidor le preguntaría para obtener una respuesta autoritativa?**  
  Para obtener una respuesta autoritativa, tendrías que preguntarle a uno de los servidores NS listados en la sección de autoridad, como `ss00.ejemplo.com` o `ss01.ejemplo.com`, etc.

- **¿La consulta fue recursiva? ¿Y la respuesta?**  
  Sí, la consulta fue recursiva, como se indica por el flag `rd` (recursion desired) en la línea de flags. La respuesta también indica que la recursión está disponible, como se muestra por el flag `ra` (recursion available).

- **¿Qué representan los valores 10 y 5 en las líneas 7 y 8?**  
  Los valores 10 y 5 son prioridades para los servidores de correo en registros MX. Un valor más bajo indica una mayor prioridad. Por lo tanto, el servidor de correo `srv00.ejemplo.com` con una prioridad de 5 se utilizará antes que `srv01.ejemplo.com` con una prioridad de 10.

  

```shell
1 ;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 4, ADDITIONAL: 4
2
3 ;; QUESTION SECTION:
4 ;ejemplo.com.                   IN MX
5
6 ;; ANSWER SECTION:
7 ejemplo.com.           1634    IN MX    10 srv01.ejemplo.com.
8 ejemplo.com.           1634    IN MX    5  srv00.ejemplo.com.
9
10 ;; AUTHORITY SECTION:
11 ejemplo.com.           92354   IN NS    ss00.ejemplo.com.
12 ejemplo.com.           92354   IN NS    ss02.ejemplo.com.
13 ejemplo.com.           92354   IN NS    ss01.ejemplo.com.
14 ejemplo.com.           92354   IN NS    ss03.ejemplo.com.
15
16 ;; ADDITIONAL SECTION:
17 srv01.ejemplo.com.     272     IN A     64.233.186.26
18 srv01.ejemplo.com.     240     IN AAAA  2800:3f0:4003:c00::1a
19 srv00.ejemplo.com.     272     IN A     74.125.133.26
20 srv00.ejemplo.com.     240     IN AAAA  2a00:1450:400c:c07::1b
```