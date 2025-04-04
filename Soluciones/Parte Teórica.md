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

- **Subred 1:** 192.168.50.0 - 192.168.50.63  
- **Subred 2:** 192.168.50.64 - 192.168.50.127  
- **Subred 3:** 192.168.50.128 - 192.168.50.191  
- **Subred 4:** 192.168.50.192 - 192.168.50.255  


**Pregunta 4:**  
*¿Qué concepto moderno de redes representa el tótem con flechas de la encrucijada? Explica qué es una tabla de enrutamiento y cómo funciona en un router actual. Además, interpreta la diferencia entre las flechas talladas en piedra y las flechas móviles en términos de enrutamiento estático vs. enrutamiento dinámico en redes.*

**Respuesta:**  
El tótem representa un **router**, un dispositivo que dirige el tráfico de datos entre diferentes redes. Cada “aldea” simboliza una **red distinta**.

- **Tabla de Enrutamiento:**  
  Una **tabla de enrutamiento** es una base de datos interna en el router que almacena información sobre las rutas disponibles para llegar a diferentes destinos. Esta tabla incluye datos como:  
  - La **dirección de la red destino**.  
  - La **máscara de subred** asociada.  
  - El **próximo salto** a continuación.  
  - La **interfaz de salida** por la que se debe enviar el paquete.  
  - Una métrica o cantidad de saltos mínimos necesarios para alcanzar el destino.  

- **Enrutamiento Estático vs. Enrutamiento Dinámico:**  
  - Las **flechas talladas en piedra** simbolizan el **enrutamiento estático**, donde las rutas se configuran manualmente y permanecen fijas a menos que alguien las modifique.  
  - Las **flechas móviles** representan el **enrutamiento dinámico**, en el cual las rutas se determinan automáticamente mediante algoritmos.
  - *Ventaja del enrutamiento dinámico:* Automatiza la adaptación a cambios, reduciendo la necesidad de intervención manual.  
  - *Desventaja:* Consume más ancho de banda y puede ser menos seguro en comparación con las rutas estáticas.


**Pregunta 5:**  
*¿Qué técnica de redes moderna se refleja en la leyenda del Guardián de la Máscara? Nombra y describe brevemente este mecanismo, explicando cómo permite que múltiples dispositivos internos de una red compartan una única identidad (dirección) al comunicarse con el exterior, y menciona dos beneficios que brinda esta estrategia a las redes actuales.*

**Respuesta:**  
El guardián de la máscara es una metáfora de **NAT**, concretamente de un tipo de NAT dinámico. Este mecanismo permite que varios dispositivos dentro de una red privada, que poseen direcciones IP internas únicas, compartan una sola dirección IP pública cuando se comunican con el exterior. El router realiza esta tarea asignando diferentes puertos a cada dispositivo, de modo que, al recibir la respuesta, sepa a qué dispositivo interno corresponde cada paquete basándose en el puerto utilizado.

Esta estrategia evita la necesidad de comprar múltiples direcciones IP públicas, lo cual es especialmente importante y necesitado ante la escasez de direcciones IPv4. Además, NAT añade una capa extra de privacidad, ya que las direcciones internas de los dispositivos permanecen ocultas para el exterior, protegiendo así la red de accesos no autorizados.


