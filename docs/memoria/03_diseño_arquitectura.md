3. Diseño de la arquitectura
El diseño de la arquitectura de red corporativa para TechMarbella Solutions S.L. se basa en los requisitos definidos en el capítulo anterior y en las buenas prácticas de administración de sistemas y seguridad. La solución propuesta busca garantizar la disponibilidad, seguridad, escalabilidad y eficiencia de los servicios corporativos.

3.1 Visión general de la arquitectura
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

3.2 Segmentación de red mediante VLANs
Para mejorar la seguridad y el rendimiento, la red se segmenta en VLANs:




Cada VLAN tiene su propio rango de direcciones IP y políticas de acceso específicas.

3.3 Tabla de direccionamiento IP
La tabla de direccionamiento propuesta es:

VLAN	Rango IP	Gateway	Máscara
10	192.168.10.0/24	192.168.10.1	255.255.255.0
20	192.168.20.0/24	192.168.20.1	255.255.255.0
30	192.168.30.0/24	192.168.30.1	255.255.255.0
40	192.168.40.0/24	192.168.40.1	255.255.255.0
50	192.168.50.0/24	192.168.50.1	255.255.255.0
60	192.168.60.0/24	192.168.60.1	255.255.255.0


El firewall se encarga del enrutamiento inter-VLAN y de aplicar las políticas de seguridad.

3.4 Componentes principales de la arquitectura
Firewall perimetral
Filtrado de tráfico entrante y saliente.

NAT y port forwarding.

VPN corporativa.

Control de acceso entre VLANs.

Switch gestionable
Creación y gestión de VLANs.

Trunking hacia el firewall.

QoS para priorizar tráfico crítico.

Servidor Windows Server
AD DS: gestión de usuarios y grupos.

DNS/DHCP: servicios de red centralizados.

Servidor de archivos con permisos basados en departamentos.

GPOs para aplicar políticas de seguridad.

Servidor Linux
IDS/IPS (Suricata).

Monitorización (Wazuh / Zabbix / Prometheus).

Intranet corporativa.

Scripts de automatización.

Sistema de copias de seguridad
Backups incrementales diarios.

Copias completas semanales.

Almacenamiento en NAS o servidor dedicado.

3.5 Diagrama lógico de la arquitectura
(Aquí colocarás tu diagrama cuando lo generemos. Si quieres, te lo preparo yo.)

El diagrama mostrará:

Firewall

Switch gestionable

VLANs

Servidores

Estaciones de trabajo

VPN

IDS/IPS

Sistema de backups

3.6 Políticas de acceso entre VLANs
Administración puede acceder a Servidores.

Desarrollo solo accede a su VLAN y a servicios corporativos.

Soporte Técnico tiene acceso controlado a todas las VLANs.

Invitados no tienen acceso a recursos internos.

La VLAN de servidores está aislada excepto para tráfico autorizado.

3.7 Consideraciones de seguridad
Segmentación estricta entre departamentos.

Firewall con reglas específicas por VLAN.

IDS/IPS monitorizando tráfico interno y externo.

Autenticación centralizada mediante AD DS.

Copias de seguridad automatizadas.

VPN con cifrado fuerte.

3.8 Conclusión del diseño
La arquitectura propuesta proporciona una infraestructura segura, escalable y eficiente, alineada con las necesidades de TechMarbella Solutions S.L. y con las buenas prácticas de administración de sistemas. Este diseño servirá como base para la implementación detallada en el capítulo siguiente.
