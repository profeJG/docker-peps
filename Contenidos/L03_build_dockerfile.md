![Logotipos Fondos Next Generation](../imagenes/Logotipo_ME_FP_GV_FSE.png)
# Construcción de imagenes: `docker build` y  *Dockerfile*.
## Contenidos:
1. Docker build.
2. Dockerfile.


Docker Build y Dockerfile son dos componentes clave en el proceso de construcción de imágenes de contenedores personalizadas en Docker. A continuación, se explica el funcionamiento de cada uno:

## 1. Docker build
**Docker Build** es el comando utilizado para construir una imagen de contenedor a partir de un Dockerfile y otros recursos necesarios. Este comando toma como entrada un contexto de construcción, que es un directorio local que contiene el Dockerfile y cualquier otro archivo requerido por la aplicación. Docker Build ejecuta las instrucciones definidas en el Dockerfile y crea una nueva imagen de contenedor basada en esas instrucciones.

El comando `docker build` realiza los siguientes pasos:

- Lee el Dockerfile y las instrucciones que contiene.
- Crea una imagen base inicializada a partir de una imagen existente o una imagen base predeterminada.
- Ejecuta cada instrucción del Dockerfile en orden, construyendo capas adicionales en la imagen base.
- Cada instrucción puede agregar, eliminar o modificar archivos o configuraciones en la imagen.
- Cada instrucción genera una nueva capa en la imagen, lo que permite el reutilización y la eficiencia en las construcciones posteriores.
- Al finalizar la construcción, se genera una imagen de contenedor lista para ser utilizada.

## 2. Dockerfile: 
El Dockerfile es un archivo de texto plano que contiene una serie de instrucciones y comandos utilizados por Docker Build para construir una imagen de contenedor. El Dockerfile define los pasos necesarios para configurar el entorno de ejecución de la aplicación dentro del contenedor.

El Dockerfile incluye instrucciones como:

- **FROM:** especifica la imagen base a partir de la cual se construirá la imagen del contenedor.
- **RUN:** ejecuta comandos en el entorno del contenedor durante el proceso de construcción.
- **COPY:** copia archivos y directorios desde el contexto de construcción al contenedor.
- **WORKDIR:** establece el directorio de trabajo dentro del contenedor.
- **EXPOSE:** especifica los puertos en los que la aplicación dentro del contenedor escucha conexiones.
- **CMD:** define el comando predeterminado que se ejecutará cuando se inicie el contenedor.

El Dockerfile permite definir de manera reproducible y automatizada la configuración y los pasos necesarios para construir una imagen de contenedor. Se puede utilizar para personalizar y ajustar la configuración del contenedor según las necesidades específicas de la aplicación.

### Ejemplo de *Dockerfile*
```dockerfile
FROM ubuntu:latest # Imagen básica del SO Linux del contenedor

# Ejecuta comandos de instalación en el contenedor
RUN apt-get update -y
RUN apt-get install -y python-pip python-dev build-essential

WORKDIR /app
COPY . /app
RUN pip install -r requirements.txt
ENTRYPOINT ["python"]
CMD ["app.py"]
```

En resumen, Docker Build es el comando que ejecuta las instrucciones definidas en un Dockerfile para construir una imagen de contenedor. El Dockerfile es el archivo de configuración que contiene las instrucciones y comandos necesarios para construir la imagen. Juntos, Docker Build y Dockerfile permiten construir imágenes de contenedores personalizadas y reproducibles de manera eficiente.


## Flask
Flask es un framework web ligero y flexible escrito en Python. Es utilizado para construir aplicaciones web rápidas y eficientes. Flask se basa en el concepto de "microframework", lo que significa que proporciona solo las funcionalidades básicas necesarias para construir aplicaciones web, pero es altamente extensible y permite agregar funcionalidades adicionales según sea necesario.
![Logotipo Flask](https://files.virgool.io/upload/users/176/posts/hfjdahdqvyl9/wylydhixkqcz.png)

Algunas características destacadas de Flask son:

1. Enfoque minimalista: Flask se enfoca en la simplicidad y la legibilidad del código. Proporciona solo las funcionalidades esenciales para el desarrollo web, lo que hace que el código sea más limpio y fácil de entender.

2. Routing: Flask permite definir rutas y asociar funciones a esas rutas para manejar las solicitudes HTTP entrantes. Esto facilita la creación de diferentes rutas para diferentes páginas o funcionalidades de una aplicación.

3. Templates: Flask incluye un motor de plantillas que permite separar la lógica de presentación del código de la aplicación. Los templates permiten generar contenido HTML dinámico e interactivo.

4. Integración con bases de datos: Flask proporciona una capa de abstracción para interactuar con bases de datos. Puede trabajar con diferentes bases de datos, como SQLite, MySQL, PostgreSQL, etc., utilizando extensiones o librerías adicionales.

5. Extensibilidad: Flask es altamente extensible y permite agregar funcionalidades adicionales mediante el uso de extensiones. Existen numerosas extensiones disponibles para agregar autenticación, manejo de formularios, manejo de sesiones, API REST, entre otros.

6. Compatibilidad con Python: Flask está escrito en Python y se integra perfectamente con el ecosistema de Python. Esto significa que se puede aprovechar la amplia variedad de librerías y herramientas disponibles en Python para complementar el desarrollo de aplicaciones web con Flask.

En resumen, Flask es un framework web minimalista y flexible escrito en Python. Proporciona las funcionalidades básicas necesarias para el desarrollo web y se puede extender según las necesidades del proyecto. Flask es ampliamente utilizado en la comunidad de desarrollo web de Python debido a su simplicidad y facilidad de uso.
## Referencias
- [Flask](https://flask.palletsprojects.com/en/2.3.x/)
- [Wikipedia: Flask](https://es.wikipedia.org/wiki/Flask)
- [Documentación de Dockerfile](https://docs.docker.com/engine/reference/builder/)