# asir-proyecto-red-corporativa
Proyecto ASIR – Diseño e Implementación de una Infraestructura de Red Corporativa Segura
1. Introducción
El presente documento constituye la memoria técnica del proyecto final del módulo 0379 – Administración de Sistemas Informáticos en Red (ASIR).
El objetivo principal es diseñar, implementar y documentar una infraestructura de red corporativa segura, orientada a una empresa ficticia de tamaño medio, siguiendo buenas prácticas de administración de sistemas, seguridad informática y gestión de servicios.

Este proyecto refleja las competencias adquiridas durante el ciclo formativo, incluyendo administración de redes, despliegue de servicios, gestión de identidades, seguridad perimetral, monitorización y documentación técnica.

2. Descripción de la empresa
TechMarbella Solutions S.L. es una empresa ficticia dedicada a servicios tecnológicos, con una plantilla de 30 empleados distribuidos en tres departamentos: Administración, Desarrollo y Soporte.
La organización requiere una infraestructura de red segura, segmentada y gestionable, que garantice la disponibilidad, integridad y confidencialidad de sus servicios internos.

3. Objetivos del proyecto
Objetivo general
Diseñar y desplegar una infraestructura de red corporativa que integre servicios esenciales, mecanismos de seguridad y procedimientos de administración, cumpliendo los requisitos funcionales y no funcionales definidos.

Objetivos específicos
Implementar una red segmentada mediante VLANs.

Desplegar servicios corporativos: Directorio Activo, DNS, DHCP, servidor de archivos e intranet.

Configurar un firewall perimetral con políticas de filtrado.

Integrar un sistema IDS/IPS para detección de amenazas.

Establecer un sistema de monitorización y alertas.

Implementar una solución de copias de seguridad y recuperación ante desastres.

Documentar la arquitectura, la configuración y las pruebas realizadas.

4. Alcance del proyecto
El proyecto abarca el diseño lógico y físico de la red, la configuración de los servicios principales, la implementación de medidas de seguridad, la realización de pruebas funcionales y de seguridad, y la elaboración de la documentación técnica correspondiente.

No se incluye la adquisición de hardware real, ya que la infraestructura se simula mediante entornos virtualizados.

5. Arquitectura de la solución
La infraestructura propuesta se compone de:

Firewall corporativo (pfSense/MikroTik)

Switches gestionables con segmentación por VLAN

Servidor Windows Server para AD DS, DNS, DHCP y recursos compartidos

Servidor Linux para servicios web internos y monitorización

Sistema IDS/IPS basado en Suricata

Plataforma de análisis y correlación de eventos (Wazuh)

VPN corporativa para acceso remoto seguro

Sistema de copias de seguridad con pruebas de restauración

Los diagramas de red y topología se encuentran en la carpeta /diagrams.

6. Estructura del repositorio
Código
asir-proyecto-red-corporativa/
├── README.md
├── docs/
│   ├── memoria/
│   └── manuales/
├── diagrams/
├── config/
├── scripts/
├── tests/
└── assets/
7. Documentación asociada
En la carpeta /docs/memoria se incluye la memoria completa del proyecto, organizada en capítulos:

Introducción

Análisis de requisitos

Diseño de la arquitectura

Implementación

Seguridad

Pruebas

Conclusiones

Anexos

Los manuales de usuario y administrador se encuentran en /docs/manuales.

8. Estado del proyecto
El proyecto se encuentra en fase de desarrollo y documentación.
Las configuraciones, diagramas y evidencias se irán incorporando progresivamente conforme avance la implementación.

9. Autoría
Proyecto realizado por Diego, alumno del ciclo formativo de Administración de Sistemas Informáticos en Red (ASIR).
