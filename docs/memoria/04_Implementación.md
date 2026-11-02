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
  Conecto con el servidor Proxmox VE a través de mi portátil a través del navegador.

  https://192.168.1.45:8006/
  <img width="1911" height="1071" alt="imagen" src="https://github.com/user-attachments/assets/8a3595b1-9354-40cd-bbf9-ea09aab6cabc" />

   Me logueo con el usuario y contraseña, en el servidor donde instale Proxmox VE. Muestro los discos enmarcados en rojo con los que voy a trabajar.
  
   <img width="1919" height="1079" alt="imagen" src="https://github.com/user-attachments/assets/e990bf66-493e-43b1-a1ce-e6feaf296050" />


