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

## ONBUILD

Permite agregar una instrucción a la imágen que se va a ejecutar cuando sea usada como base para otro build.
Se ejecuta inmediatamente luego del `FROM` que haga referencia a la imágen base y que contiene la instrucción.

`ONBUILD <INSTRUCTION>`

Por ejemplo, si queremos hacer una imágen base que sirve una aplicación web Java, no se puede hacer `ADD` durante 
el build de la imágen base, ya que no se tiene el código en ese momento. Se puede utilizar `ONBUILD` para copiar el código en el build "hijo".

## VOLUME

Crea un punto de montaje en el conenedor con el nombre expecificado mapeado a una ubicación en el sistema de archivos del host.

`VOLUME ["<MOUNTPOINT>"]`

Los volúmenes se utilizan cuando los datos que se van a escribir en una ubicación necesitan sobrevivir al ciclo de vida de un contenedor. Por ejemplo, si se corre un motor de base de datos en un contenedor, se esperaría que la ubicacion que usa el motor sea un volúmen para que al matar el contenedor y crear otro nuevo, los datos no se pierdan. 
