# Práctica Jekyll

Jekyll es un generador de sitios web estáticos que nos permite crear de forma sencilla blogs, sitios webs personales o webs para proyectos. Los sitios webs generados con Jekyll no usan una base de datos, el contenido del sitio web está escrito en archivos de texto plano en formato Markdown (o Textile) y plantillas Liquid.

### Creación de un contenedor Docker con Jekyll

Si buscamos la imagen oficial de Jekyll en Docker Hub encontraremos el repositorio oficicial en GitHub.

Existen tres imágenes oficiales con Jekyll:

jekyll/jekyll: Default image.
jekyll/minimal: Very minimal image.
jekyll/builder: Includes tools.
En esta práctica utilizaremos la imagen por defecto jekyll/jekyll.

Para consultar todos los comandos que podemos ejecutar con jekyll podemos ejecutar el siguiente comando:

~~~
docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll
~~~

### jekyll new

Este comando nos permite crear la estructura de directorios y los archivos necesarios de un nuevo proyecto Jekyll.

~~~
docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll new blog
~~~


### jekyll build

Este comando nos permite generar un sitio HTML estático a partir del contenido del proyecto Jekyll.

~~~
docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll build
~~~

 ### jekyll serve

Este comando nos permite servir de forma local un sitio HTML estático generado a partir del contenido del proyecto Jekyll.

~~~
docker run -it --rm -p 4000:4000 -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll serve --force_polling
~~~

La opción --force_polling permite que el contenido del sitio se vaya generando automáticamente cuando existe algún cambio en los archivos del proyecto.

Contenido de nuestro directorio **_posts**:

![Screenshot 2024-03-13 020930](https://github.com/SamuelPadillaS/SamuelPadillaS.github.io/assets/114667075/ce881e7b-c445-4a78-8154-6f5b7be7788c)

En este directorio se guardaran y se publicaran los post que subiremos a nuestra página web estática

Y el archivo que complementa a este sería **images**, que es donde se guardan las imagenes de nuestros posts.

Para ver nuestro sitio web sólo tenemos que abrir un navegador web y acceder a la dirección de localhost en el puerto 4000:

~~~
http://127.0.0.1:4000
~~~

También podríamos acceder a través de la dirección IP de nuestra máquina.
