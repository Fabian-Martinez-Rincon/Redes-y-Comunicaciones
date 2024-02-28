## Práctica 8

### Capa de Red: Fragmentación- Ruteo

**Recomendación**

> Al final de la práctica se encuentra un ejercicio para ser realizado en la herramienta CORE. Si bien el ejercicio no agrega conceptos nuevos a los vistos previamente recomendamos su resolución para que puedan configurar, probar y analizar todo lo aprendido en una simulación de una red.

**Fragmentación**

- [Ejercicio 2. Se tiene la siguiente red con los MTUs indicados en la misma.](#ejercicio-2)
- [Ejercicio 3 ¿Qué es el ruteo? ¿Por qué es necesario?](#ejercicio-3)
- [Ejercicio 4 En las redes IP el ruteo puede configurarse en forma estática o en forma dinámica](#ejercicio-4)
- [Ejercicio 5 Una máquina conectada a una red pero no a Internet, ¿tiene tabla de ruteo?](#ejercicio-5)
- [Ejercicio 6 Observando el siguiente gráfico y la tabla de ruteo del router D](#ejercicio-6)
- [Ejercicio 7 Evalúe para cada caso si el mensaje llegará a destino](#ejercicio-7)

**DHCP y NAT**

- [Ejercicio 8 Con la máquina virtual con acceso a Internet realice las siguientes observaciones](#ejercicio-8)
- [Ejercicio 9 ¿Qué es NAT y para qué sirve?](#ejercicio-9)
- [Ejercicio 10 ¿Qué especifica la RFC 1918 y cómo se relaciona con NAT?](#ejercicio-10)
- [Ejercicio 11 En la red de su casa o trabajo verifique la dirección IP de su computadora y luego acceda a www.cualesmiip.com](#ejercicio-11)
- [Ejercicio 12 Resuelva las consignas que se dan a continuación](#ejercicio-12)
- [Ejercicio 13 Asigne las redes que faltan utilizando los siguientes bloques y las consideraciones debajo](#ejercicio-13)
- [Ejercicio 14 Asigne IP a todas las interfaces de las redes listadas a continuación](#ejercicio-14)
- [Ejercicio 15 Realice las tablas de rutas de RouterE y BORDER considerando](#ejercicio-15)
- [Ejercicio 16 Utilizando la máquina virtual, se configurará ruteo estático en la red](#ejercicio-16)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">


### Ejercicio 2

Se tiene la siguiente red con los MTUs indicados en la misma. Si desde pc1 se envía un paquete IP a pc2 con un tamaño total de 1500 bytes (cabecera IP más payload) con el campo Identification = 20543, responder:

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/32329820-51e7-4344-8fe9-d718683d67f1)

- Indicar IPs origen y destino y campos correspondientes a la fragmentación cuando el paquete sale de pc1
- ¿Qué sucede cuando el paquete debe ser reenviado por el router R1?
- Indicar cómo quedarían las paquetes fragmentados para ser enviados por el enlace entre R1 y R2.
- ¿Dónde se unen nuevamente los fragmentos? ¿Qué sucede si un fragmento no llega? 
- Si un fragmento tiene que ser reenviado por un enlace con un MTU menor al tamaño del fragmento, ¿qué hará el router con ese fragmento?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 3

¿Qué es el ruteo?

¿Por qué es necesario?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 4

En las redes IP el ruteo puede configurarse en forma estática o en forma dinámica. Indique ventajas y desventajas de cada método.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 5

Una máquina conectada a una red pero no a Internet, ¿tiene tabla de ruteo?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 6

Observando el siguiente gráfico y la tabla de ruteo del router D, responder:

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/482f5dd5-acb7-4fa6-aa87-7c6a1d36eb0c)

 #### Parte a
 
 ¿Está correcta esa tabla de ruteo? En caso de no estarlo, indicar el o los errores encontrados.
 
 Escribir la tabla correctamente (no es necesario agregar las redes que conectan contra los ISPs)
 
#### Parte b
 
Con la tabla de ruteo del punto anterior, Red D, ¿tiene salida a Internet?

¿Por qué?

¿Cómo lo solucionaría? 

Suponga que los demás routers están correctamente configurados, con salida a Internet y que Rtr-D debe salir a Internet por Rtr-C.

#### Parte c

Teniendo en cuenta lo aplicado en el punto anterior, si en Rtr-C estuviese la siguiente entrada en su tabla de ruteo qué sucedería si desde una PC en Red D se quiere acceder un servidor con IP 163.10.5.15

| Red Destino | Mask | Next-Hop | Iface |
|-------------|------|----------|-------|
| 163.10.5.0  | /24  | 10.0.0.9 | eth1  |

#### Parte d

¿Esposible aplicar sumarización en esa tabla, la del router Rtr-D? 

¿Por qué? ¿Qué debería suceder para poder aplicarla?

#### Parte e

La sumarización aplicada en el punto anterior, ¿se podría aplicar en Rtr-B?

¿Por qué?

#### Parte f

Escriba la tabla de ruteo de Rtr-B teniendo en cuenta lo siguiente:

- Debe llegarse a todas las redes del gráfico
- Debe salir a Internet por Rtr-A
- Debe pasar por Rtr-D para llegar a Red D
- Sumarizar si es posible

#### Parte g

Si Rtr-C pierde conectividad contra ISP-2, ¿es posible restablecer el acceso a Internet sin esperar a que vuelva la conectividad entre esos dispositivos?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 7

Evalúe para cada caso si el mensaje llegará a destino, saltos que tomará y tipo de respuesta recibida el emisor.

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/00434c70-d298-4e63-90f4-9890417d2629)

- Un mensaje ICMP enviado por PC-B a PC-C.
- Un mensaje ICMP enviado por PC-C a PC-B.
- Un mensaje ICMP enviado por PC-C a 8.8.8.8.
- Un mensaje ICMP enviado por PC-B a 8.8.8.8.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

## DHCP y NAT

### Ejercicio 8

Con la máquina virtual con acceso a Internet realice las siguientes observaciones respecto de la auto configuración IP vía DHCP:

#### Parte a

Inicie una captura de tráfico Wireshark utilizando el filtro bootp para visualizar únicamente tráfico de DHCP.

#### Parte b

En una terminal de root, ejecute el comando sudo /sbin/dhclient eth0 y analice el intercambio de paquetes capturado.

#### Parte c

Analice la información registrada en el archivo /var/lib/dhcp/dhclient.leases, ¿cuál parece su función?

#### Parte d

Ejecute el siguiente comando para eliminar información temporal asignada por el servidor DHCP.

```bash
rm /var/lib/dhcp/dhclient.leases 
```

#### Parte e

Enunaterminal de root, vuelva a ejecutar el comando 

```bash
sudo /sbin/dhclient eth0
```

y analice el intercambio de paquetes capturado nuevamente ¿a que se debió la diferencia con lo observado en el punto “b”?

#### Parte f

Tanto en “b” comoen“e”, ¿quéinformación es brindada al host que realiza la petición DHCP, además de la dirección IP que tiene que utilizar?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 9

¿Qué es NAT y para qué sirve?

De un ejemplo de su uso y analice cómo funcionaría en ese entorno.
 
> Ayuda: analizar el servicio de Internet hogareño en el cual varios dispositivos usan Internet simultáneamente.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 10

¿Qué especifica la RFC 1918 y cómo se relaciona con NAT?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 11

En la red de su casa o trabajo verifique la dirección IP de su computadora y luego acceda a www.cualesmiip.com. 

¿Qué observa?

¿Puede explicar qué sucede?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 12

Resuelva las consignas que se dan a continuación.

#### Parte a

En base a la siguiente topología y a las tablas que se muestran, complete los datos que faltan.

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/a5f56e81-b65b-43be-80aa-690cad709156)

#### PC-A (ss)

| Local Address:Port | Peer Address:Port |
|--------------------|-------------------|
| 192.168.1.2:49273  |                   |
|                    | 190.50.10.63:25   |
| 192.168.1.2:_____  | 190.50.10.81:8080 |

#### PC-B (ss)

| Local Address:Port | Peer Address:Port |
|--------------------|-------------------|
| 192.168.1.3:52734  |                   |
| 192.168.1.3:39275  |                   |

#### RTR-1 (Tabla de NAT)

| Lado LAN           | Lado WAN          |    
|--------------------|-------------------|
| 192.168.1.2:49273  | 205.20.0.29:25192 |
| 192.168.1.2:51238  | _________________ |
| 192.168.1.3:52734  | 205.20.0.29:51091 |
| 192.168.1.2:37484  | 205.20.0.29:41823 |
| 192.168.1.3:39275  |  205.20.0.29:9123 |


#### SRV-A (ss)

| Local Address:Port | Peer Address:Port   |
|--------------------|---------------------|
| 190.50.10.63:80    | 205.20.0.29:25192   |
| 190.50.10.63:25    | 205.20.0.29:41823   |

#### SRV-B (ss)

| Local Address:Port | Peer Address:Port |
|--------------------|-------------------|
| 190.50.10.81:8080  | 205.20.0.29:16345 |
| 190.50.10.81:8081  | 205.20.0.29:51091 |
| 190.50.10.81:8080  | 205.20.0.29:9123  |

#### Parte b

En base a lo anterior, responda:

i. ¿Cuántas conexiones establecidas hay y entre qué dispositivos?

ii. ¿Quién inició cada una de las conexiones? 

¿Podrían haberse iniciado en sentido inverso? 

¿Por qué? 

Investigue qué es port forwarding y si serviría como solución en este caso.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

## Ejercicio de repaso

### Ejercicio 13

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/d1755aab-13c5-4f76-8c58-3275a655a572)

Asigne las redes que faltan utilizando los siguientes bloques y las consideraciones debajo:

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/132257ce-9729-4666-9235-6f2fa7b0a47b)

- Red Cyla Red Ddeben ser públicas.
- Los enlaces entre routers deben utilizar redes privadas.
- Se debe desperdiciar la menor cantidad de IP posibles.
- Si va a utilizar un bloque para dividir en subredes, asignar primero la red con más cantidad de hosts y luego las que tienen menos.
- Las redes elegidas deben ser válidas.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 14

Asigne IP a todas las interfaces de las redes listadas a continuación. 

> Los routers deben tener asignadas las primeras IP de la red. Para enlaces entre routers, asignar en el siguiente orden: RouterA, RouterB, RouterC, RouterD y RouterE

- Red A, Red B, Red C y Red D.
- Red entre RouterA-RouterB-RouterE.
- Red entre RouterC-RouterD.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 15

Realice las tablas de rutas de RouterE y BORDER considerando

- Siempre se deberá tomar la ruta más corta.
- Sumarizar siempre que sea posible.
- El tráfico de Internet a la Red D y viceversa debe atravesar el RouterC.
- Todos los hosts deben poder conectarse entre sí y a Internet

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

## Aclaración importante

En CORE no se guardan los cambios realizados en una topología al detenerla. Por ello, es deseable completar todo el ejercicio una vez empezado, para no tener que volver a configurar todo. Alternativamente se puede utilizar el script que se encuentra en este repositorio https://github.com/RYSAEI/SaveRestoreScripts para forzar que se guarden los cambios.

### Ejercicio 16

Utilizando la máquina virtual, se configurará ruteo estático en la red que se muestra en el siguiente gráfico:

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/4fe3fa1b-6b4f-4a91-ad38-b1bfc9369700)

#### Parte a

Antes de empezar el ejercicio ejecute en una terminal el siguiente comando:

```bash
sudo iptables-P FORWARD ACCEPT
```

#### Parte b

Inicie la herramienta CORE y abra el archivo 1-ruteo-estatico.imn.

#### Parte c

Inicie la virtualización de la topología.

#### Parte d

Analice las tablas de ruteo de las diferentes PCs y de los routers. 

¿Qué observa? ¿Puede explicar por qué?

#### Parte e

Configure las las direcciones IP de las interfaces según lo que muestra el gráfico (para entrar a configurar cada equipo (PC o router) debe hacer doble click sobre el mismo, lo cual abre una terminal de comandos). Por ejemplo

- En la PC n6 debe configurar la interfaz eth0 con la IP 10.0.0.10.
- En el Router n1 debe configurar la eth0 con la IP 10.0.0.1, la eth1 con la IP 10.0.1.2 y la eth2 con la 10.0.2.1.

#### Parte f

Analice las tablas de ruteo de las diferentes PCs y de los routers. ¿Qué observa? ¿Puede explicar por qué?

#### Parte g

Compruebe conectividad. Para ello, tome por ejemplo la PC n7 y haga un ping a cada una de las diferentes IPs que configuró. ¿Qué ocurre y por qué?
#### Parte h

Configure una ruta por defecto en todas las computadoras y analice los cambios en las tablas de ruteo.

#### Parte i

Compruebe conectividad repitiendo el mismo procedimiento que hizo anteriormente. ¿Qué ocurre y por qué?

#### Parte j

Función de ruteo: un dispositivo que actúe como router requiere tener habilitado el encaminamiento de paquetes entre sus interfaces

Verificar IP_FORWARD, en los routers y las PCs, obteniendo la configuración con:

```bash
cat /proc/sys/net/ipv4/ip_forward
```


El valor 0 indica funcionalidad desactivada (esto es correcto para las PCs). 1 indica que está habilitado (esto es requerido para los routers)

#### Parte k

Configure en los routers rutas estáticas a cada una de las redes de la topología (no utilice rutas por defecto).

#### Parte l

Compruebe conectividad entre todos los dispositivos de la red. Si algún dispositivo no puede comunicarse con otro revise las tablas de ruteo y solucione los inconvenientes hasta que la conectividad sea completa.

#### Parte m

Modifique ahora las tablas de ruteo de los routers, eliminando todas las rutas configuradas hasta el momento y vuelva a configurarlas en base al siguiente criterio.
- Router n1 envía todo el tráfico desconocido a Router n2.
- Router n2 envía todo el tráfico desconocido a Router n3.
- Router n3 envía todo el tráfico desconocido a Router n1.

#### Parte n

Compruebe conectividad entre todos los dispositivos de la red. Si algún dispositivo no puede comunicarse con otro revise las tablas de ruteo y solucione los inconvenientes hasta que la conectividad sea completa.

#### Parte ñ

En base a las dos configuraciones de las tablas de ruteo anteriores, responda:

- ¿Cuál opción le resultó más sencilla y por qué?
- Considerando el tamaño de las tablas de ruteo en cada situación, ¿cuál de las dos opciones la parece más conveniente y por qué?
- ¿Puede pensar en algún caso donde la segunda opción sea la única posible?
- Suponga que realiza un ping a un host que tiene la IP 190.50.12.34.
- ¿Qué ocurrirá en cada caso? ¿Cuál le parece mejor?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">