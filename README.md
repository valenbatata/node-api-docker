Ejercicio 1 


    ¿Qué hace git clone y dónde sitúa el control de versiones?
        El git clone, clona el repositorio de github y lo sitúa en la carpeta qué nosotros queramos.


    ¿Qué es un Dockerfile y por qué Docker cachea capas?
        Un Dockerfile es un archivo de texto que contiene una serie de instrucciones para construir una imagen Docker. 

        Docker cachea en capas para acelerar la construcción de imágenes.

    Diferencia entre git add y git commit.
        “Git add .”  añade todas las actualizaciones / cambios del directorio al proyecto, así deja todo preparado para el siguiente commit.

        El “Git commit” es el comando que utilizamos para mandar todos los cambios realizados al repositorio en github, le podemos agregar un -m para mandarlo con mensajes y tener un mejor recuento de los cambios que vamos haciendo. 



Ejercicio 2: Modificación y versionado (Semi-autónomo)


    ¿Qué es un PR y cómo facilita la colaboración?
        En GitHub, un Pull Request (PR) o Solicitud de Incorporación de Cambios es una forma de proponer cambios a un repositorio.
        Es una solicitud para que los colaboradores revisen, discutan y eventualmente fusionen tus cambios con la rama principal (main o master) del proyecto.

Ejercicio 4: 

    Explicar los comandos vistos en el PDF

        git clone https://github.com/brandoncaulfield/node-api-docker.git

            Este comando clona el repositorio de github en nuestro visual studio para poder trabajar con todos los archivos.

        git clone https://github.com/brandoncaulfield/node-api-docker.git cd node-api-docker

            Este es para (por si no lo hiciste antes) clonarlo pero además posicionarse en la carpeta del principal.

        docker build -t clase-api:1.0 .

            Este comando es para crear el contenedor en docker, otorgando el nombre “clase-api:1.0”.

        docker run -d -p 5001:8080 --name tp-api clase-api:1.0

            Este es para correr el contenedor en el puerto 5001.

        curl http://localhost:5001

            Este hace la solicitud HTTPS GET a la URL.

        git checkout -b ejercicio1 
        git add .
        git commit -m "feat: cloné y levanté la API en Docker"

            Estos son todos los comandos necesarios para crear una rama nueva llamada “ejercicio1”, agregar los cambios y envíar el commit con el comentario.

        docker build -t clase-api:2.0 . 

            Creamos otro contenedor docker.

        docker stop tp-api && docker rm tp-api 

            Detenemos y borramos el contenedor creado al principio.

        docker run -d -p 5001:8080 --name tp-api clase-api:2.0

            Arrancamos el contenedor en el puerto 5001.

        curl http://localhost:5001/ping

            Hacemos la solicitud pero especificando que pruebe el espacio /ping.

        git checkout -b ejercicio2 

            Creamos una nueva rama “ejercicio2”.

        git add src/index.js

            Agregamos cambios hechos en el index.

         git commit -m "feat: agregada ruta /ping" 

            Hacemos el commit.

        git push origin ejercicio2

            Mandamos la rama ejercicio2 al repositorio.
