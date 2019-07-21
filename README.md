# How to install locally on Mac using Docker for Mac as testing purposes

0. Install docker for mac
1. Enable kubernetes through docker for mac GUI
2. ```$ kubectel proxy```, then visit: http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/
3. ```$ helm install stable/rabbitmq-ha --name my-rabbit --namespace rabbit -f rabbit.yaml```
4. wait...
5. ```kubectl port-forward my-rabbit-rabbitmq-ha-0 --namespace rabbit 5672:5672 15672:15672```
6. visit http://localhost:15672

