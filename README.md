# Option 1: Off-the-shell solution (assuming GCP)

Google Click to Deploy (aka. Google GCP marketplace) 


# Option 2: Cloud/On-prem agnostic

> Assuming there is already a Kubernetes cluster setup

To deploy RabbitMQ on Kubernetes run this: 

0. ```kubectl apply -f rabbitmq-kube/rabbitmq-kube.yamy```
1. visit http://localhost:31672 or https://localhost:31671
2. username and password are `guest` and `guest`

To destroy RabbitMQ on Kubernetes run this: 
```kubectl delete -f rabbitmq-kube/rabbitmq-kube.yaml```


### Local Testing on Mac with Docker for Mac Kubernetes enabled

0. Install docker for mac
1. Enable kubernetes through docker for mac GUI
2. ```$ kubectel proxy```, then visit: http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/
3. ```$ helm install stable/rabbitmq-ha --name my-rabbit --namespace rabbit -f rabbit.yaml```
4. wait...
5. ```kubectl port-forward my-rabbit-rabbitmq-ha-0 --namespace rabbit 5672:5672 15672:15672```
6. visit http://localhost:15672
