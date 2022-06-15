# ejercicio04

Para elegir la imágen base se investigó la imágen oficial de [openjdk](https://hub.docker.com/_/openjdk)
Siguiendo la recomendación indicada en el readme de la imágen, finalmente decidí utilizar [amazoncorretto](https://hub.docker.com/_/amazoncorretto)
También se probó [eclipse-temurin](https://hub.docker.com/_/eclipse-temurin) obteniendo errores de memoria al arrancar.

### Para buildear y taggear la imágen

`docker build -t brunoelottero/passwordapi:1 .`

### Para correr la aplicación

Para exponerla en el puerto 8080 local

`docker run -p 8080:8080 brunoelottero/passwordapi:1`

### Por último se sube la imágen a dockerhub

`docker push brunoelottero/passwordapi:1`

[link al repo](https://hub.docker.com/repository/docker/brunoelottero/passwordapi)


