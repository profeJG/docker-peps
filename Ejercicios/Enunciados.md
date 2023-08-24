# Enunciados de ejercicios Docker
## Servicios en red
1. Ejecutar de forma manual un servidor web estático:**seqvence/static-site**.
```bash
docker run --name static-site \
 -e AUTHOR="Your Name" -d \
 -p 9000:80 seqvence/static-site
```
2. Averigue los contenedores que se encuentran en ejecución.
```bash
docker ps
```
3. Obtener la salida estándar del contenedor *static-site*.
```bash
docker logs static-site
```
4. Abre la URL http://127.0.0.1:9000 en un navegador y accede al puerto 80 de la aplicación en el contenedor.
5. Parar el contenedor *static-site*.
```bash
docker stop static-site
```
6. Parar y borrar todos los contenedores.
```bash
docker rm -f $(ps -a -q)
```
7. Arranque un contenedor MySQL llamado **miBD**, que disponga de las siguientes variables de entorno configuradas: *MYSQL_ROOT_PASSWORD, MYSQL_DATABASE,MYSQL_USER, MYSQL_PASSWORD=micontrasea*
```bash
docker run --name miBD -d \
-e MYSQL_ROOT_PASSWORD=12345678Aa \
-e MYSQL_DATABASE=db_my \
-e MYSQL_USER=myuser \
-e MYSQL_PASSWORD=micontrasea \
mysql
```
8. Conecte con la base de datos MySQL dockerizada.
```bash
docker exec -it miBD mysql -h 172.17.0.2 -P 3306 -u root -p
```
9.  Ejecutar un servidor web con **[Drupal](https://www.drupal.org/home)** dockerizada.
```bash
docker run -d -p 8081:80 drupal
```
10. Acceda al servidor web ejercutado a través de un navegador y proceda a su configuración.
11. Ejecuta un servidor web **NGINX** que haga uso de volumenes para almacenar las páginas HTML.
```bash
docker run -d -p 9000:80 -v "$PWD":/usr/share/nginx/html nginx
```
12. **Jekyll** es una herramienta que genera un sitio web partiendo de ficheros de texto (**Markdown**). Ejecuta Jekyll desde un contenedor sin tener que instalarlo en el host.
  ```bash
  # Descarga el contenido de ejemplo desde GitHub.
  git clone https://github.com/henrythemes/jekyll-minimal-theme
  cd jekyll-minimal-theme 
  
  # Ejecuta el contenedor para generar el sitio web en la carpeta descargada.
  docker run --rm  -v "$PWD":/src grahamc/jekyll build
  ```
      
1.  ii
2.  
3.  oooo
4.  ooo

  

