# Ejercicio01

## Para ejecutar el ejercicio se debe

Correr el comando

```docker run --name simple-nginx -v <path_to_repo>/ejercicio01/:/usr/share/nginx/html:ro -d -p 8080:80 nginx```

y acceder por un navegador a [http://localhost:8080](http://localhost:8080)

## Breve explicación de las opciones usadas

* `--name simple-nginx` -> Asigna un nombre al conenedor
* `-v` -> Monta un directorio desde el sistema de archivos local a un directorio en el contenedor
* `-d` -> Para que el proceso quede corriendo en background
* `-p 8080:80` -> Mapea el puerto 80 del conenedor al 8080 del host local
