# ejercicio09

### Para desplegar el deployment

`kubectl apply -f deployment.yaml`

### Se puede ver que el deployment fué exitoso

```
# kubectl get deployment password-api

NAME           READY   UP-TO-DATE   AVAILABLE   AGE
password-api   3/3     3            3           2m16s
```

### También el detalle de los pods levantados

```
# kubectl get pods

NAME                            READY   STATUS    RESTARTS   AGE
password-api-6b5c84657f-g5lzd   1/1     Running   0          4m15s
password-api-6b5c84657f-jmlvj   1/1     Running   0          4m15s
password-api-6b5c84657f-qzh9p   1/1     Running   0          4m15s
```

### Se comprueba la aplicación dentro de cada pod

```
# kubectl exec -it password-api-6b5c84657f-g5lzd -- curl localhost:3000/password

{"password":"!333CcTtLl=="}

# kubectl exec -it password-api-6b5c84657f-jmlvj -- curl localhost:3000/password

{"password":"!754SsXxTtPp"}

# kubectl exec -it password-api-6b5c84657f-qzh9p -- curl localhost:3000/password

{"password":"!108DdPpGgQq"}
```

### Finalmente se destruye el deployment

`kubectl delete -f deployment.yaml`


