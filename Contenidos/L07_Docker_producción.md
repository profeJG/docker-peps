![Logotipos Fondos Next Generation](../imagenes/Logotipo_ME_FP_GV_FSE.png)
# Docker para la puesta en producción segura
Uso práctico de Docker para el módulo Puesta en Producción Segura del Curso de Especialización en Ciberseguridad.

## Contenidos:
1. Introducción a Docker.
2. Arquitecturas de microservicios.
3. Construcción de imagenes: `docker build` y  *Dockerfile*.
4. Desarrollo de contenedores: `docker-compose`.
5. Integración continua.
6. Docker en producción.

## Docker en producción
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

## Referencias:
- [Set up a dev enviroment.](https://docs.docker.com/desktop/dev-environments/set-up/)
- [Use compose in production.](https://docs.docker.com/compose/production/)
- [Docker: Buenas prácticas en entornos de producción.](https://santimacnet.wordpress.com/2017/10/22/docker-buenas-practicas-en-entornos-de-produccion/)