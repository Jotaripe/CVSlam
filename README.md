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

Guía sobre como usar el proyecto :

* 1.- Instalar ROS en la raspberry pi 3B+
* 2.- Instalar ROS en la máquina remoto
* 3.- Instalar paquetes y sus dependencias: uvc_camera [Raspberry], find_object_2d[Máquina remoto], Cartographer-ROS[Máquina remoto]
* 4.- Iniciar ROS en raspberry y maquian remoto con:
```
roscore
```
* 4.- Iniciar los diferentes nodos con:
[Raspberry]
```
rosrun uvc_camera uvc_camera_node
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
[Máquina remoto]
```
rosrun find_object find_object_2d image:=image_raw
roslaunch turtlebot3_slam turtlebot3.launch slam_methods:=karto

```

[EN CONSTRUCCIÓN]

*
*
*


## Autores ✒️

* **Jorge Rivas Pérez** - *Trabajo inicial*
