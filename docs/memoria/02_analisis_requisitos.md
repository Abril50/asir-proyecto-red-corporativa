### **2. Análisis de requisitos**
El presente capítulo recoge el análisis de necesidades de la empresa TechMarbella Solutions S.L., así como los requisitos funcionales y no funcionales que definirán el diseño de la infraestructura de red corporativa. Este análisis sirve como base para la arquitectura propuesta y para la posterior implementación de los servicios.

**2.1 Necesidades de la empresa**
TechMarbella Solutions S.L. es una empresa tecnológica con tres departamentos principales: Administración, Desarrollo y Soporte Técnico. Debido a su crecimiento y a la necesidad de mejorar la seguridad y eficiencia de sus procesos internos, la organización requiere una infraestructura de red que cumpla los siguientes objetivos:

Garantizar una comunicación interna segura entre empleados y departamentos.

Centralizar la gestión de usuarios, permisos y recursos corporativos.

Implementar una segmentación de red que evite accesos no autorizados entre departamentos.

Disponer de servicios corporativos estables (DNS, DHCP, servidor de archivos, autenticación).

Asegurar la protección perimetral frente a amenazas externas.

Contar con un sistema de monitorización y alertas que permita detectar incidentes.

Establecer un sistema de copias de seguridad fiable y recuperable.

Facilitar el acceso remoto seguro para empleados autorizados mediante VPN.

Estas necesidades se traducen en requisitos técnicos que guiarán el diseño de la solución.

**2.2 Requisitos funcionales**
Los requisitos funcionales definen las capacidades que la infraestructura debe proporcionar:

Directorio Activo (AD DS) para la gestión centralizada de usuarios, grupos y políticas.

Servidor de archivos con permisos basados en departamentos.

Servicios de red: DNS y DHCP centralizados.

Segmentación mediante VLANs para separar Administración, Desarrollo y Soporte Técnico.

Firewall corporativo con reglas de filtrado y NAT.

VPN para acceso remoto seguro.

IDS/IPS para detección y prevención de intrusiones.

Sistema de monitorización (logs, métricas, alertas).

Sistema de copias de seguridad automatizado.

Intranet corporativa para documentación interna y comunicación.

**2.3 Requisitos no funcionales**
Los requisitos no funcionales establecen criterios de calidad y rendimiento:

Disponibilidad: los servicios deben estar operativos la mayor parte del tiempo.

Rendimiento: la red debe soportar el tráfico generado por los departamentos sin saturación.

Escalabilidad: la infraestructura debe permitir añadir nuevos usuarios, servicios o equipos.

Seguridad: cumplimiento de buenas prácticas y políticas internas.

Mantenibilidad: la infraestructura debe ser fácil de administrar y documentar.

Fiabilidad: los datos deben estar protegidos y ser recuperables ante fallos.

**2.4 Restricciones del proyecto**
El proyecto debe desarrollarse teniendo en cuenta las siguientes limitaciones:

Presupuesto limitado, propio de una PYME.

Infraestructura existente, que debe aprovecharse en la medida de lo posible.

Recursos humanos reducidos, con un equipo técnico pequeño.

Tiempo de ejecución acotado, según los plazos del proyecto académico.

Compatibilidad con los sistemas ya utilizados por la empresa.

**2.5 Alcance del proyecto**
El alcance del proyecto incluye:

Incluido
Diseño completo de la arquitectura de red.

Implementación de VLANs y segmentación.

Configuración de firewall, IDS/IPS y VPN.

Despliegue de servicios corporativos (AD DS, DNS, DHCP, servidor de archivos).

Sistema de monitorización y alertas.

Copias de seguridad y recuperación.

Documentación técnica y manuales.

Auditoría informática final.

No incluido
Desarrollo de aplicaciones internas.

Gestión de hardware fuera del ámbito del proyecto.

Servicios cloud avanzados no contemplados en la infraestructura local.

Mantenimiento posterior al despliegue.

**2.6 Conclusión del análisis**
El análisis de requisitos permite establecer una visión clara de las necesidades de TechMarbella Solutions S.L. y define los elementos esenciales que la infraestructura debe cubrir. Este capítulo sirve como base para el diseño técnico que se desarrollará en el capítulo siguiente.
