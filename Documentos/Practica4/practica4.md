Práctica 4

Capa de Aplicación - Correo electrónico

Correo electrónico

1. ¿Qué protocolos se utilizan para el envío de mails entre el cliente y su servidor de correo? ¿Y entre servidores de correo?

2. ¿Qué protocolos se utilizan para la recepción de mails? Enumere y explique características y diferencias entre las alternativas posibles.

3. Utilizando la VM y teniendo en cuenta los siguientes datos, abra el cliente de correo (thunderbird) y configure dos cuentas de correo. Una de las cuentas utilizará POP para solicitar al servidor los mails recibidos para la misma mientras que la otra utilizará IMAP.

Al crear cada una de las cuentas, seleccionar Manual config y luego de configurar las mismas según lo indicado, ignorar advertencias por uso de conexión sin cifrado

**Datos para POP**

- Cuenta de correo: alumnopop@redes.unlp.edu.ar
- Nombre de usuario: alumnopop
- Contraseña: alumnopoppass
- Puerto: 110

**Datos para IMAP**

- Cuenta de correo: alumnoimap@redes.unlp.edu.ar
- Nombre de usuario: alumnoimap
- Contraseña: alumnoimappass
- Puerto: 143

**Datos comunes para ambas cuentas**

Servidor de correo entrante (POP/IMAP):
- Nombre: mail.redes.unlp.edu.ar
- SSL: None
- Autenticación: Normal password

Servidor de correo saliente (SMTP):
- Nombre: mail.redes.unlp.edu.ar
- Puerto: 25
- SSL: None
- Autenticación: Normal password

a. Verificar el correcto funcionamiento enviando un email desde el cliente de una cuenta a la otra y luego desde la otra responder el mail hacia la primera.

b. Análisis del protocolo SMTP

i. Utilizando Wireshark, capture el tráfico de red contra el servidor de correo mientras desde la cuenta alumnopop@redes.unlp.edu.ar envía un correo a alumnoimap@redes.unlp.edu.ar
ii. Utilice el filtro SMTP para observar los paquetes del protocolo SMTP en la captura generada y analice el intercambio de dicho protocolo entre el cliente y el servidor para observar los distintos comandos utilizados y su correspondiente respuesta. 

Ayuda: filtre por protocolo SMTP y sobre alguna de las líneas del intercambio haga click derecho y seleccione Follow TCP Stream. . .