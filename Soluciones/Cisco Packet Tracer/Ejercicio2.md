# Documentación de Red – Red Aislada con VLANs y Switch Core

## Descripción General

Esta red representa una **infraestructura aislada con VLANs**, donde un **router actúa como gateway** entre VLANs para permitir la comunicación entre ellas (**Router-on-a-Stick**). El **Switch0** funciona como **switch core**, encargado de distribuir el tráfico entre los switches de acceso (**Switch1 y Switch2**) usando **enlaces troncales (trunk)** y el protocolo **VTP** para la propagación de información de VLANs.

---

## Topología

- **Router0 (Modelo ISR 4331)**: Encargado del enrutamiento entre VLANs (router-on-a-stick).
- **Switch0 (Core)**: Switch principal conectado al router y a los switches de acceso.
- **Switch1 y Switch2 (de acceso)**: Conectan PCs de diferentes VLANs.

---

## VLANs y Dispositivos

| VLAN | Nombre       | Dispositivos asignados |
|------|--------------|------------------------|
| 10   | vlan10     | PC0, PC1               |
| 20   | vlan20     | PC2, PC3               |

---

## Enlaces Troncales (Trunk)

Los puertos que conectan **Switch0 con Switch1 y Switch2** están configurados como **trunk**, permitiendo que las VLANs pasen entre switches a través del **VTP**.

---

## Configuración General

### En el Router0 (Router-on-a-Stick)
```bash
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

interface GigabitEthernet0/0.30
encapsulation dot1Q 30
ip address 192.168.30.1 255.255.255.0


vtp mode server
vtp domain empresa


vtp mode client
vtp domain empresa


vtp mode client
vtp domain empresa


interface GigabitEthernetX/X
switchport mode trunk
