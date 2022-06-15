# ejercicio05

## HEALTHCHECK

Chequea el estado del container corriendo un comando dentro del mismo.

`HEALTHCHECK [OPTIONS] CMD <COMMAND>`

Las `OPTIONS` posibles son:

* `--interval=DURATION` (default: 30s)
* `--timeout=DURATION` (default: 30s)
* `--start-period=DURATION` (default: 0s)
* `--retries=N` (default: 3)

El check se va a ejecutar luego de `interval` segundos luego de que el contenedor arranque, de la misma manera, luego de `interval` segundos después del último check.
Si al comando le toma mas de `timeout` segundos terminar, el check se considera fallido.
`retries` indica cuantos reintentos consecutivos del check son necesarios para considerar al container `unhealty`
`start-period` indica un período de gracia al arrancar el contenedor, durante el cual al fallar el check, no se lo tiene en cuenta en el conteo de reintentos.

El status que retorne el comando ejecutado, va a ser el status del container. Si es:

* `0`, el estado del contenedor es `healthy`
* `1`, el estado del contenedor es `unhealty`


