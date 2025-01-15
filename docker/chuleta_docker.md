# Obtener una ayuda

`docker build --help `

# Descargar la imagen base

`docker pull alpine`

## Crear una imagen a partir de una imagen base que se encuentra en el 
## archivo Dockerfile con directiva FROM y IMAGE-NAME es el nombre que 
## se le quiera dar a la imagen

`docker build -f Dockerfile.backup -t IMAGE-NAME .`

# Crear una imagen a partir de un contenedor

`docker commit <CONTAINER_ID> <NOMBRE_DE_LA_IMAGEN>:<ETIQUETA>`

# Borrar imagenes

`docker rmi IMAGE-ID o REPOSITORY`

# Cambiar nombres de la imagen

`docker tag IMAGE-ID nombre-nuevo`

# Instaciacion

## Instanciar una imagen y ejecutarla en background

`docker run -d -p 3000:3000 IMAGE-ID o REPOSITORY-NAME`

`docker run -id --name CONTAINER-NAME IMAGE-NAME sh`

# Instanciar una imagen y ejecutar el shell

`docker run -it -p 3000:3000 IMAGE-ID o REPOSITORY-NAME sh`

# Usar directorios de la maquina anfitrion

`docker run -v /home/neo/mongodb -it -v /home/neo/backend IMAGE-ID bash`

`docker run -id -v ~/directorio/local:/directorio/container IMAGE-ID bash`

# Ingresar en un container y ejecutar un comando. En este caso bash.

`docker exec -it CONTAINER-ID bash`

# Ingresar en un container como root y ejecutar un comando.

`docker exec -it -u root CONTAINER-ID sh`

# Copiar un archivo a un container

`docker cp file.ext CONTAINER-ID:/directorio`

# Ver los containers activos

`docker ps`

# Ver los containers activos e inactivos

`docker ps -a`

# Borrar todas las instancias

`docker rm $(docker ps -aq)`

# Ver los logs del container

`docker logs CONTAINER-ID`

# Reiniciar un container.

`docker start CONTAINER-ID`

# Detener un container.

`docker stop CONTAINER-ID`

# Ejecutando a mano
## Si está definido (--network) no son necesarios los ports

docker run -d --rm --network confusionserver_default \
--network-alias mongonet \
-p 27016:27017 \
-e MONGO_INITDB_ROOT_USERNAME=admin \
-e MONGO_INITDB_ROOT_PASSWORD=password \
mongo:4.2

docker run -d --rm --init --network confusionserver_default \
--network-alias server \
-p 3000:3000 \
-p 3443:3443 \
confusion

docker run -it --init --rm -p 3000:3000 -p 3443:3443 confusion sh
