![Logotipos Fondos Next Generation](../imagenes/Logotipo_ME_FP_GV_FSE.png)
# Docker: Preparación de contenedores mediante comandos.
El objteto de esta lección es aprender como preparar un contenedor personalizado mediante comandos.

## Contenidos:
1. Entorno de desarrollo Python.

## 1. Entorno de desarrollo Python
En primer lugar, aprenderemos como preparar un entorno de desarrollo Python sobre un sistema operativo Linux empleado comandos Docker. Los pasos que debemos seguir son:
1. Descarga de la imagen del sistema operativo Ubuntu.
```bash
$ docker pull ubuntu:latest
```
2. Comprobamos que la imagen del sistema operativo se ha descargado correctamente.
```bash
$ docker images
```
3. Creamos una carpeta *my-python-app* donde almacenaremos los ficheros que deseamos compartir con el contenedor.
```bash
$ mkdir my-python-app
```
4. En el interior de la carpeta *my-python-app* creamos un fichero llamado *requierements.txt* que contendrá las librerias Python que deseamos instalar en el entorno.
```bash
$ cd my-python-app
$ nano requierements.txt
Pylint
Pytest
$ cd ..
```

5. Ejecutamos un contenedor Docker a partir de la imagen de Ubuntu descargada.
```bash
$ docker run -it --name ubuntu-python -v ${PWD}/my-python-app:/app -w /app ubuntu
```
6. Una vez iniciado el terminal interactivo del contenedor, procederemos a instalar Python.
```sh
apt update && apt install -y python3 pip
```
7. Seguidamente instalaremos las librerías del lenguaje.
```sh
/app# 
pip install -r requierements.txt
```


## Vídeos:
- [Ejecutar comandos dentro de un contenedor Docker con `docker run](https://youtu.be/3zxWWRmOdug)


## Referencias:
- [Ejecutar comandos dentro de un contenedor Docker con `docker run`.](https://geekytheory.com/curso-docker-ejecutar-comandos-dentro-contenedor-docker-run/)
