# Turtlebot3 - Model Burger integración con ROS y cámara web.
Este proyecto tiene como objetivo dar a conocer en profundidad detalles del proceso de instalación e integración del trabajo fin de máster asociado a la Universidad de Granada llamado: Generación y exploración de entornos desconocidos con Cartographer. Detección de objetos en el entorno.

### Introducción

En primer lugar, se ha integrado Cartographer, un algoritmo de construcción de mapas basado en SLAM sobre un robot móvil con la ayuda de ROS, un sistema operativo orientado a robótica.

En segundo lugar, se utilizaron imágenes tomadas como entrada a una biblioteca de inteligencia artificial que permite realizar diversas tareas, como detectar objetos en el camino del robot, esta tarea es la base para realizar reconocimientos más complejos como la detección de personas en entornos desestructurados como puede ser la exploración para el rescate de personas un espacio tras producirse un terremoto.

De esta forma, se pretende explorar un entorno con un robot utilizando técnicas de reconstrucción del estado del arte como es SLAM, obtenido este entorno utilizar inteligencia artificial para obtener información sobre el mismo, particularizando por ejemplo a un objeto como es un mando de videoconsola.

Se utilizarán dos máquinas, una raspberry pi 3B+ donde se instalará ROS y una máquina más potente como p

### Instalación de ROS 🔧
* 1.- Raspberry pi 3B+: https://emanual.robotis.com/docs/en/platform/turtlebot3/setup/#sbc-setup
* 2.- Máquina remoto: https://emanual.robotis.com/docs/en/platform/turtlebot3/pc_setup/
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

* 5.- Teleoperar el robot con:
[Android] : https://emanual.robotis.com/docs/en/platform/turtlebot3/teleoperation/#android-app

[Teclado máquina remoto]
```
export TURTLEBOT3_MODEL=${TB3_MODEL}
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
[Autónomo]
```
roslaunch turtlebot3_teleop turtlebot3_drive.launch
```


## Autores ✒️

* **Jorge Rivas Pérez** - *Trabajo inicial*
