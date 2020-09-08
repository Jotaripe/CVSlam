# Turtlebot3 - Model Burger integración con ROS y cámara web.
Este proyecto tiene como objetivo dar a conocer en profundidad detalles del proceso de instalación e integración del trabajo fin de máster asociado a la Universidad de Granada llamado: Generación y exploración de entornos desconocidos con Cartographer. Detección de objetos en el entorno.

### Introducción

En primer lugar, se ha integrado Cartographer, un algoritmo de construcción de mapas basado en SLAM sobre un robot móvil con la ayuda de ROS, un sistema operativo orientado a robótica.

En segundo lugar, se utilizaron imágenes tomadas como entrada a una biblioteca de inteligencia artificial que permite realizar diversas tareas, como detectar objetos en el camino del robot, esta tarea es la base para realizar reconocimientos más complejos como la detección de personas en entornos desestructurados como puede ser la exploración para el rescate de personas un espacio tras producirse un terremoto.

De esta forma, se pretende explorar un entorno con un robot utilizando técnicas de reconstrucción del estado del arte como es SLAM, obtenido este entorno utilizar inteligencia artificial para obtener información sobre el mismo, particularizando por ejemplo a un objeto como es un mando de videoconsola.

Se utilizarán dos máquinas, una raspberry pi 3B+ donde se instalará ROS y una máquina más potente como p

### Instalación de ROS 🔧

En esta sección se detallarán los pasos necesarios para mantener, reiniciar o en general poner en funcionamiento el sistema.
* 1.- El sistema operativo elegido para las raspberrys es Raspbian release 9.9 GNU/Linux codename: stretch. Instalado a través de Noobs_V3_1_1.
* 2.- Normalmente se accederá a través de SSH o Escritorio remoto dependiendo del sistema operativo del cliente donde nos encontremos.
* 3.- La librería controladora de la cámara es python-picamera. Instalada con el comando:
```
sudo apt-get install python-picamera
```
Nota: Antes de poner a funcionar la cámara es necesario activar el módulo de la raspberry: Camera. Disponible en: raspi_config
* 4.- El sistema de transferencia de archivos será un servidor ftp, accesible a través de WinSCP en Windows y por línea de comandos y más accesible en Linux.
* 5.- Es de vital importancia apagar las raspberrys por línea de comandos o desde la interfaz, jamás se hará desconectando la alimentación debido a la probable corrupción del sistema. Nota: Para paliar este problema se ha hecho una copia de seguridad con el sistema operativo listo para su uso.

### USO 🔧

Guía sobre como usar el proyecto optovision:

* 1.- Encender cada una de las fuentes de alimentación, esto dará pie a la inicialización automática de cada una de las raspberrys, que inicializarán un servidor ssh, estas raspberrys están enroutadas por un router genérico, en este cao, tp-link, con lo que será necesario conectar las raspberrys por wifi o ethernet al router. Este servidor ssh será accedido a través de una máquina que recoja las imagenes tomadas por las cámaras y almacenadas en cada una de las raspberrys. Con lo que el proceso:
  *  a) Encender fuentes
  *  b) Colocar modelo
  *  c) Tomar una imagen del modelo: [Ver script: "TomarImagenConFecha.py]. [En el futuro, interfaz].
  *  c.2) Nótese que se debe ejecutar este script en cada una de las raspberrys, para ellos se utilizará xterm y cssh para                          *   conectarse a cada una de las raspberrys al mismo tiempo.
  *  d) Transferir imágenes al host anfitrión a través de SCP. [Ver script: "TransferenciaDeImagenes.sh]
  *  e) Cargar las imágenes en Metashape
  *  f) Generar el modelo 3D. Insertar previamente los parámetros intrínsecos de cada cámara en Metashape.
  *  g) Apagar mediante línea de comandos las raspberrys con "sudo shutdown now".
  *  h) Apagar las fuentes del botón preparado para ello, y dejar el sistema listo para un nuevo uso.

* 2.- Interfaz
    [Nota: ESTA INTERFAZ NO ESTÁ DISEÑADA PARA UN USO COMERCIAL]
    - Sirva a modo de visualización de una interfaz profesional:
    - La interfaz está basada en Tkinter que funciona sobre python 3.7+.
    - Sobre ella se ejecutarán los scripts mencionados en esta guía: Apartado USO c) y d)
    - Para ello se debe operar la interfaz en el punto USO b-c de esta misma guía. Aplicar el script de Toma de imagenes
    - Aplicar el script Transferencia de imagenes que guardará la imagenes en la ruta especificada en el script.
    


[EN CONSTRUCCIÓN]

*
*
*


## Autores ✒️

* **Javier Melero Rus** - *Supervisión*
* **Jorge Rivas Pérez** - *Trabajo inicial*

Todos los derechos reservados
