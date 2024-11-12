# Proyecto-FInal---infraestructura-Computaci-nal
Bitácora de proyecto final - Infraestructura Computacional

    Proceso para la creación de los RAIDs:

a. Creación de los discos necesarios:
 ![alt text](image.png)
 ![alt text](image-1.png)

b. Proceso en la terminal para crear los RAIDS:
1. Ver los diferentes dispositivos de almacenamiento del sistema:
![alt text](image-2.png)
2. Proceso para la creacion de los RAIDS:
![alt text](image-3.png)
3. Resultado: 
![alt text](image-5.png)
4. Procedemos a proporcionar el sistema de archivo a los diferentes RAIDS: 
![alt text](image-6.png)




    Proceso para la creación de los Volúmenes Lógicos:

a. Crear un volumen físico (PV) para RAID
![alt text](image-7.png)
b. Crear un grupo de volúmenes (VG)
![alt text](image-8.png)
c. Crear volúmenes lógicos (LV)
![alt text](image-9.png)
d. Formatear los volúmenes lógicos (ext4) para poder dar uso de estos: 
![alt text](image-10.png)
e. Procedemos a crear los directorios en los cuales se montaran los volumenes logicos:
![alt text](image-11.png)
f. Se monta los diferentes volumenes logicos en los directorios /mnt creados : 
![alt text](image-12.png)
g. Resultado obtenido: 
![alt text](image-13.png)


    Proceso para la creación de las diferentes imagenes que sera usadas: 

a. Creacionde del directorio Donde se almacenaran los diferentes Dockerfiles
![alt text](image-14.png)
b. Procedemos a crear los Dockerfile para sus respectivas imagenes:
![alt text](image-15.png)
c. Crearemos la imagen necesarias para cada uno de los servicios (apache,mysql y nginx):
1. Imagen apache: 
![alt text](image-17.png)
![alt text](image-18.png)
![alt text](image-19.png)










