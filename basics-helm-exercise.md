# Apprendre les bases de Helm

A la fin de cet exercice vous connaîtrez les bases de Helm, ainsi vous pourrez piloter vos déploiement sur un cluster local (`minikube`)

## Partie 1 : Mon premier chart ``Helm``

### La TODO

1. Installer Helm
1. Création d'un chart Helm (nginx)
1. Vérifier son package Helm
1. Packager un chart Helm
1. Déployer un chart Helm

### Résultat attendu

Lorsque l'on fait un port forward d'un des pods, nous arrivons sur la mire de nginx, sur le port `80`.

## Partie 2 : Enrichir un chart ``Helm``

### La TODO

> Cet exercice nécessite d'avoir effectué l'[exercice sur les bases de Kubernetes](https://github.com/yohikofox/formation-infrastructure/tree/basics/kubernetes-exercise)

1. Ajouter une définition de certificat TLS au chart
1. Ajouter une définition Ingress au chart

### Résultat attendu

Une fois la partie Ingress effectuée, le service nginx devra être accessible depuis l'extérieur du cluster, sans port-forward et de manière sécurisée.

## Partie 3 : Rendre disponible son chart Helm

> **/!\\** : Par soucis de sécurité, ce qui suit nécessite de publier des ressources en mode publique. Assurez-vous de ne pas publier de données sensibles (Token, clé, password, email, etc ...)

### La TODO

1. Créer un dépôt publique Github pour y héberger nos charts
1. Enrichir ce dépôt avec vos charts
1. Indexer vos packages
1. Transformer ce dépôt en Github pages

### Résultat attendu 

Une fois la `Partie 3` effectuée, votre chart devrait être disponible sur internet.
