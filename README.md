Skip to content
Ceci0405
dmz-lab
Repository navigation
Code
Issues
Pull requests
Actions
Projects
Wiki
Security
Insights
Settings
Files
Go to file
t
CAPTURAS
DMZ_PROJECT.pka
Informe Técnico_ Implementación de Arquitectura de Red Segura (DMZ).pdf
README.es.md
report_DMZ.es.md
dmz-lab
/
README.es.md
in
main

Edit

Preview
Indent mode

Spaces
Indent size

2
Line wrap mode

Soft wrap
Editing README.es.md file contents
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
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

Use Control + Shift + m to toggle the tab key moving focus. Alternatively, use esc then tab to move to the next interactive element on the page.
Ningún archivo seleccionado
Attach files by dragging & dropping, selecting or pasting them.
