## Instalar minikube

$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-latest.x86_64.rpm

$ sudo rpm -Uvh minikube-latest.x86_64.rpm

## Arrancar el cluster

$ minikube start 

## Crear un pod

$ kubectl run POD-NAME --image=alpine:latest --port=80 80

## Exponer los puertos en minikube y eliminar un servicio

$ kubectl expose pod POD-NAME --type=LoadBalanceer --port=8080 --target-port=80
$ kubectl get services
$ kubectl describe services 
$ minikube service POD-NAME
$ kubectl delete service POD-NAME

## listar los pods

$ kubectl get pods

## Borrar un pod

$ kubectl delete pod POD-NAME

## Detener el cluster

$ minkube stop
