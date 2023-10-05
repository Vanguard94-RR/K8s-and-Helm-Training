# K8s and Helm Training

## Ingress

Create an ingress to expose the application to the exterior

1.- Using helm download and install nginx ingress controller

    helm repo add ingress-nginx <https://kubernetes.github.io/ingress-nginx>
    helm repo update
    helm install [RELEASE_NAME] ingress-nginx/ingress-nginx -n [DESIRED_NAMESPACE]

or if you are using MiniKube do:

    minikube addons enable ingress

2.-Create tls certificate and keys to deploy in your ingress

    openssl req -x509 -newkey rsa:4096 -sha256 -nodes -keyout tls.key -out tls.crt -subj "/CN=pgadmin-basic.com" -days 365

then create secret

    kubectl create secret tls pgadmin-basic-com-tls --cert=tls.crt --key=tls.key

STILL IN CONTRUCTION


kubectl delete -A ValidatingWebhookConfiguration ingress-nginx-admission

{{- if eq .Values.env "production" }}
replicas: 2
{{- else }}
replicas: 1
{{- end }}

## Issues

    Unable to perform rolling update, error in secret

    Unable to log in to database with provided credentials

    Ingress is not working, we can't use the exposed ip and url to access pgadmin

    Unable to use if selector for replicas on deployment chart
