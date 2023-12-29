![Logotipos Fondos Next Generation](../imagenes/Logotipo_ME_FP_GV_FSE.png)
# Docker para la puesta en producción segura
Uso práctico de Docker para el módulo Puesta en Producción Segura del Curso de Especialización en Ciberseguridad.

## Contenidos:
1. Docker en producción.
2. Entorno de desarrollo Node.js

## 1. Docker en producción
Para utilizar Docker en entornos de producción, se recomienda seguir las mejores prácticas para garantizar la seguridad y la eficiencia del sistema. Docker Compose es una herramienta útil para definir y ejecutar aplicaciones Docker en diferentes entornos, como **CI**, *staging* y **producción**.

Para preparar una aplicación Docker para producción, es necesario realizar algunos cambios en la configuración de la aplicación. Algunos de estos cambios incluyen:

- Eliminar cualquier enlace de volumen para el código de la aplicación, para que el código permanezca dentro del contenedor y no se pueda cambiar desde el exterior
- Enlazar a diferentes puertos en el host.
- Especificar variables de entorno de manera diferente, como reducir la verbosidad del registro o especificar configuraciones para servicios externos como un servidor de correo electrónico.
- Especificar una política de reinicio como `restart: always` para evitar el tiempo de inactividad.
- Agregar servicios adicionales como un agregador de registros.

Para hacer estos cambios, se puede definir un archivo adicional de Compose, por ejemplo **production.yml**, que especifique la configuración adecuada para producción. Este archivo de configuración solo necesita incluir los cambios que se desean hacer en el archivo *Compose* original. El archivo adicional de **Compose** se aplica sobre el archivo `compose.yml` original para crear una nueva configuración.

Una vez que se tiene un segundo archivo de configuración, se puede usar con la opción -f:
```sh
docker compose -f compose.yml -f production.yml up -d
```
## 2. Entorno de desarrollo Node.js
### Preparación del entorno testing con Node.js mediante comandos docker
En primer lugar, aprenderemos como preparar un entorno de desarrollo Node.js sobre un sistema operativo Linux empleado comandos Docker. Los pasos que debemos seguir son:
1. Descarga de la imagen del entorno Nodejs.
```bash
docker pull node:latest
```
2. Comprobamos que la imagen del sistema operativo se ha descargado correctamente.
```bash
docker images
```
3. Ejecutamos un contenedor Docker a partir de la imagen de Nodejs descargada.
```bash
docker run -it --entrypoint bash --name jg-my-javascript-app -p 8080:8080 -v ${PWD}/my-javascript-app:/app -w /app node:latest
```
4. Dentro del contenedor `/app#` ejecutamos **mocha** `mpm test`. En caso de que *mocha* no esté instalado lo instalamos previamente `npm install mocha`.
5. Lanzamos el servidor **Exrpress** dentro del contenedor **Node**. En el contenedor `/app#` ejecutamos `node src/index.js`, si todo ha ido bien debemos obtener la respuesta *"Servidor escuchando en el puerto 8080"*

## Vídeos:

- [Cómo crear nuestra primera pagina web con NodeJS, Express, Docker y Publicarla en Digitalocean.](https://youtu.be/USivUGPSZ9s)

## Referencias:
- [Set up a dev enviroment.](https://docs.docker.com/desktop/dev-environments/set-up/)
- [Use compose in production.](https://docs.docker.com/compose/production/)
- [Docker: Buenas prácticas en entornos de producción.](https://santimacnet.wordpress.com/2017/10/22/docker-buenas-practicas-en-entornos-de-produccion/)