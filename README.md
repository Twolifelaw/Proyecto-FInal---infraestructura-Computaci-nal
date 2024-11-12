# Proyecto-FInal---infraestructura-Computaci-nal
Bitácora de proyecto final - Infraestructura Computacional

    Proceso para la creación de los RAIDs:

Antes de crear los volúmenes RAID, es necesario disponer de los discos físicos que formarán parte de estos volúmenes. Los discos deben ser de la capacidad adecuada para cumplir con los requerimientos de la infraestructura.

A continuación, se utiliza la terminal para configurar los RAIDs:

a. Creación de los discos necesarios:
 ![alt text](image.png)
 ![alt text](image-1.png)

b. Proceso en la terminal para crear los RAIDS:

1. Primero, se verifica que los dispositivos de almacenamiento estén correctamente reconocidos por el sistema utilizando el siguiente comando:
![alt text](image-2.png)
2. Para crear los volúmenes RAID, se utiliza la herramienta mdadm, que permite crear arreglos RAID de diferentes niveles (en este caso, RAID 1). Este proceso implica la selección de los discos y la creación del RAID.
![alt text](image-3.png)
3. Una vez que los RAIDs han sido creados, es necesario verificar que el sistema haya reconocido correctamente los arreglos y que estos estén funcionando. El comando cat lsblk permite visualizar el estado de los RAIDs.
![alt text](image-5.png)
4. Con los RAIDs creados, el siguiente paso es asignarles un sistema de archivos. Esto se hace utilizando el comando mkfs.ext4 para formatear los volúmenes RAID.
![alt text](image-6.png)




   Proceso para la Creación de los Volúmenes Lógicos (LVM)

a. Una vez que los RAIDs han sido configurados, el siguiente paso es crear un volumen físico (PV) que utilizará LVM. Esto convierte el RAID en un volumen gestionado por LVM.
![alt text](image-7.png)
b. Después de crear el volumen físico, se agrupan uno o más volúmenes físicos en un grupo de volúmenes (VG). Este grupo de volúmenes permite la gestión más flexible de los recursos de almacenamiento.
![alt text](image-8.png)
c. Con el grupo de volúmenes (VG) configurado, se procede a crear los volúmenes lógicos (LV). Estos volúmenes son los que finalmente se usarán para montar los sistemas de archivos.
![alt text](image-9.png)
d. Una vez creados los volúmenes lógicos, es necesario formatearlos para que puedan ser utilizados. El formato más común es ext4, pero dependiendo del caso, se pueden utilizar otros tipos de sistemas de archivos.
![alt text](image-10.png)
e. A continuación, se crean los directorios donde se montarán los volúmenes lógicos. 
![alt text](image-11.png)
f. Luego de crear los directorios, se montan los volúmenes lógicos en dichos directorios. Esto asegura que los datos se almacenen en el volumen lógico correspondiente.
![alt text](image-12.png)
g. Para asegurar que los volúmenes lógicos se monten automáticamente al iniciar el sistema, se debe editar el archivo /etc/fstab y agregar una línea para cada volumen lógico:
![alt text](image-31.png)
h. Una vez configurado todo, los volúmenes lógicos se montan correctamente en sus respectivos directorios al iniciar el sistema, sin necesidad de intervención manual.
![alt text](image-13.png)


    Proceso para la creación de las diferentes imagenes que sera usadas: 

a. Para gestionar las imágenes de los contenedores Docker, se crea un directorio donde se almacenarán los archivos Dockerfile.
![alt text](image-14.png)
b. A continuación, se crean los archivos Dockerfile para los contenedores Apache, MySQL y Nginx. Cada Dockerfile define la configuración y los servicios que se ejecutarán en el contenedor.
![alt text](image-15.png)
c. Podman es una alternativa a Docker y se utiliza para construir las imágenes desde los Dockerfiles creados. Cada uno de los servicios (Apache, MySQL, Nginx) se construye utilizando el siguiente comando:
1. Imagen Docker apache: 
![alt text](image-17.png)
![alt text](image-22.png)
![alt text](image-20.png)
![alt text](image-21.png)
2. Imagen Docker mysql: 
![alt text](image-24.png)
![alt text](image-38.png)
![alt text](image-37.png)

3. Imagen nginx:
![alt text](image-27.png)
![alt text](image-28.png)
![alt text](image-29.png)
![alt text](image-30.png)

d. Resultado de la creacion de las imagenes con podman: 
![alt text](image-33.png)

    Proceso de montaje de las imagenes en los volumenes logicos configurados

a. Primero establecemos los volumenes logicos como almacenamiento para los contenedores y a su vez los corremos
![alt text](image-40.png)
b.Verificamos que este en funcionamiento los contenedores: 
![alt text](image-41.png)
c.Mostrar el uso de los diferentes contenedores y su funcionamiento : 
1. Apache: 
![alt text](image-50.png)
![alt text](image-51.png)
![alt text](image-52.png)

2. nginx:
![alt text](image-46.png)
![alt text](image-47.png)
![alt text](image-49.png)
3. mysql: 
![alt text](image-53.png)
![alt text](image-54.png)






