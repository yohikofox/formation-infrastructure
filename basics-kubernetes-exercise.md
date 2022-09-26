# Apprendre les bases de Kubernetes

A la fin de cet exercice vous connaîtrez les bases de Kubernetes, vous permettant ainsi de créer `pods`, `services`, `deployments` sur un cluster local (`minikube`)

## Partie 1 : Mon premier cluster

### La TODO

1. Création d'un cluster (minikube)
1. Créer un pod nginx
1. Créer un deployment nginx
1. Créer un service (1*)
    * Type `ClusterIP`
    * Basé sur un pod nginx
    * Doit servir 2 pods

### Résultat attendu

Lorsque l'on fait un port forward d'un des pods, nous arrivons sur la mire de nginx, sur le port `80`.

## Partie 2 : Access depuis l'extérieur

### La TODO

1. Installer un IngressController - nginx
1. Créer une ingress rule du protocole HTTP vers notre service nginx

### Résultat attendu

Une fois la partie Ingress effectuée, le service nginx devra être accessible depuis l'extérieur du cluster, sans port-forward.

## Partie 3 : Premier pas en sécurité

### La TODO

1. Installer un cert-manager
1. Créer un ClusterIssuer `selfSigned`
1. Créer un certificat TLS
1. Créer une ingress rule du protocole HTTPS vers notre service nginx

### Résultat attendu 

Une fois la partie Ingress effectuée, le service nginx devra être accessible depuis l'extérieur du cluster en HTTPS.

> Le ClusterIssuer étant un `selfSigned`, votre navigateur ne reconnaîtra pas votre certificat comme valide. C'est normal, des solutions existent mais ne sont pas l'objet de cette formation.
