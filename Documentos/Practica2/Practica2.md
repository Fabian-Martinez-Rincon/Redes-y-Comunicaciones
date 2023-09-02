<h1 align="center"> Práctica 2 Capa de Aplicación - HTTP</h1>

- [2. ¿Cuál es la función de la capa de aplicación?]()
- [3. Si dos procesos deben comunicarse]()
- [4. Explique brevemente cómo es el modelo Cliente/Servidor.]()
- [5. Describa la funcionalidad de la entidad genérica “Agente de usuario” o “User agent”.]()
- [6. ¿Qué son y en qué se diferencian HTML y HTTP?]()
- [7. Utilizando la VM, abra una terminal. Investigue sobre el comando curl]()
- [8. Ejecute el comando curl sin ningún parámetro adicional y acceda a www.redes.unlp.edu.ar.]()
- [9. Ejecute a continuación los siguientes comandos]()
- [10. Ejecute una vez más el comando curl www.redes.unlp.edu.ar ]()
- [11. Utilizando la VM, realice las siguientes pruebas]()
- [12. En base a lo obtenido en el ejercicio anterior, responda]()
- [13. La página www.redes.unlp.edu.ar/http/idioma.php tiene soporte para visualizarse en inglés y en español.]()
- [14. En el siguiente ejercicio veremos la diferencia entre los métodos POST y GET.]()
- []()

### Introducción


#### Pregunta 2
***¿Cuál es la función de la capa de aplicación?***

La capa de aplicación es donde las aplicaciones de red y sus protocolos residen, es la capa que hace de interfaz entre los ususarios finales y el resto de la red.

#### Pregunta 3
***Si dos procesos deben comunicarse***

***¿pueden hacerlo sin utilizar protocolos de aplicación? Justifique.***

a) Si están en diferentes máquinas, ambos procesos usan sockets que se asocia a un puerto, el cual sirve para enviar o recibir datos entre las máquinas correspondientes.

***Y si están en la misma máquina, ¿qué alternativas existen?***

b) Si están en la misma máquina, pueden usar los mecanismos provistos por sistema operativo basandose en su pid para identificarse

