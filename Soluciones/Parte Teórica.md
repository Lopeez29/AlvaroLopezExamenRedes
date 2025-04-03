**Pregunta 1:**  
*¿Qué representa el mural de las siete capas en términos de las redes de comunicación modernas? Identifica brevemente cada capa y explica cómo se relaciona este antiguo “modelo” con el proceso de comunicación de datos actual.*

**Respuesta:**  
El mural **simboliza las siete capas** del modelo OSI, que estructuran el proceso de comunicación de datos en las redes modernas. A continuación, se describe brevemente cada capa:

1. **Capa Física**  
   Se encarga de la **transmisión de bits** a través de medios físicos, como cables y señales eléctricas. Es la base que permite la comunicación a nivel de hardware.

2. **Capa de Enlace de Datos**  
   Gestiona la **transferencia de datos en redes locales**, utilizando dispositivos como switches y empleando **direcciones MAC** para identificar de forma única a cada dispositivo en el mismo segmento.

3. **Capa de Red**  
   Facilita el **encaminamiento de datos entre diferentes redes**. Mediante el uso de routers y **direcciones IP**, esta capa determina la ruta óptima para la transmisión de la información.

4. **Capa de Transporte**  
   Se encarga de la **entrega fiable de los datos** entre dispositivos. Utiliza protocolos como **TCP** y **UDP** 

5. **Capa de Sesión**  
   Establece, mantiene y finaliza las **conexiones entre dispositivos**. Coordina el diálogo y la sincronización durante la comunicación, asegurando que ambas partes estén listas para intercambiar información.

6. **Capa de Presentación**  
   Realiza la **traducción, codificación, decodificación y compresión** de los datos, garantizando que la información se presente en un formato adecuado para la capa de aplicación.

7. **Capa de Aplicación**  
   Es el punto de interacción directa con el usuario, conectando las **aplicaciones a la red** a través de servicios y protocolos como **DNS** y **FTP**.

En conjunto, estas capas trabajan de forma integrada para que el proceso de comunicación de datos sea eficiente, reflejando en la práctica moderna el antiguo “modelo” representado en el mural.


**Pregunta 2:**  
*Interpreta los dos rituales descritos. ¿A qué protocolos de comunicación actuales equivalen el mensajero confiable y el mensajero veloz? Compara sus características, explicando las ventajas y desventajas de cada enfoque en redes modernas.*

**Respuesta:**  
Los rituales hacen referencia a dos protocolos esenciales en la **capa de transporte**: **TCP** y **UDP**.

- **Mensajero Confiable (TCP):**  
  Este ritual se corresponde con **TCP**, ya que implica un proceso de establecimiento y finalización de conexión (por ejemplo, mediante un saludo de tres vías) y requiere que cada paquete enviado reciba una **confirmación** de su destino. Esto asegura la **fiabilidad y precisión** de la información transmitida, lo cual es fundamental para aplicaciones donde los datos deben llegar completos y en orden, como la transferencia de archivos o la mensajería de texto.  
  *Ventaja:* Garantiza la integridad y secuencia de los datos.  
  *Desventaja:* Su proceso de verificación adicional reduce la velocidad de transmisión.

- **Mensajero Veloz (UDP):**  
  El ritual del mensajero veloz se asocia con **UDP**, un protocolo que omite el proceso de verificación y no establece una conexión previa. No se envían confirmaciones para cada paquete, lo que permite una **transmisión más rápida**. Esta característica es especialmente útil en aplicaciones en tiempo real, como el **streaming** de audio y video, donde la velocidad es prioritaria sobre la precisión total.  
  *Ventaja:* Alta velocidad en la transmisión de datos.  
  *Desventaja:* Menor confiabilidad, ya que no se asegura la entrega de todos los paquetes.


  **Pregunta 3:**  
*Descifra el enigma de la losa. Si la antigua red usaba la dirección 192.168.50.0 como base y necesitaba dividirse en 4 subredes de igual tamaño (una para cada gremio), ¿qué máscara de subred habrían utilizado los antiguos para lograrlo? ¿Cuántas direcciones de host (utilizables) tendría cada subred resultante? Explica brevemente tu razonamiento al calcular la máscara.*

**Respuesta:**  
Para dividir la red **192.168.50.0/24** en 4 subredes iguales, debemos seleccionar **2 bits** del campo de host, lo que nos lleva a una nueva máscara de **/26** (Al "seleccionar" esos 2 bits de los 8 de hosts, la nueva máscara se convierte en **/24 + 2 = /26**.). Esto significa lo siguiente:

- Cada subred tendrá **2^(8-2) = 2^6 = 64** direcciones totales (el 2 viene de los posibles casos 0 o 1 mientras que el exponente se define según los bits que has tomado prestado para crear las subredes que necesites).
- De estas, la **primera dirección** se reserva para identificar la subred (dirección de red) y la **última** para el broadcast, dejando **64 - 2 = 62 direcciones de host utilizables** en cada subred.

Las subredes quedarían distribuidas de la siguiente manera:

1. **Subred 1:** 192.168.50.0 - 192.168.50.63  
2. **Subred 2:** 192.168.50.64 - 192.168.50.127  
3. **Subred 3:** 192.168.50.128 - 192.168.50.191  
4. **Subred 4:** 192.168.50.192 - 192.168.50.255  





