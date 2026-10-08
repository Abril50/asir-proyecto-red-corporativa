## 3. Diseño de la arquitectura
El diseño de la arquitectura de red corporativa para TechMarbella Solutions S.L. se basa en los requisitos definidos en el capítulo anterior y en las buenas prácticas de administración de sistemas y seguridad. La solución propuesta busca garantizar la disponibilidad, seguridad, escalabilidad y eficiencia de los servicios corporativos.
## 3.1 Visión general de la arquitectura
La infraestructura se compone de:
- Dos firewalls perimetrales configurados en alta disponibilidad para garantizar la continuidad del servicio ante fallos. 
- Un switch gestionable que permite la segmentación mediante VLANs.
- Un servidor Windows Server para servicios corporativos (AD DS, DNS, DHCP, servidor de archivos y aplicación de políticas mediante GPO). 
- Un servidor Linux para servicios de monitorización, gestión de eventos, IDS/IPS, intranet corporativa y automatización de tareas.
- Una plataforma de virtualización que permita desplegar y administrar los diferentes servidores de forma centralizada. 
- Una plataforma de monitorización y análisis de eventos para la supervisión continua de la infraestructura. 
- Un sistema de almacenamiento centralizado destinado a copias de seguridad, registros de eventos y documentación corporativa.
- Un sistema de copias de seguridad automatizado para garantizar la recuperación de la información ante incidencias.
- Un sistema de auditoría informática basado en el análisis de registros y eventos de seguridad.
- Una VPN corporativa para acceso remoto seguro.
- Estaciones de trabajo distribuidas en tres departamentos: Administración, Desarrollo y Soporte Técnico.
## 3.2 Segmentación de red mediante VLANs
Para mejorar la seguridad y el rendimiento, la red se segmenta en VLANs:
| Departamento / Servicio        | VLAN | Descripción                                      |
|--------------------------------|------|--------------------------------------------------|
| Administración                 | 10   | Gestión financiera y administrativa              |
| Desarrollo                     | 20   | Equipos de programación y pruebas                |
| Soporte Técnico                | 30   | Técnicos y herramientas de diagnóstico           |
| Servidores                     | 40   | Segmento aislado para servicios críticos         |
| Gestión / Administración de red| 50   | Acceso restringido para administradores          |
| Invitados                      | 60   | Red aislada para dispositivos externos           |
Cada VLAN tiene su propio rango de direcciones IP y políticas de acceso específicas.
## 3.3 Tabla de direccionamiento IP
La tabla de direccionamiento propuesta es:
| VLAN | Red | Gateway | Máscara |
|------|----------|---------|---------|
| 10   | 192.168.10.0/24 | 192.168.10.1 | 255.255.255.0 |
| 20   | 192.168.20.0/24 | 192.168.20.1 | 255.255.255.0 |
| 30   | 192.168.30.0/24 | 192.168.30.1 | 255.255.255.0 |
| 40   | 192.168.40.0/24 | 192.168.40.1 | 255.255.255.0 |
| 50   | 192.168.50.0/24 | 192.168.50.1 | 255.255.255.0 |
| 60   | 192.168.60.0/24 | 192.168.60.1 | 255.255.255.0 |
El firewall se encarga del enrutamiento inter-VLAN y de aplicar las políticas de seguridad.
## 3.3.1 Justificación del direccionamiento IP
Se ha optado por utilizar direcciones privadas dentro del rango 192.168.0.0/16 debido a su simplicidad de administración y amplia compatibilidad con entornos empresariales.
 
Cada VLAN dispone de una subred independiente de tipo /24, permitiendo una correcta segregación del tráfico y facilitando la gestión de los distintos departamentos de la empresa.
 
Esta estructura permite ampliar la infraestructura en el futuro manteniendo una organización lógica y escalable.
## 3.4 Componentes principales de la arquitectura 
### Firewall perimetral 
Responsable de proteger la red corporativa mediante filtrado de tráfico, NAT, VPN y control de acceso entre VLANs. 
### Switch gestionable
Permite la segmentación de la red mediante VLANs y la conexión de los distintos segmentos de la infraestructura. 
### Servidor Windows Server 
Proporciona servicios de directorio activo, DNS, DHCP, servidor de archivos y aplicación de políticas de grupo.
### Servidor Linux 
Aloja servicios de seguridad, monitorización, automatización e intranet corporativa.
### Plataforma de virtualización 
Permite la ejecución de múltiples máquinas virtuales sobre una infraestructura física común.
### Sistema de monitorización
Facilita la supervisión continua de servidores, dispositivos de red y aplicaciones.
### Sistema de copias de seguridad
Garantiza la disponibilidad y recuperación de la información.
### Sistema de auditoría informática
Permite registrar y analizar eventos relacionados con la seguridad de la infraestructura.
## 3.4.1 Virtualización de servicios 
La plataforma de virtualización seleccionada para el proyecto será Proxmox VE, solución de código abierto que permitirá desplegar y administrar las diferentes máquinas virtuales que forman parte de la infraestructura corporativa.
Proxmox VE permitirá la gestión centralizada de máquinas virtuales, snapshots, copias de seguridad y restauración de servicios críticos.
Con el fin de optimizar recursos hardware y facilitar la gestión de la infraestructura, los servicios corporativos se desplegarán mediante virtualización.
La plataforma de virtualización permitirá ejecutar múltiples máquinas virtuales sobre un mismo servidor físico, reduciendo costes y simplificando las tareas de administración, mantenimiento y recuperación ante incidencias.
 
Las máquinas virtuales previstas son:
- Windows Server.
- Servidor Linux de monitorización.
- Servidor de copias de seguridad.
- Servidor de pruebas y laboratorio.
 
La utilización de virtualización facilita además la escalabilidad futura de la infraestructura.
## 3.4.2 Monitorización y gestión de eventos
La infraestructura contará con una plataforma centralizada de monitorización que permitirá supervisar el estado de los servidores, dispositivos de red y servicios corporativos.
 
Las principales funciones serán:
 
- Supervisión de CPU, memoria y almacenamiento.
- Monitorización de disponibilidad de servicios.
- Generación de alertas ante incidencias.
- Registro de eventos y análisis de logs.
- Detección temprana de posibles fallos.
   
Para ello se utilizarán herramientas como Wazuh, Zabbix o Prometheus.
## 3.4.3 Auditoría informática  
La arquitectura ha sido diseñada considerando la futura realización de auditorías de seguridad y cumplimiento.
 
Todos los sistemas generarán registros de actividad susceptibles de ser analizados durante el proceso de auditoría informática, permitiendo evaluar la seguridad de la infraestructura y el cumplimiento de las políticas corporativas.
## 3.4.4 Sistema de almacenamiento 
La infraestructura dispondrá de un sistema de almacenamiento centralizado destinado al almacenamiento de copias de seguridad, registros de auditoría y documentación corporativa.
El sistema de almacenamiento utilizará una configuración RAID 1 con el objetivo de proporcionar redundancia de datos y minimizar la pérdida de información ante el fallo de un disco.
 
Sus funciones principales serán:
 
- Almacenamiento de copias de seguridad.
- Conservación de registros de eventos.
- Compartición de recursos corporativos.
- Almacenamiento de documentación técnica.
- Soporte a los procesos de recuperación ante desastres.
 
Este sistema podrá implementarse mediante un NAS corporativo o un servidor de almacenamiento dedicado.
## 3.5 Diagrama lógico de la arquitectura
### Elementos representados en el diagrama
- Firewall
- Switch gestionable
- VLANs
- Servidores
- Estaciones de trabajo
- VPN
- IDS/IPS
- Sistema de backups
## 3.5.1 Diagrama físico de la infraestructura
Además del diagrama lógico, se elaborará un diagrama físico que representará la distribución de los principales elementos hardware de la infraestructura:
 
- Firewall
- Switch gestionable
- Servidores
- Equipos cliente
- Puntos de acceso
- Almacenamiento de copias de seguridad
 
Este diagrama facilitará la comprensión de la arquitectura y servirá como documentación técnica para futuras tareas de mantenimiento.
## 3.5.2 Entorno de simulación
La simulación de la infraestructura de red se realizará mediante GNS3, desplegado sobre una máquina virtual alojada en Proxmox VE.
Con el fin de validar la arquitectura propuesta antes de su implantación, se utilizará la plataforma GNS3 para simular la infraestructura corporativa.
Las pruebas realizadas en GNS3 servirán como evidencia de validación de la infraestructura propuesta y formarán parte de la fase de pruebas descrita en capítulos posteriores.

El entorno permitirá verificar:
- Conectividad entre VLANs.
- Funcionamiento de los servicios corporativos.
- Políticas de seguridad.
- Redundancia de firewall.
- Acceso remoto mediante VPN.
- Monitorización y generación de eventos.

La utilización de GNS3 facilita la realización de pruebas sin necesidad de disponer de equipamiento físico completo.
## 3.6 Políticas de acceso entre VLANs
- Administración puede acceder a Servidores.
- Desarrollo solo accede a su VLAN y a servicios corporativos.
- Soporte Técnico tiene acceso controlado a todas las VLANs.
- Invitados no tienen acceso a recursos internos.
- La VLAN de servidores está aislada excepto para tráfico autorizado.
## 3.7 Consideraciones de seguridad
- Segmentación estricta entre departamentos.
- Firewall con reglas específicas por VLAN.
- IDS/IPS monitorizando tráfico interno y externo.
- Autenticación centralizada mediante AD DS.
- Copias de seguridad automatizadas.
- VPN con cifrado fuerte.
## 3.7.1 Política de copias de seguridad
Política de copias de seguridad
 
Para garantizar la disponibilidad y recuperación de la información se implementará una estrategia de copias de seguridad basada en:
 
- Copias incrementales diarias.
- Copias completas semanales.
- Verificación periódica de restauración.
- Almacenamiento seguro de los respaldos.
 
Esta política permitirá minimizar la pérdida de datos ante fallos técnicos o incidentes de seguridad.
## 3.7.2 Acceso remoto seguro
Acceso remoto seguro
 
Los usuarios autorizados podrán acceder a los recursos corporativos mediante una VPN cifrada.
 
Este sistema permitirá el teletrabajo manteniendo la confidencialidad e integridad de las comunicaciones entre los usuarios remotos y la infraestructura corporativa.
## 3.8 Redundancia y alta disponibilidad
### 3.8.1 Redundancia de conectividad
La empresa dispondrá de una conexión principal y una conexión secundaria a Internet. En caso de fallo de la conexión principal, el tráfico podrá redirigirse automáticamente a la conexión de respaldo.
### 3.8.2 Redundancia de firewall
La infraestructura contempla dos firewalls en alta disponibilidad, permitiendo que uno asuma las funciones del otro en caso de incidencia.
### 3.8.3 Redundancia de servidores
Los servicios críticos estarán virtualizados y respaldados mediante copias de seguridad periódicas y snapshots de Proxmox VE, facilitando su recuperación ante fallos y reduciendo el tiempo de recuperación ante incidencias.
### 3.8.4 Beneficios de la alta disponibilidad
Los mecanismos de redundancia permitirán:
- Reducir los tiempos de inactividad.
- Mejorar la disponibilidad de los servicios.
- Incrementar la resiliencia de la infraestructura.
- Garantizar la continuidad operativa de la empresa.
## 3.9 Conclusión del diseño
La arquitectura propuesta proporciona una infraestructura segura, escalable y eficiente, alineada con las necesidades de TechMarbella Solutions S.L. y con las buenas prácticas de administración de sistemas. Este diseño servirá como base para la implementación detallada en el capítulo siguiente.
