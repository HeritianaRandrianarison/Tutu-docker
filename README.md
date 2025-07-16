# Tuto-docker
# Commandes de Base Docker

Ce document résume les commandes Docker les plus utilisées pour créer, gérer, et déployer des conteneurs.

## Installation

### Vérifier si Docker est installé :
```bash
docker --version
```
### Télécharger une image depuis Docker Hub :
```bash
docker pull <nom_image>
```
### Supprimer une image :
```bash
docker rmi <nom_image>
```
### Conteneurs Docker
##Lancer un conteneur en mode interactif :
```bash
docker run -it <nom_image>
```
### Lancer un conteneur en arrière-plan (détaché) :
```bash
docker run -d <nom_image>
```
### Lancer un conteneur avec un port exposé :
```bash
docker run -p 8080:80 <nom_image>
```
### Lister les conteneurs actifs :
```bash
docker ps
```
### Lister tous les conteneurs (actifs et arrêtés) :
```bash
docker ps -a
```
### Arrêter un conteneur :
```bash
docker stop <nom_conteneur>
```
### Supprimer un conteneur :
```bash
docker rm <nom_conteneur>
```
### Construire une image
## Construire une image à partir d’un Dockerfile :
```bash
docker build -t nom_image .
```
### Volumes & Données
##Créer un volume :
```bash
docker volume create mon_volume
```
### Lister les volumes :
```bash
docker volume ls
```
### Monter un volume dans un conteneur :
```bash
docker run -v mon_volume:/chemin/dans/conteneur <nom_image>
```
### Nettoyage
## Supprimer tous les conteneurs arrêtés :
```bash
docker container prune
```
### Supprimer toutes les images inutilisées :
```bash
docker image prune
```
### Supprimer tout (dangereux) :
```bash
docker system prune -a
```
### Export & Import
## Exporter une image Docker :
```bash
docker save -o mon_image.tar nom_image
```
### Importer une image Docker :
```bash
docker load -i mon_image.tar
```
### Docker Compose (si utilisé)
## Lancer les services :
```bash
docker-compose up
```
### Lancer en arrière-plan :
```bash
docker-compose up -d
```
### Arrêter les services :
```bash
docker-compose down
```
### Logs et débogage
## Voir les logs d’un conteneur :
```bash
docker logs <nom_conteneur>
```
### Suivre les logs en temps réel :
```bash
docker logs -f <nom_conteneur>
```
### Réseaux Docker
## Lister les réseaux :
```bash
docker network ls
```
### Créer un réseau :
```bash
docker network create mon_reseau
```
### Connecter un conteneur à un réseau :
```bash
docker network connect mon_reseau <nom_conteneur>
```
### Déconnecter un conteneur d’un réseau :
```bash
docker network disconnect mon_reseau <nom_conteneur>
```
### Accéder au shell d’un conteneur
## Ouvrir un terminal dans un conteneur actif :
```bash
docker exec -it <nom_conteneur> /bin/bash
```
ou
```bash
docker exec -it <nom_conteneur> sh
```
### Redémarrage automatique
##Lancer un conteneur avec redémarrage automatique :
```bash
docker run --restart unless-stopped -d <nom_image>
```
### Taguer et envoyer une image
## Ajouter un tag à une image :
```bash
docker tag <image_id> moncompte/mon_image:latest
```
#### Se connecter à Docker Hub :
```bash
docker login
```
### Pousser une image vers Docker Hub :
```bash
docker push moncompte/mon_image:latest
```
### Mise à jour / upgrade
## Mettre à jour Docker (Linux avec apt) :
```bash
sudo apt update && sudo apt upgrade docker-ce
```
### Restart & Rebuild
## Redémarrer un conteneur :
```bash
docker restart <nom_conteneur>
```
### Rebuild une image (ex: après changement du Dockerfile) :
```bash
docker build --no-cache -t mon_image .
```

