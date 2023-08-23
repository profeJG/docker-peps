![Logotipos Fondos Next Generation](../imagenes/Logotipo_ME_FP_GV_FSE.png)
# Despliegue de aplicaciones con `docker-compose`

## Contenidos:
1. ¿Qué es Docker-Compose?.
2. Arquitecturas de microservicios con `compose.yml`.
3. Construcción de imagenes: `docker build` y  *Dockerfile*.
4. Desarrollo de contenedores: `docker-compose`.
5. Integración continua.
6. Docker en producción.

## 1. ¿Qué es Docker-Compose?
**Docker Compose** es una herramienta que permite definir y administrar aplicaciones multi-contenedor. Permite describir la configuración de una aplicación utilizando un archivo YAML y luego utilizar ese archivo para crear y administrar los contenedores de la aplicación de manera fácil y reproducible.
Docker Compose surge porque muchas aplicaciones requieren de más de un microservicio. Pero claro, **la idea de Docker es que únicamente ejecute un único microservicio por contenedor** y no varios a la vez.

Por tanto,  en esta situación podemos hacer dos cosas:
1. **Ejecutar dos microservicios en un mismo Docker.** Lo bueno en esta situación es que no necesitamos aprender nada para ello, simplemente con Docker podríamos lograrlo. Sin embargo, esto es muy delicado, ya que, si uno de los dos servicios fallase, fallarían todos los servicios. Además, sería poco escalable, ya que se compartirían todos los recursos y se tendría que escalar todo a la vez, lo cual no tiene mucho sentido. Lo lógico sería que si, por ejemplo, una API que tenemos en Docker recibe muchas peticiones, escalemos solo esa API, y no todo lo demás.
2. **Utilizar Docker Compose:** con Docker Compose puedes crear varios contenedores y definir cómo quieres que se relacionen y cómo quieres que gestionen los datos que generan. De esta forma, si uno de los contenedores fallase, podrías (depende cómo lo configures) permitir que los otros servicios sigan funcionando.
![Logotipo Pulpo de Docker Compose](../imagenes/L04_docker-compose-logo.png)
Con Docker Compose, se pueden definir los servicios, redes y volúmenes de una aplicación en un solo archivo, lo que facilita la configuración y el despliegue de la aplicación en diferentes entornos. Además, Docker Compose proporciona comandos para administrar los contenedores, como iniciar, detener y eliminar los servicios.

## 2. Arquitectura de microservicios con `compose.yml`.
### ¿Qué es un fichero con extensión YAML?  
**YAML** es un acrónimo que significa *Ain’t Markup Languaje (YAML no es un leguaje de marcas)*. Se trata de un estándar de serialización de datos amigable para todos los lenguajes de programación. Más información en [yaml.org](yaml.org)

Con **Compose** utilizaremos ficheros en formato **YAML**, que nos servirán para definir la configuración de la aplicación en cuestión. De esta manera podemos, con un solo comando, crear e iniciar los servicios configurados en estos ficheros.

## Referencias:
- [Fernández, A.: Tutorial Docker Compose.](https://anderfernandez.com/blog/tutorial-docker-compose/)
- [YAML: *YAML Ain't Markup Language*.](yaml.org)