<h1 align="center"> Práctica 4 Capa de Aplicación - Correo electrónico</h1>

---

- [Ejercicio 1](#ejercicio-1)
- [Ejercicio 2](#ejercicio-2)
- [Ejercicio 3](#ejercicio-3)
- [Ejercicio 4](#ejercicio-4)
- [Ejercicio 5](#ejercicio-5)
- [Ejercicio 6]()
- [Ejercicio 7]()
- [Ejercicio 8]()
- [Ejercicio 9]()
- [Ejercicio 10]()
- [Ejercicio 11]()
- [Ejercicio 12]()





---




## Correo electrónico

### Ejercicio 1

¿Qué protocolos se utilizan para el envío de mails entre el cliente y su servidor de correo? ¿Y entre servidores de correo?

---

### Ejercicio 2

¿Qué protocolos se utilizan para la recepción de mails? Enumere y explique características y diferencias entre las alternativas posibles.

---

### Ejercicio 3

Utilizando la VM y teniendo en cuenta los siguientes datos, abra el cliente de correo (thunderbird) y configure dos cuentas de correo. Una de las cuentas utilizará POP para solicitar al servidor los mails recibidos para la misma mientras que la otra utilizará IMAP.

Al crear cada una de las cuentas, seleccionar Manual config y luego de configurar las mismas según lo indicado, ignorar advertencias por uso de conexión sin cifrado

**Datos para POP**

- Cuenta de correo: alumnopop@redes.unlp.edu.ar
- Nombre de usuario: **alumnopop**
- Contraseña: **alumnopoppass**
- Puerto: **110**

**Datos para IMAP**

- Cuenta de correo: alumnoimap@redes.unlp.edu.ar
- Nombre de usuario: **alumnoimap**
- Contraseña: **alumnoimappass**
- Puerto: **143**

**Datos comunes para ambas cuentas**

- Servidor de correo entrante (POP/IMAP):
    - Nombre: **mail.redes.unlp.edu.ar**
    - SSL: **None**
    - Autenticación: **Normal password**
- Servidor de correo saliente (SMTP):
    - Nombre: **mail.redes.unlp.edu.ar**
    - Puerto: **25**
    - SSL: **None**
    - Autenticación: **Normal password**


#### Parte a)
Verificar el correcto funcionamiento enviando un email desde el cliente de una cuenta a la otra y luego desde la otra responder el mail hacia la primera.



#### Parte b)
Análisis del protocolo SMTP

- **i)** Utilizando Wireshark, capture el tráfico de red contra el servidor de correo mientras desde la cuenta alumnopop@redes.unlp.edu.ar envía un correo a alumnoimap@redes.unlp.edu.ar
- **ii)** Utilice el filtro SMTP para observar los paquetes del protocolo SMTP en la captura generada y analice el intercambio de dicho protocolo entre el cliente y el servidor para observar los distintos comandos utilizados y su correspondiente respuesta. 

> Ayuda: filtre por protocolo SMTP y sobre alguna de las líneas del intercambio haga click derecho y seleccione Follow TCP Stream. . .


#### Parte c)
Usando el cliente de correo,thunderbirddel usuario alumnopop@redes.unlp.edu.ar envíe un correoelectrónico alumnoimap@redes.unlp.edu.ar el cual debe tener: un asunto, datos en el body y unaimagen adjunta

- **i)** Verifique los fuentes del correo recibido para entender como se utiliza el header “Content-Type:multipart/mixed“ para poder realizar el envío de distintos archivos adjuntos.
- **ii)** Extraiga la imagen adjunta del mismo modo que lo hace el cliente de correo a partir de losfuentes del mensaje

---

### Ejercicio 4

**Análisis del protocolo POP**

#### Parte a)
Utilizando Wireshark, capture el tráfico de red contra el servidor de correo mientras desde la cuentaalumnoimap@redes.unlp.edu.ar le envía una correo a alumnopop@redes.unlp.edu.ar y mientrasalumnopop@redes.unlp.edu.ar recepciona dicho correo.

#### Parte b)

Utilice el filtro POP para observar los paquetes del protocolo POP en la captura generada y analiceel intercambio de dicho protocolo entre el cliente y el servidor para observar los distintos comandosutilizados y su correspondiente respuesta.

---

### Ejercicio 5 

**Análisis del protocolo IMAP**

#### Parte a)

Utilizando Wireshark, capture el tráfico de red contra el servidor de correo mientras desde la cuentaalumnopop@redes.unlp.edu.ar le envía una correo a alumnoimap@redes.unlp.edu.ar y mientrasalumnoimap@redes.unlp.edu.ar recepciona dicho correo.

#### Parte b)

Utilice el filtro IMAP para observar los paquetes del protocolo IMAP en la captura generada y analiceel intercambio de dicho protocolo entre el cliente y el servidor para observar los distintos comandosutilizados y su correspondiente respuesta.

---

### Ejercicio 6

**IMAP vs POP**

#### Parte a)

Marque como leídos todos los correos que tenga en el buzón de entrada de alumnopop y de alum-noimap. Luego, cree una carpeta llamada POP en la cuenta de alumnopop y una llamada IMAP enla cuenta de alumnoimap.

Asegurese que tiene mails en el inbox y en la carpeta recientemente creada en cada una de las cuentas.

#### Parte b)

Cierre la sesión iniciada e ingrese nuevamente identificandose como usuario root y password packer,ejecute el cliente de correos.

De esta forma, iniciará el cliente de correo con el perfil del superusuario (diferente del usuario conel que ya configuró las cuentas antes mencionadas).

Luego configure las cuentas POP e IMAP de los usuarios alumnopop y alumnoimap como se des-cribió anteriormente pero desde el cliente de correos ejecutado con el usuario root.

***Luego responda:***

**¿Qué correos ve en el buzón de entrada de ambas cuentas?**

**¿Están marcados como leídos ocomo no leídos?** 

**¿Por qué?**

**¿Qué pasó con las carpetas POP e IMAP que creó en el paso anterior?**

#### Parte c)

En base a lo observado. ¿Qué protocolo le parece mejor? ¿POP o IMAP? ¿Por qué? ¿Qué protocoloconsidera que utiliza más recursos del servidor? ¿Por qué?

---

### Ejercicio 7

¿En algún caso es posible enviar más de un correo durante una misma conexión tcp?
Considere:

- Destinatarios múltiples del mismo dominio entre MUA-MSA y entre MTA-MTA
- Destinatarios múltiples de diferentes dominios entre MUA-MSA y entre MTA-MTA

### Ejercicio 8)

Indique sí es posible que el MSA escuche en un puerto TCP diferente a los convencionales y quéimplicancias tendría.

### Ejercicio 9)

Indique sí es posible que el MTA escuche en un puerto TCP diferente a los convencionales y qué impli-cancias tendría

### Ejercicio 10)

**Ejercicio integrador HTTP, DNS y MAIL**

Suponga que registró bajo su propiedad el dominio redes2022.com.ar y dispone de 4 servidores:

- Un servidor DNS instalado configurado como primario de la zona redes2022.com.ar. (hostname: ns1/ ip: 203.0.113.65).
- Un servidor DNS instalado configurado como secundario de la zona redes2022.com.ar. (hostname:ns2 / ip: 203.0.113.66).
- Un servidor de correo electrónico (hostname: mail / ip: 203.0.113.111). Permitirá a los usuariosenvíar y recibir correos a cualquier dominio de Internet.- Un servidor WEB para el acceso a un webmail (hostname: correo / ip: 203.0.113.8). Permitiráa los usuarios gestionar vía web sus correos electrónicos a través de la URL https://webmail.re-des2022.com.ar


