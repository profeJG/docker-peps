![Logotipos Fondos Next Generation](../imagenes/Logotipo_ME_FP_GV_FSE.png)
# Construcción de imagenes: `docker build` y  *Dockerfile*.
## Contenidos:

Docker Build y Dockerfile son dos componentes clave en el proceso de construcción de imágenes de contenedores personalizadas en Docker. A continuación, se explica el funcionamiento de cada uno:

1. Docker Build: Docker Build es el comando utilizado para construir una imagen de contenedor a partir de un Dockerfile y otros recursos necesarios. Este comando toma como entrada un contexto de construcción, que es un directorio local que contiene el Dockerfile y cualquier otro archivo requerido por la aplicación. Docker Build ejecuta las instrucciones definidas en el Dockerfile y crea una nueva imagen de contenedor basada en esas instrucciones.

El comando Docker Build realiza los siguientes pasos:

- Lee el Dockerfile y las instrucciones que contiene.
- Crea una imagen base inicializada a partir de una imagen existente o una imagen base predeterminada.
- Ejecuta cada instrucción del Dockerfile en orden, construyendo capas adicionales en la imagen base.
- Cada instrucción puede agregar, eliminar o modificar archivos o configuraciones en la imagen.
- Cada instrucción genera una nueva capa en la imagen, lo que permite el reutilización y la eficiencia en las construcciones posteriores.
- Al finalizar la construcción, se genera una imagen de contenedor lista para ser utilizada.

2. Dockerfile: El Dockerfile es un archivo de texto plano que contiene una serie de instrucciones y comandos utilizados por Docker Build para construir una imagen de contenedor. El Dockerfile define los pasos necesarios para configurar el entorno de ejecución de la aplicación dentro del contenedor.

El Dockerfile incluye instrucciones como:

- FROM: especifica la imagen base a partir de la cual se construirá la imagen del contenedor.
- RUN: ejecuta comandos en el entorno del contenedor durante el proceso de construcción.
- COPY: copia archivos y directorios desde el contexto de construcción al contenedor.
- WORKDIR: establece el directorio de trabajo dentro del contenedor.
- EXPOSE: especifica los puertos en los que la aplicación dentro del contenedor escucha conexiones.
- CMD: define el comando predeterminado que se ejecutará cuando se inicie el contenedor.

El Dockerfile permite definir de manera reproducible y automatizada la configuración y los pasos necesarios para construir una imagen de contenedor. Se puede utilizar para personalizar y ajustar la configuración del contenedor según las necesidades específicas de la aplicación.

En resumen, Docker Build es el comando que ejecuta las instrucciones definidas en un Dockerfile para construir una imagen de contenedor. El Dockerfile es el archivo de configuración que contiene las instrucciones y comandos necesarios para construir la imagen. Juntos, Docker Build y Dockerfile permiten construir imágenes de contenedores personalizadas y reproducibles de manera eficiente.
## Referencias
