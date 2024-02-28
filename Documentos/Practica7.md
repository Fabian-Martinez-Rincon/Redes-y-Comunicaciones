## Práctica 7

### Capa de Red - Direccionamiento

**Introducción**
- [Ejercicio 1 ¿Qué servicios presta la capa de red? ¿Cuál es la PDU en esta capa? ¿Qué dispositivo es considerado sólo de la capa de red?](#ejercicio-1)
- [Ejercicio 2 ¿Por qué se lo considera un protocolo de mejor esfuerzo?](#ejercicio-2)
- [Ejercicio 3 ¿Cuántas redes clase A, B y C hay? ¿Cuántos hosts como máximo pueden tener cada una?](#ejercicio-3)
- [Ejercicio 4 ¿Qué son las subredes? ¿Por qué es importante siempre especificar la máscara de subred asociada?](#ejercicio-4)
- [Ejercicio 5 ¿Cuál es la finalidad del campo Protocol en la cabecera IP? ¿A qué campos de la capa de transporte se asemeja en su funcionalidad?](#ejercicio-5)

**División en subredes**

- [Ejercicio 6 Para cada una de las siguientes direcciones IP](#ejercicio-6)
- [Ejercicio 7 Su organización cuenta con la dirección de red 128.50.10.0. Indique](#práctica-7)
- [Ejercicio 8 Si usted estuviese a cargo de la administración del bloque IP 195.200.45.0/24](#ejercicio-8)
- [Ejercicio 9 Dado el siguiente gráfico](#ejercicio-9)

**CIDR**

- [Ejercicio 10 ¿Qué es CIDR (Class Interdomain routing)?](#ejercicio-10)
- [Ejercicio 11 ¿Cómo publicaría un router las siguientes redes si se aplica CIDR?](#ejercicio-11)
- [Ejercicio 12 Listar las redes involucradas en los siguientes bloques CIDR](#ejercicio-12)
- [Ejercicio 13 El bloque CIDR 128.0.0.0/2 o 128/2](#ejercicio-13)

**VLSM**

- [Ejercicio 14 ¿Qué es y para qué se usa VLSM?](#ejercicio-14)
- [Ejercicio 15 Describa, con sus palabras, el mecanismo para dividir subredes utilizando VLSM](#ejercicio-15)
- [Ejercicio 16 Suponga que trabaja en una organización que tiene la red que se ve en el gráfico](#ejercicio-16)
- [Ejercicio 17 Utilizando la siguiente topología y el bloque asignado](#ejercicio-17)
- [Ejercicio 18 Asigne direcciones IP en los equipos de la topología según el plan anterior](#ejercicio-18)

**ICMP y Configuraciones IP**

- [Ejercicio 19 Describa qué es y para qué sirve el protocolo ICMP](#ejercicio-19)
- [Ejercicio 20 ¿Para que se usa el bloque 127.0.0.0/8?](#ejercicio-20)
- [Ejercicio 21 Investigue para qué sirven los comandos ifconfig y route.](#ejercicio-21)

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">


### Ejercicio 1

¿Qué servicios presta la capa de red?

¿Cuál es la PDU en esta capa?

¿Qué dispositivo es considerado sólo de la capa de red?


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 2

¿Por qué se lo considera un protocolo de mejor esfuerzo?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 3

¿Cuántas redes clase A, B y C hay?

¿Cuántos hosts como máximo pueden tener cada una?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 4

¿Qué son las subredes?

¿Por qué es importante siempre especificar la máscara de subred asociada?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 5

¿Cuál es la finalidad del campo Protocol en la cabecera IP?

¿A qué campos de la capa de transporte se asemeja en su funcionalidad?


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 6

Para cada una de las siguientes direcciones IP (172.16.58.223/26, 163.10.5.49/27, 128.10.1.0/23, 10.1.0.0/24, 8.40.11.179/12) determine:

#### Parte a

¿De qué clase de red es la dirección dada (Clase A, B o C)?

#### Parte b

¿Cuál es la dirección de subred?

#### Parte c

¿Cuál es la cantidad máxima de hosts que pueden estar en esa subred?

#### Parte d

¿Cuál es la dirección de broadcast de esa subred?

#### Parte e

¿Cuál es el rango de direcciones IP válidas dentro de la subred?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 7

Su organización cuenta con la dirección de red 128.50.10.0. Indique:

#### Ejercicio a)

¿Es una dirección de red o de host?

#### Ejercicio b)

Clase a la que pertenece y máscara de clase.

#### Ejercicio c)

Cantidad de hosts posibles.

#### Ejercicio d)

Se necesitan crear, al menos, 513 subredes. Indique:

i. Máscara necesaria.

ii. Cantidad de redes asignables.

iii. Cantidad de hosts por subred.

iv. Dirección de la subred 710.

v. Dirección de broadcast de la subred 710


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 8

Si usted estuviese a cargo de la administración del bloque IP 195.200.45.0/24

#### Parte a

¿Qué máscara utilizaría si necesita definir al menos 9 subredes?

#### Parte b

Indique la dirección de subred de las primeras 9 subredes.

#### Parte c

Seleccione una e indique dirección de broadcast y rango de direcciones asignables en esa 
subred.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 9

Dado el siguiente gráfico:

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/c4d6738b-0a8f-4692-97ed-f150867eee30)

#### Parte a
 
Verifique si es correcta la asignación de direcciones IP y, en caso de no serlo, modifique la misma para que lo sea.
 
#### Parte b
 
¿Cuántos bits se tomaron para hacer subredes en la red 10.0.10.0/24? ¿Cuántas subredes se podrían generar?

#### Parte c

Para cada una de las redes utilizadas indique si son públicas o privadas.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

## CIRD

### Ejercicio 10

¿Qué es CIDR (Class Interdomain routing)?

¿Por qué resulta útil?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 11

¿Cómo publicaría un router las siguientes redes si se aplica CIDR?

- 198.10.1.0/24
- 198.10.0.0/24
- 198.10.3.0/24
- 198.10.2.0/2



<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 12

Listar las redes involucradas en los siguientes bloques CIDR:

- 200.56.168.0/21
- 195.24.0.0/13
- 195.24/13

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 13

El bloque CIDR 128.0.0.0/2 o 128/2, 

¿Equivale a listar todas las direcciones de red de clase B? 

¿Cuál sería el bloque CIDR que agrupa todas las redes de clase A?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### VLSM

### Ejercicio 14

¿Qué es y para qué se usa VLSM?


<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 15

Describa, con sus palabras, el mecanismo para dividir subredes utilizando VLSM.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 16

Suponga que trabaja en una organización que tiene la red que se ve en el gráfico y debe armar el direccionamiento para la misma, minimizando el desperdicio de direcciones IP. Dicha organización posee la red 205.10.192.0/19, que es la que usted deberá utilizar.

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/64885ee2-2455-4020-a151-2696bb91c304)

#### Parte a

¿Es posible asignar las subredes correspondientes a la topología utilizando subnetting sin vlsm? Indique la cantidad de hosts que se desperdicia en cada subred.


#### Parte b

Asigne direcciones a todas las redes de la topología. Tome siempre en cada paso la primer dirección de red posible.


#### Parte c

Para mantener el orden y el inventario de direcciones disponibles, haga un listado de todas las direcciones libres que le quedaron, agrupándolas utilizando CIDR.


#### Parte d

Asigne direcciones IP a todas las interfaces de la topología que sea posible.



<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 17

Utilizando la siguiente topología y el bloque asignado, arme el plan de direccionamiento IPv4 teniendo en cuenta las siguientes restricciones:

Utilizar el bloque IPv4 200.100.8.0/22.

![image](https://github.com/Fabian-Martinez-Rincon/Fabian-Martinez-Rincon/assets/55964635/3b2ea30a-1cd4-45b9-9e9f-147e115608cc)

#### Parte a

La red A tiene 125 hosts y se espera un crecimiento máximo de 20 hosts.

#### Parte b

La red X tiene 63 hosts.

#### Parte c

La red B cuenta con 60 hosts

#### Parte d

La red Y tiene 46 hosts y se espera un crecimiento máximo de 18 hosts.

#### Parte e

En cada red, se debe desperciciar la menor cantidad de direcciones IP posibles. En este 
sentido, las redes utilizadas para conectar los routers deberán utilizar segmentos de red /30 de modo de desperdiciar la menor cantidad posible de direcciones IP.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 18

Asigne direcciones IP en los equipos de la topología según el plan anterior.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

## ICMP y Configuraciones IP

### Ejercicio 19

Describa qué es y para qué sirve el protocolo ICMP

#### Parte a

Analice cómo funciona el comando ping.

i. Indique el tipo y código ICMP que usa el ping.
ii. Indique el tipo y código ICMP que usa la respuesta de un ping.

#### Parte b

Analice cómo funcionan comandos como traceroute/tracert de Linux/Windows y cómo manipulan el campo TTL de los paquetes IP.

#### Parte c

Indique la cantidad de saltos realizados desde su computadora hasta el sitio www.nasa.gov. Analice:

i. Cómo hacer para que no muestre el nombre del dominio asociado a la IP de cada salta.

ii. La razón de la aparición de * en parte o toda la respuesta de un salto.

#### Parte d

Verifique el recorrido hacia los servidores de nombre del dominio unlp.edu.ar. En base al recorrido realizado, ¿podría confirmar cuál de ellos toma un camino distinto?

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">

### Ejercicio 20

¿Para que se usa el bloque 127.0.0.0/8?

¿Qué PC responde a los siguientes comandos?

- **a)** ping 127.0.0.1
- **b)** ping 127.0.54.43

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">


### Ejercicio 21

Investigue para qué sirven los comandos ifconfig y route. ¿Qué comandos podría utilizar en su reemplazo? Inicie una topología con CORE, cree una máquina y utilice en ella los comandos anteriores para practicar sus diferentes opciones, mínimamente:

- Configurar y quitar una dirección IP en una interfaz.
- Ver la tabla de ruteo de la máquina.

<img src= 'https://i.gifer.com/origin/8c/8cd3f1898255c045143e1da97fbabf10_w200.gif' height="20" width="100%">