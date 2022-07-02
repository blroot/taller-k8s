# ejercicio10

### Para levantar el deployment

`kubectl apply -f deployment.yaml`

### Se comprueba el estado del deployment

```
# kubectl get deployment botardo

NAME      READY   UP-TO-DATE   AVAILABLE   AGE
botardo   1/1     1            1           5m14s
```

# Se le pide la versión al bot

![botardo](https://github.com/blroot/taller-k8s/blob/master/ejercicio10/Screenshot%20from%202022-07-02%2012-48-25.jpg "Botardo")

# Finalmente se destruye el deployment

`kubectl delete -f deployment.yaml`
