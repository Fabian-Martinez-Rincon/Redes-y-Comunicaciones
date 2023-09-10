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

Investigue y describa cómo funciona el DNS. ¿Cuál es su objetivo?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 2

¿Qué es un root server? ¿Qué es un generic top-level domain (gtld)?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 3

¿Qué es una respuesta del tipo autoritativa?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 4

¿Qué diferencia una consulta DNS recursiva de una iterativa?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 5

¿Qué es el resolver?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 6

Describa para qué se utilizan los siguientes tipos de registros de DNS:

a. A 
f. NS
b. MX 
g. CNAME
c. PTR 
h. SOA
d. AAAA 
i. TXT
e. SRV

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 7

En Internet, un dominio suele tener más de un servidor DNS. ¿Por qué cree que esto es así?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 8

Cuando un dominio cuenta con más de un servidor, uno de ellos es el primario (o maestro) y todos los demás son los secundarios (o esclavos). ¿Cuál es la razón de que sea así?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 9

Explique brevemente en qué consiste el mecanismo de transferencia de zona y cuál es su finalidad.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 10

Imagine que usted es el administrador del dominio de DNS de la UNLP (unlp.edu.ar). A su vez, cada facultad de la UNLP cuenta con un administrador que gestiona su propio dominio (por ejemplo, en el caso de la Facultad de Informática se trata de info.unlp.edu.ar). Suponga que se crea una nueva facultad, Facultad de Redes, cuyo dominio será redes.unlp.edu.ar, y el administrador le indica que quiere poder manejar su propio dominio. ¿Qué debe hacer usted para que el administrador de la Facultad de Redes pueda gestionar el dominio de forma independiente? (Pista: investigue en qué consiste la delegación de dominios).

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 11

Responda y justifique los siguientes ejercicios

**a. En la VM, utilice el comando dig para obtener la dirección IP del host www.redes.unlp.edu.ar y responda:**

**b. ¿Cuáles son los servidores de DNS del dominio redes.unlp.edu.ar?**

**c. Repita la consulta anterior cuatro veces más. ¿Qué observa? ¿Puede explicar a qué se debe?**

**d. Observe la información que obtuvo al consultar por los servidores de DNS del dominio. En base a la salida, ¿es posible indicar cuál de ellos es el primario?**

**e. Consulte por el registro SOA del dominio y responda.**

- **i** ¿Puede ahora determinar cuál es el servidor de DNS primario?
- **ii** ¿Cuál es el número de serie, qué convención sigue y en qué casos es importante actualizarlo?
- **iii** ¿Qué valor tiene el segundo campo del registro? Investigue para qué se usa y como se interpreta el valor.
- **iv** ¿Qué valor tiene el TTL de caché negativa y qué significa?

**f. Indique qué valor tiene el registro TXT para el nombre saludo.redes.unlp.edu.ar. Investigue para qué es usado este registro.**

**g. Utilizando dig, solicite la transferencia de zona de redes.unlp.edu.ar, analice la salida y responda.**

- **i.** ¿Qué significan los números que aparecen antes de la palabra IN? ¿Cuál es su finalidad?
- **ii.** ¿Cuántos registros NS observa? Compare la respuesta con los servidores de DNS del dominio redes.unlp.edu.ar que dio anteriormente. ¿Puede explicar a qué se debe la diferencia y qué significa?

**h. Consulte por el registro A de www.redes.unlp.edu.ar y luego por el registro A de www.practica.redes.unlp.edu.ar.** 
Observe los TTL de ambos. Repita la operación y compare el valor de los TTL de cada uno respecto de la respuesta anterior. ¿Puede explicar qué está ocurriendo? (Pista: observar los flags será de ayuda).

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