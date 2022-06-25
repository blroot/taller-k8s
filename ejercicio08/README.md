# ejercicio08

### Para correr el ejercicio

`docker-compose up -d`

Y acceder a [localhost:8080](http://localhost:8080)

### Para parar el ejercicio

`docker-compose stop`

### Detalles

Nginx está configurado para balancear por round robin, se comprueba que los requests se alternan uno a uno

Primera request a [/health](http://localhost:8080/health)

```
{"host":"2a1fd730cc73","loadavg":[1.31298828125,0.81201171875,0.65087890625],"freemem":469479424,"appversion":"1.0.0"}
```

Segunda request a [/health](http://localhost:8080/health)

```
{"host":"1e477d476280","loadavg":[0.72265625,0.62841796875,0.609375],"freemem":544358400,"appversion":"1.0.0"}
```

