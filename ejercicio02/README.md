# ejercicio02

### Se hace pull de la imágen desde el repositorio nicopaez
`docker pull nicopaez/pingapp:3.0.0`

### Se hace login a dockerhub (en mi caso ya tenía credenciales existentes)
`docker login`

### En este caso elegí ponerle el mismo tag para el repositorio destino y se puede observar en la lista de imágenes local la nueva imágen
`docker tag nicopaez/pingapp:3.0.0 brunoelottero/pingapp:3.0.0`
`docker image ls`

```
docker image ls
REPOSITORY              TAG                 IMAGE ID            CREATED             SIZE
alpine                  latest              e66264b98777        2 weeks ago         5.53MB
hello-world             latest              feb5d9fea6a5        8 months ago        13.3kB
brunoelottero/pingapp   3.0.0               5021b0410677        15 months ago       883MB
nicopaez/pingapp        3.0.0               5021b0410677        15 months ago       883MB
nicopaez/holanico       2.0.0               e6f79d94eddb        15 months ago       5.05MB
nicopaez/pingapp        latest              b30ba4516116        3 years ago         783MB
```

# Finalmente se hace el push de la imágen a mi repositorio
`docker push brunoelottero/pingapp:3.0.0`

# Se puede hacer pull de la imágen con este comando
`docker pull brunoelottero/pingapp:3.0.0`
