# 🛡️ Laboratorio de Seguridad: Implementación de DMZ

Este repositorio contiene la configuración de una red segmentada mediante una **Zona Desmilitarizada (DMZ)** realizada en **Cisco Packet Tracer**. El objetivo principal es garantizar la seguridad de una red interna permitiendo servicios públicos controlados.

## 🎯 Objetivo del Proyecto
Configurar un router Cisco como firewall para gestionar el tráfico entre tres zonas distintas:
1.  **LAN (Internal):** Red privada de confianza.
2.  **DMZ:** Zona para servidores públicos (Servidor Web).
3.  **External:** Simulación de tráfico proveniente de Internet.

Se han aplicado técnicas de **NAT Estático** para la publicación de servicios y **Listas de Control de Acceso (ACL)** para mitigar riesgos de seguridad y evitar el acceso no autorizado a la red interna.

---

## 📂 Contenido del Repositorio
El repositorio está organizado de la siguiente manera, cumpliendo con los requisitos de entrega:

* **`DMZ_PROJECT.pkt`**: Archivo original de Cisco Packet Tracer con la topología y configuración completa.
* **`informe/`**: Contiene el `report_DMZ.es.md` con el detalle técnico del proyecto.
* **`CAPTURAS/`**: Capturas de pantalla que demuestran el funcionamiento de las pruebas de conectividad y seguridad.

---

## 🛠️ Tecnologías y Protocolos
* **Simulador:** Cisco Packet Tracer.
* **Seguridad:** Access Control Lists (ACL) Extendidas.
* **Direccionamiento:** IPv4 con NAT Estático.
* **Servicios:** HTTP (Servidor Web en DMZ).

---

## 🧪 Pruebas de Validación
Para confirmar que la configuración es correcta, se realizaron las siguientes validaciones:
1.  **Acceso Externo:** El usuario externo puede visualizar la página web mediante la IP pública configurada.
2.  **Aislamiento de DMZ:** Se comprobó que el servidor en la DMZ **no puede** iniciar conexiones hacia la red interna (LAN), protegiendo los equipos privados.
3.  **Conectividad Interna:** El PC de la red interna tiene acceso total para administrar el servidor.

---

## 🚛 Instrucciones de Entrega
Este proyecto ha sido desarrollado siguiendo la estructura solicitada por 4Geeks Academy, incluyendo informe técnico y evidencias visuales de cada paso.
