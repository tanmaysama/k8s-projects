Hands On minikube-ingress project

#Enable the Ingress controller

To enable the NGINX Ingress controller, run the following command:

$ minikube addons enable ingress

#create deployments and services

$ kubectl apply -f web1-deployment.yaml

$ kubectl apply -f web2-deployment.yaml

$ kubectl apply -f web1-svc.yaml

$ kubectl apply -f web2-svc.yaml

#create ingress resource 

$ kubectl apply -f ingress.yaml

#find out minikube ip

$ minikube ip

#create entry in /etc/hosts for dns resolution

add below line for dns resolution in /etc/hosts file

192.168.49.2 hello-world.info

#Test your Ingress

$ curl http://hello-world.info

Output:

Hello, world!
Version: 1.0.0
Hostname: web-55b8c6998d-8k564

-------------------------------------------------------------------

$ curl http://hello-world.info/v2

Output:

Hello, world!
Version: 2.0.0
Hostname: web2-75cd47646f-t8cjk


