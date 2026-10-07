**3. Diseño de la arquitectura**
El diseño de la arquitectura de red corporativa para TechMarbella Solutions S.L. se basa en los requisitos definidos en el capítulo anterior y en las buenas prácticas de administración de sistemas y seguridad. La solución propuesta busca garantizar la disponibilidad, seguridad, escalabilidad y eficiencia de los servicios corporativos.

**3.1 Visión general de la arquitectura**

La infraestructura se compone de:

Un firewall perimetral que actúa como punto de entrada y salida de la red.

Un switch gestionable que permite la segmentación mediante VLANs.

Un servidor Windows Server para servicios corporativos (AD DS, DNS, DHCP, servidor de archivos).

Un servidor Linux para servicios de monitorización, IDS/IPS y utilidades.

Una VPN corporativa para acceso remoto seguro.

Un sistema de copias de seguridad centralizado.

Una intranet corporativa alojada en el servidor Linux.

Estaciones de trabajo distribuidas en tres departamentos: Administración, Desarrollo y Soporte Técnico.

La arquitectura está diseñada para ser modular y escalable, permitiendo añadir nuevos servicios o departamentos sin reestructurar la red.

## 3.3.1 Justificación del direccionamiento IP

### Justificación del direccionamiento IP
 
Se ha optado por utilizar direcciones privadas dentro del rango 192.168.0.0/16 debido a su simplicidad de administración y amplia compatibilidad con entornos empresariales.
 
Cada VLAN dispone de una subred independiente de tipo /24, permitiendo una correcta segregación del tráfico y facilitando la gestión de los distintos departamentos de la empresa.
 
Esta estructura permite ampliar la infraestructura en el futuro manteniendo una organización lógica y escalable.

**3.2 Segmentación de red mediante VLANs**

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

**3.3 Tabla de direccionamiento IP**

La tabla de direccionamiento propuesta es:

| VLAN | Rango IP | Gateway | Máscara |
|------|----------|---------|---------|
| 10   | 192.168.10.0/24 | 192.168.10.1 | 255.255.255.0 |
| 20   | 192.168.20.0/24 | 192.168.20.1 | 255.255.255.0 |
| 30   | 192.168.30.0/24 | 192.168.30.1 | 255.255.255.0 |
| 40   | 192.168.40.0/24 | 192.168.40.1 | 255.255.255.0 |
| 50   | 192.168.50.0/24 | 192.168.50.1 | 255.255.255.0 |
| 60   | 192.168.60.0/24 | 192.168.60.1 | 255.255.255.0 |

El firewall se encarga del enrutamiento inter-VLAN y de aplicar las políticas de seguridad.

## 3.4 Componentes principales de la arquitectura
 
### Firewall perimetral
 
- Filtrado de tráfico entrante y saliente.
- NAT y Port Forwarding.
- VPN corporativa.
- Control de acceso entre VLANs.
 
### Switch gestionable
 
- Creación y gestión de VLANs.
- Trunking hacia el firewall.
- QoS para priorizar tráfico crítico.
 
### Servidor Windows Server
 
- Active Directory Domain Services (AD DS).
- Gestión centralizada de usuarios y grupos.
- DNS y DHCP corporativos.
- Servidor de archivos.
- Aplicación de políticas mediante GPO.
 
### Servidor Linux
 
- IDS/IPS mediante Suricata.
- Plataforma de monitorización.
- Intranet corporativa.
- Scripts de automatización.
 
### Plataforma de monitorización y gestión de eventos
 
- Monitorización de servidores y dispositivos de red.
- Gestión y análisis de logs.
- Generación de alertas.
- Detección temprana de incidencias.
 
**Herramientas previstas:**
- Wazuh.
- Zabbix.
- Prometheus.
 
### Plataforma de virtualización
 
Con el fin de optimizar los recursos hardware y facilitar la administración de los sistemas, la infraestructura utilizará tecnología de virtualización.
 
Las máquinas virtuales previstas son:
 
- Windows Server.
- Servidor Linux de monitorización.
- Servidor de copias de seguridad.
- Entorno de pruebas y laboratorio.
 
### Sistema de copias de seguridad
 
- Copias incrementales diarias.
- Copias completas semanales.
- Almacenamiento en NAS o servidor dedicado.
- Verificación periódica de restauración.
 
### Sistema de auditoría informática
 
La infraestructura incorporará mecanismos de registro y auditoría que permitirán:
 
- Registrar eventos de seguridad.
- Supervisar accesos de usuarios.
- Analizar incidencias.
- Facilitar futuras auditorías de cumplimiento y seguridad.

   ## 3.4.1 Virtualización
  
Virtualización de servicios. 

 
Con el fin de optimizar recursos hardware y facilitar la gestión de la infraestructura, los servicios corporativos se desplegarán mediante virtualización.
 
La plataforma de virtualización permitirá ejecutar múltiples máquinas virtuales sobre un mismo servidor físico, reduciendo costes y simplificando las tareas de administración, mantenimiento y recuperación ante incidencias.
 
Las máquinas virtuales previstas son:
 
1 - Windows Server
2 - Servidor Linux de monitorización
3 - Servidor de copias de seguridad
4 - Servidor de pruebas
 
La utilización de virtualización facilita además la escalabilidad futura de la infraestructura.

**3.4.2 Monitorización y gestión de eventos**

Sistema de monitorización y gestión de eventos

La infraestructura contará con una plataforma centralizada de monitorización que permitirá supervisar el estado de los servidores, dispositivos de red y servicios corporativos.
 
Las principales funciones serán:
 
- Supervisión de CPU, memoria y almacenamiento.
- Monitorización de disponibilidad de servicios.
- Generación de alertas ante incidencias.
- Registro de eventos y análisis de logs.
- Detección temprana de posibles fallos.
 
Para ello se utilizarán herramientas como Wazuh, Zabbix o Prometheus.

**3.4.3 Auditoría informática**

Integración de la auditoría informática
 
La arquitectura ha sido diseñada considerando la futura realización de auditorías de seguridad y cumplimiento.
 
Todos los sistemas generarán registros de actividad susceptibles de ser analizados durante el proceso de auditoría informática, permitiendo evaluar la seguridad de la infraestructura y el cumplimiento de las políticas corporativas.
Mostrar más líneas
  

**3.5 Diagrama lógico de la arquitectura**

El diagrama mostrará:

Firewall

Switch gestionable

VLANs

Servidores

Estaciones de trabajo

VPN

IDS/IPS

Sistema de backups

**3.5.1 Diagrama físico de la infraestructura**


Además del diagrama lógico, se elaborará un diagrama físico que representará la distribución de los principales elementos hardware de la infraestructura:
 
- Firewall
- Switch gestionable
- Servidores
- Equipos cliente
- Puntos de acceso
- Almacenamiento de copias de seguridad
 
Este diagrama facilitará la comprensión de la arquitectura y servirá como documentación técnica para futuras tareas de mantenimiento.


**3.6 Políticas de acceso entre VLANs**

Administración puede acceder a Servidores.

Desarrollo solo accede a su VLAN y a servicios corporativos.

Soporte Técnico tiene acceso controlado a todas las VLANs.

Invitados no tienen acceso a recursos internos.

La VLAN de servidores está aislada excepto para tráfico autorizado.

**3.7 Consideraciones de seguridad**

Segmentación estricta entre departamentos.

Firewall con reglas específicas por VLAN.

IDS/IPS monitorizando tráfico interno y externo.

Autenticación centralizada mediante AD DS.

Copias de seguridad automatizadas.

VPN con cifrado fuerte.

**3.7.1 Política de copias de seguridad**

Política de copias de seguridad
 
Para garantizar la disponibilidad y recuperación de la información se implementará una estrategia de copias de seguridad basada en:
 
- Copias incrementales diarias.
- Copias completas semanales.
- Verificación periódica de restauración.
- Almacenamiento seguro de los respaldos.
 
Esta política permitirá minimizar la pérdida de datos ante fallos técnicos o incidentes de seguridad.

**3.7.2 Acceso remoto seguro**

Acceso remoto seguro
 
Los usuarios autorizados podrán acceder a los recursos corporativos mediante una VPN cifrada.
 
Este sistema permitirá el teletrabajo manteniendo la confidencialidad e integridad de las comunicaciones entre los usuarios remotos y la infraestructura corporativa.

**3.8 Conclusión del diseño**

La arquitectura propuesta proporciona una infraestructura segura, escalable y eficiente, alineada con las necesidades de TechMarbella Solutions S.L. y con las buenas prácticas de administración de sistemas. Este diseño servirá como base para la implementación detallada en el capítulo siguiente.
