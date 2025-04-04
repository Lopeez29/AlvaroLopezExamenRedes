# Documentación de Red – Conexión entre Ciudades Remotas

## Descripción General

Este diseño representa una red que conecta dos ciudades remotas utilizando routers Cisco 2911 con **enrutamiento estático**. Cada ciudad cuenta con una red local compuesta por un switch y dos computadoras.

---

## Topología

### Router0 (Ciudad A)
- **Red LAN:** `192.168.1.0/24`
- **Switch conectado:** Switch0
- **Dispositivos:** PC0 y PC1 conectados al switch

### Router1 (Ciudad B)
- **Red LAN:** `192.168.100.0/24`
- **Switch conectado:** Switch1
- **Dispositivos:** PC2 y PC3 conectados al switch

### Enlace Serial entre Routers
- **Red del enlace:** `192.168.10.0/30`
- **IP Router0 (Serial):** `192.168.10.1/30`
- **IP Router1 (Serial):** `192.168.10.2/30`

---

## Enrutamiento Estático

Para permitir la comunicación entre las redes locales de ambas ciudades, se configura enrutamiento estático:

### En Router0
```bash
ip route 192.168.100.0 255.255.255.0 192.168.10.2
ip route 192.168.1.0 255.255.255.0 192.168.10.1


## Resumen de Equipos

| Dispositivo | Interfaz        | Dirección IP        | Red               |
|-------------|------------------|---------------------|--------------------|
| PC0         | FastEthernet0    | 192.168.1.2         | 192.168.1.0/24     |
| PC1         | FastEthernet0    | 192.168.1.3         | 192.168.1.0/24     |
| Router0     | G0/0 (LAN)       | 192.168.1.1         | 192.168.1.0/24     |
| Router0     | Serial0/0/0      | 192.168.10.1        | 192.168.10.0/30    |
| Router1     | Serial0/0/0      | 192.168.10.2        | 192.168.10.0/30    |
| Router1     | G0/0 (LAN)       | 192.168.100.1       | 192.168.100.0/24   |
| PC2         | FastEthernet0    | 192.168.100.2       | 192.168.100.0/24   |
| PC3         | FastEthernet0    | 192.168.100.3       | 192.168.100.0/24   |

