# Setting up HTTP(S) Load Balancing for offer-service with Ingress example

This a a helm-chart repo for offers image (renuba/offers-image created using https://github.com/renuba/offers-microservice-spring-boot)
-have a k8s cluster

This directory (helm-chart) contains:

- `basic-ingress.yaml` defines an Ingress resource.
- `deployment.yaml` defines a Deployment resource.
- `service.yaml` defines a Service resource that makes the deployment reachable within your cluster.
- `values.yaml` placeholder values

Steps for deployment:

Way1 (with helm chart)

This directory (helm-chart) contains:

- `basic-ingress.yaml` defines an Ingress resource.
- `deployment.yaml` defines a Deployment resource.
- `service.yaml` defines a Service resource that makes the deployment reachable within your cluster.
- `values.yaml` placeholder values

1. open shell script in k8s cluster
2. package helm-chart using helm packhae helm-chart command
3. upload the package helm-chart artifact 
4. run command `helm install <deployment-name> <helm-chart artifact name>`

deployment take some time

5. use external IP address in ingress to access the api for example: http://34.96.125.39/api/v1/offers

Way2 (without helm chart)

- `offers-k8s-deployment-demo.yaml` defines an k8s deployment yaml file.

1. open shell script in k8s cluster
2. upload offers-k8s-deployment-demo.yaml file  
3. run command `kubectl apply -f offers-k8s-deployment-demo.yaml`

deployment take some time

4. expose the service using load balance with target port 1001

5. Access the api with exposed external ip address for example: http://34.118.72.142/api/v1/offers


This example shows how to run a web application behind
an [external HTTP(S) load balancer](https://cloud.google.com/load-balancing/docs/https)
using the [Ingress](https://cloud.google.com/kubernetes-engine/docs/concepts/ingress) resource.



