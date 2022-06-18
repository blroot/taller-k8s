# ejercicio07

### ¿Cuántos contenedores se están ejecutando?

```
CONTAINER ID        IMAGE                            COMMAND                  CREATED             STATUS              PORTS                                NAMES
be536509bb83        nicopaez/jobvacancy-ruby:1.3.0   "/jobvacancy/start_a…"   2 minutes ago       Up 2 minutes        0.0.0.0:3000->3000/tcp               ejercicio07_web_1
8f65ab27a0ce        postgres                         "docker-entrypoint.s…"   2 minutes ago       Up 2 minutes        5432/tcp                             ejercicio07_db_1
```

Se están ejecutando dos contenedores

### ¿Cuales son las imágenes en las que están basados los mencionados contenedores?

* nicopaez/jobvacancy-ruby:1.3.0
* postgres

### ¿Puedes leer el docker-compose-jobvacancy.yml y describir lo que hace cada una de sus lineas?

```
version: '2'   # Indica cual es la versión del schema para el YAML 
services:    # 
  web:    # Es el inicio de la definición del servicio "web"
    image: nicopaez/jobvacancy-ruby:1.3.0    # Imágen a utilizar para levantar el contenedor del servicio
    links:    # Indica que el servicio "db" va a ser accesible desde "web"
      - db
    ports:    # Define el mapeo del puerto 3000 del contenedor al 3000 del host
      - "3000:3000"
    environment:    # Esta sección permite setear varaibles de entornos dentro del contenedor
      PORT: "3000"
      RACK_ENV: "production"
      DATABASE_URL: "postgres://postgres:Passw0rd!@db:5432/postgres"
    depends_on:    # Para que levante "web", "db" deberá levantar primero
      - db
  db:    # Inicio de la definición del servicio "db"
    image: postgres    # Imágen a utilizar para el contenedor
    environment:    # 
      POSTGRES_PASSWORD: Passw0rd!
```

### Dado que cada contenedor corre en forma aislada ¿Cómo es posible que esos contenedores se vean entre sí?

Docker compose se encarga de poner los servicios en una misma red y de que puedan verse a través de sus nombres.
