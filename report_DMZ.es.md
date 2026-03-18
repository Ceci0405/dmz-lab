
# Informe de configuración de DMZ con Cisco Packet Tracer


### 1. Objetivo del laboratorio

> Explica brevemente qué se buscaba lograr con este laboratorio.

**Ejemplo:**  
Configurar una DMZ segura usando un router Cisco ISR, aplicando NAT y ACLs para controlar el tráfico entre LAN, DMZ y red externa.

Configurar una arquitectura de red segmentada para proteger una red interna (LAN) mediante una Zona Desmilitarizada (DMZ). Se busca permitir el acceso público a un servidor web mediante NAT Estático y restringir el tráfico malicioso o innecesario desde la DMZ hacia la LAN mediante ACLs.

### 2. Topología implementada

Cantidad de redes: 3 redes (LAN, DMZ y Externa/Internet).

Dispositivos usados: Router Cisco 2911 (Firewall), Switches 2960, Server-PT (Web), y 2 PCs.

Descripción de zonas:

LAN: Zona privada y segura para usuarios internos.

DMZ: Zona para servidores públicos; accesible desde fuera pero aislada de la LAN.

Externa: Simulación de Internet desde donde se accede a los servicios.



### 3. Plan de direccionamiento IP

Completa la tabla con las IPs asignadas (puedes copiarla del enunciado si no cambió).

| Dispositivo             | IP              | Máscara           | Gateway           |
|-------------------------|------------------|-------------------|-------------------|
| PC_Internal             |192.168.10.10     |255.255.255.0      | 192.168.10.1      |
| Server_DMZ              |172.16.0.10       |255.255.255.0      | 172.16.0.1        |
| PC_External             |200.0.0.10        |255.255.255.0      |200.0.0.1          |
| Router_FW Gi0/0 (LAN)   |192.168.10.1      |255.255.255.0      |                   |
| Router_FW Gi0/1 (DMZ)   |192.168.10.1      |255.255.255.0      |                   |
| Router_FW Gi0/2 (Ext)   |200.0.0.1         |255.255.255.0      |                   |


### 4. Configuración aplicada (resumen)

Configuración de Interfaces: Se asignaron IPs y se definieron los roles de NAT (ip nat inside en Gi0/0 y Gi0/1; ip nat outside en Gi0/2).

NAT: Se creó un mapeo estático para el servidor web.
`ip nat inside source static 172.16.0.10 200.0.0.100`
ACLs: Se creó una lista de control de acceso para proteger la LAN.

`ip access-list extended SEGURIDAD_DMZ`
 `permit tcp any host 172.16.0.10 eq 80`
 `deny ip 172.16.0.0 0.0.0.255 192.168.10.0 0.0.0.255`
 `permit ip any any`


### 5. Verificaciones realizadas

> Describe las pruebas y su resultado. Incluye capturas o salidas de comandos si se puede.

- `ping` desde PC_Internal al router: ✅
- Acceso web desde PC_External: ✅
- Bloqueo de acceso desde DMZ a LAN: ✅


### 6. Conclusiones y recomendaciones

> ¿Qué aprendiste con este ejercicio? ¿Qué mejorarías?
Aprendí que la DMZ es una capa de seguridad crítica. Aunque un servidor sea público, nunca debe tener permiso para iniciar conexiones hacia la red privada. Recomiendo siempre verificar los Gateway de los dispositivos antes de configurar las ACL para evitar falsos errores.

**Ejemplo:**
Aprendí a aplicar NAT y ACLs en un entorno simulado. Recomiendo verificar conectividad básica antes de aplicar reglas de firewall, ya que un error en la IP puede bloquear todo.


### 7. Capturas de evidencia
En el propio repositorio hay una carpeta llamada Capturas, en ella se adjuntan todas las evidencias 
`acceso a la pagina web.png` (Muestra la web cargando desde el exterior).
`ip pc iunterno.png` (Muestra el ping fallido desde el servidor a la LAN).
`pc interno haciendo ping.png` (Muestra el ping exitoso del PC interno al servidor).
`show ip.png` (Muestra la tabla de NAT en el router).