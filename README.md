# K8s and Helm Training


## Ingress

Create an ingress to expose the application to the exterior

1.- Using helm download and install nginx ingress controller

    helm repo add ingress-nginx <https://kubernetes.github.io/ingress-nginx>
    helm repo update
    helm install [RELEASE_NAME] ingress-nginx/ingress-nginx -n [DESIRED_NAMESPACE]

or if you are using MiniKube do:

    minikube addons enable ingress

STILL IN CONTRUCTION
