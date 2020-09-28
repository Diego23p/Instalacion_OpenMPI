# Instalacion de OpenMPI (Ubuntu)

1. Descargar la última versión estable de [Open MPI](https://www.open-mpi.org/)

Comandos desde consola: 

2. Descomprimir el archivo: ```tar -xzf <Nombre del archivo comprimido>```
3. Entrar a la carpeta descomprimida: ```cd  <Nombre del la carpeta>```
4. Hacer una carpeta para la construcción: ```mkdir build```
5. Ingresar a dicha carpeta: ```cd build```
6. Configuración de Open MPI: ```../configure --prefix=/usr/local``` (Establecerá una variable en la ```Makefile``` que está disponible al momento de compilar el programa).

- Si tiene el error ```configure: error: no acceptable C compiler found in $PATH``` es porque la librería gcc no está instalada, puede agregarla con:```sudo apt-get update``` y ```sudo apt install build-essential ``` y ejecutar el comando nuevamente.

7. Descargar la última versión de las herramientas de desarrollo y sus dependencias: ```make all```
8. Construir el software en este lugar: ```sudo make install```

# Compilación y Ejecución:

Dentro de la carperta descomprimida, se encuentra otra llamada ```examples``` que nos brinda un Hello World para compilar y ejecutar.

Se hará uso de comando ```mpicc codigo_fuente.c -o ejecutable``` para compilar un programa con MPI en C. Estando en la consola dentro de ```examples```:

9. Compilar: ```mpicc hello_c.c -o hello_c```
 
Ejecutar el programa paralelo con 2 procesos:

10. Ejecutar: ```mpirun -np 2 hello_c```

![](/img/1.jpg)