## 4. Implementación
## 4.1 Preparación del entorno
La infraestructura fue desplegada sobre un equipo físico dotado de un procesador AMD Ryzen 5 7600X y 32 GB de memoria RAM.
El entorno de virtualización se desplegó sobre un SSD dedicado de 480 GB donde se instaló Proxmox VE.
Adicionalmente se utilizó un disco duro secundario de 500 GB destinado al almacenamiento de copias de seguridad, imágenes ISO y evidencias generadas durante el proyecto.
El sistema operativo principal del equipo (Windows 11) se mantuvo instalado en una unidad NVMe independiente de 1 TB, garantizando la separación entre el entorno de trabajo habitual y el laboratorio de virtualización.
## 4.2 Instalación de Proxmox VE
- Descarga de ISO.
- Creación del USB arrancable.
- Instalación.
- Configuración IP inicial.
- Acceso web:



- Conecto con el servidor Proxmox VE a través de mi portátil a través del navegador. Todo esto después de haber descargado la ISO de Proxmox VE
  y la creación de un USB arranca-ble con balenaEtcher programa para crear autoarrancable de proxmox VE, luego instalo, configuro varias pasos e inicio el acceso. 


  https://192.168.1.45:8006/
  <img width="1911" height="1071" alt="imagen" src="https://github.com/user-attachments/assets/8a3595b1-9354-40cd-bbf9-ea09aab6cabc" />
  
  - Me logueo con el usuario y contraseña, muestro como queda el data center de proxmox en su ventana inicial.
  
  <img width="1919" height="1071" alt="imagen" src="https://github.com/user-attachments/assets/e1158024-4a45-43b7-ba99-875af8fa19d6" />

   - En el servidor donde instale Proxmox VE. Muestro los discos enmarcados en rojo con los que voy a trabajar.
  
   <img width="1919" height="1079" alt="imagen" src="https://github.com/user-attachments/assets/e990bf66-493e-43b1-a1ce-e6feaf296050" />

   - Después de instalar proxmox, lo actualizo con apt update
     <img width="1919" height="1073" alt="imagen" src="https://github.com/user-attachments/assets/d5a5a4cc-52c5-4c52-94d2-7a708475a0b0" />
   - Termina la instalación de actualización 
   <img width="1901" height="1075" alt="imagen" src="https://github.com/user-attachments/assets/23cdabba-6938-4341-939b-d40a7b0aad94" />
   
  ## 4.3.1 Configuración del almacenamiento
  
  - Tras la instalación de Proxmox VE se procedió a la configuración del sistema de almacenamiento que dará soporte a las máquinas virtuales y a los recursos necesarios para el desarrollo de la infraestructura.

  - El entorno de virtualización se ha desplegado utilizando dos unidades de almacenamiento independientes:

  - Un SSD de 480 GB destinado a la instalación de Proxmox VE y al almacenamiento principal de las máquinas virtuales.
  - Un disco duro mecánico de 500 GB destinado al almacenamiento secundario para copias de seguridad, imágenes ISO, plantillas y recursos auxiliares.
  -  El sistema operativo principal del equipo, Windows 11, permanece instalado en una unidad NVMe independiente de 1 TB, manteniéndose aislado del entorno de virtualización para evitar interferencias entre ambos sistemas.

 - La configuración del almacenamiento se ha realizado siguiendo una estrategia de separación entre rendimiento y capacidad. El SSD proporciona un acceso rápido a las máquinas virtuales críticas, mientras que el disco duro secundario permite almacenar copias de seguridad y otros recursos sin consumir espacio en la unidad principal.

 - La distribución prevista del almacenamiento es la siguiente:

 - Almacenamiento	Uso principal
 - SSD 480 GB	Proxmox VE, Windows Server, Linux Server, pfSense y GNS3
 - HDD 500 GB	Copias de seguridad, imágenes ISO, plantillas y evidencias del proyecto
 - NVMe 1 TB	Sistema Windows 11 (uso independiente del laboratorio)
 - Esta configuración permite optimizar el rendimiento de la plataforma de virtualización y facilita la gestión de las copias de seguridad y la recuperación ante incidencias.
  
   
  ## 4.3.2 Configuración de red
  - Tras la instalación de Proxmox VE se verificó la configuración de red creada automáticamente durante el proceso de instalación.

  - La plataforma configuró el bridge virtual vmbr0 utilizando la interfaz física principal nic0.

  - La dirección IP asignada al servidor Proxmox fue 192.168.1.45/24, permitiendo el acceso a la interfaz de administración web desde la red local.

  - Este bridge actúa como punto de conexión entre las máquinas virtuales y la red física, permitiendo que los diferentes servicios desplegados dispongan de conectividad y acceso a Internet.
    
  ## 4.4 Implementación del entorno GNS3

  - Con el fin de validar la infraestructura diseñada en fases anteriores, se desplegó una máquina virtual Ubuntu Server sobre Proxmox VE, destinada a ejecutar el servicio GNS3 Server.

  - Esta plataforma permitió construir laboratorios virtuales para verificar la conectividad entre VLANs, las políticas de seguridad implementadas en pfSense y el funcionamiento general de la infraestructura antes de su despliegue definitivo.
  - Descargo Ubuntu Server 24.04.3-live-server-amd64.iso
   <img width="1450" height="204" alt="imagen" src="https://github.com/user-attachments/assets/422d6265-732d-4ce9-b697-c0bd62370247" />
  - Subo la imagen a Proxmox para la posterior creación de la máquina virtual para la implementación de GNS3 Server.
    <img width="1901" height="1079" alt="imagen" src="https://github.com/user-attachments/assets/f9865e16-777e-49a1-990c-9928e0746be5" />
  - Tarea ok, como resultado de la subida de la imagen.
    <img width="1919" height="1074" alt="imagen" src="https://github.com/user-attachments/assets/8a339988-adbc-45c3-a5b4-ede8dc01551a" />
  - Configuro el asistente con los valores necesarios para la máquina virtual.
    <img width="1919" height="1073" alt="imagen" src="https://github.com/user-attachments/assets/93876586-39f8-4bd5-9fc7-5f294eac748e" />
  -Se desplegó una máquina virtual Ubuntu Server 24.04 LTS destinada a alojar GNS3 Server. Durante la instalación se configuró un disco virtual de 40 GB        utilizando almacenamiento SSD gestionado por Proxmox VE, garantizando un rendimiento adecuado para las tareas de simulación de red.

  

    


  



   
   

