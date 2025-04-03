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


