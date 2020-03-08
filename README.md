# kubernetes-ingress
Setup of Kubernetes Ingress Controller and Mapping to different services

To configure Ingress in Kubernetes Cluster(Bare Metal) we need to configure Ingress Controller first and then Ingress resource.

Steps to configure Nginx Ingress controller.

1. Create the Service account and namespace.
   kubectl apply -f ns-and-sa.yaml
2. Create Role based access for the namespace.
   kubectl apply -f rbac.yaml
3. Add the certificate key and value inside secret.
   kubectl apply -f default-server-secret.yaml
4. Create a default kubernetes config object
   kubectl apply -f nginx-config.yaml
5. Create the Nginx Ingress controller as Deployment object.
   kubectl apply -f nginx-ingress.yaml
6. Expose the Ingress Controller as Service.
   kubectl apply -f nodeport.yaml

Configure Ingress Resource.
   kubectl apply -f ingress-rule.yaml

Start all your application and expose as service.
   kubectl apply -f application.yaml
