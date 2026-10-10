## Asir-Proyecto-Red-Corporativa
Proyecto ASIR – Diseño e Implementación de una Infraestructura de Red Corporativa Segura

## 1. Introducción
El presente documento constituye la memoria técnica del proyecto final del módulo 0379 – Administración de Sistemas Informáticos en Red (ASIR).
El objetivo principal es diseñar, implementar y documentar una infraestructura de red corporativa segura, orientada a una empresa ficticia de tamaño medio, siguiendo buenas prácticas de administración de sistemas, seguridad informática y gestión de servicios.

Este proyecto refleja las competencias adquiridas durante el ciclo formativo, incluyendo administración de redes, despliegue de servicios, gestión de identidades, seguridad perimetral, monitorización y documentación técnica.

## 2. Descripción de la empresa
TechMarbella Solutions S.L. es una empresa ficticia dedicada a servicios tecnológicos, con una plantilla de 30 empleados distribuidos en tres departamentos: Administración, Desarrollo y Soporte.
La organización requiere una infraestructura de red segura, segmentada y gestionable, que garantice la disponibilidad, integridad y confidencialidad de sus servicios internos.

## 3. Objetivos del proyecto
Objetivo general
- Diseñar y desplegar una infraestructura de red corporativa que integre servicios esenciales, mecanismos de seguridad y procedimientos de administración, cumpliendo los requisitos funcionales y no funcionales definidos.

Objetivos específicos
- Implementar una red segmentada mediante VLANs.
- Desplegar servicios corporativos: Directorio Activo, DNS, DHCP, servidor de archivos e intranet.
- Configurar una infraestructura de firewall en alta disponibilidad con políticas de filtrado y control de acceso.
- Integrar un sistema IDS/IPS para detección de amenazas.
- Establecer un sistema de monitorización y alertas.
- Implementar una solución de copias de seguridad y recuperación ante desastres.
- Documentar la arquitectura, la configuración y las pruebas realizadas.
- Implementar una plataforma de virtualización basada en Proxmox VE.
- Validar la infraestructura mediante simulación utilizando GNS3.
- Diseñar mecanismos de redundancia y alta disponibilidad para minimizar interrupciones del servicio.

## 4. Alcance del proyecto
El proyecto abarca el diseño lógico y físico de la red, la configuración de los servicios principales, la implementación de medidas de seguridad, la realización de pruebas funcionales y de seguridad, y la elaboración de la documentación técnica correspondiente.
No se incluye la adquisición de hardware específico para producción. La infraestructura será desplegada y validada mediante un entorno virtualizado basado en Proxmox VE y un laboratorio de simulación implementado con GNS3.

## 5. Arquitectura de la solución
La infraestructura propuesta se compone de:
- Dos firewalls pfSense configurados en alta disponibilidad.
- Switch gestionable con segmentación mediante VLANs.
- Plataforma de virtualización basada en Proxmox VE.
- Entorno de simulación y validación mediante GNS3.
- Servidor Windows Server para Active Directory, DNS, DHCP y recursos compartidos.
- Servidor Linux para monitorización, IDS/IPS, automatización e intranet corporativa.
- Sistema IDS/IPS basado en Suricata.
- Plataforma de monitorización y correlación de eventos basada en Wazuh.
- VPN corporativa para acceso remoto seguro.
- Sistema de almacenamiento con redundancia RAID 1.
- Sistema de copias de seguridad y recuperación ante desastres.
- Infraestructura diseñada con mecanismos de redundancia y alta disponibilidad.

## 6. Estructura del repositorio

La siguiente estructura muestra la organización completa del proyecto **asir-proyecto-red-corporativa**, incluyendo la memoria, manuales, diagramas y recursos asociados.

```asir-proyecto-red-corporativa/
├── README.md
├── docs/
│ ├── memoria/
│ │ ├── 00_planificacion.md
│ │ ├── 01_introduccion.md
│ │ ├── 02_analisis_requisitos.md
│ │ ├── 03_diseno_arquitectura.md
│ │ ├── 04_implementacion.md
│ │ ├── 05_seguridad.md
│ │ ├── 06_pruebas.md
│ │ ├── 07_conclusiones.md
│ │ └── 08_anexos.md
│ └── manuales/
│ ├── manual_usuario.md
│ └── manual_administrador.md
├── diagrams/
│ ├── gantt_project.gan
│ ├── gantt_proyecto.png
│ └── cronograma.pdf
├── config/
├── scripts/
├── tests/
└── assets/
```

## 7. Documentación asociada
En la carpeta /docs/memoria se incluye la memoria completa del proyecto, organizada en capítulos:

- Planificación
- Introducción
- Análisis de requisitos
- Diseño de la arquitectura
- Implementación
- Seguridad
- Pruebas
- Conclusiones
- Anexos

Los manuales de usuario y administrador se encuentran en /docs/manuales.

## 8. Estado del proyecto
El proyecto se encuentra en fase de implementación. Las fases de planificación, análisis de requisitos y diseño de arquitectura han sido completadas. La siguiente etapa contempla el despliegue y configuración de los servicios definidos en la infraestructura.
Las configuraciones, diagramas y evidencias se irán incorporando progresivamente conforme avance la implementación.

## 9. Autoría
Proyecto realizado por Diego Manuel Abril Cervera, alumno de IES Aguadulce del ciclo formativo de Administración de Sistemas Informáticos en Red (ASIR).
