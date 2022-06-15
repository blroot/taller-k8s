# ejercicio04

Para elegir la imágen base se investigó la imágen oficial de [openjdk](https://hub.docker.com/_/openjdk)
Siguiendo la recomendación indicada en el readme de la imágen, finalmente decidí utilizar [amazoncorretto](https://hub.docker.com/_/amazoncorretto)

### Para buildear y taggear la imágen

`docker build -t brunoelottero/passwordapi:1 .`

### Para correr la aplicación

Usando el puerto 8080 local

`docker run -p 8080:8080 brunoelottero/passwordapi:1`




