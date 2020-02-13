 
# Bueno project

## Pré-requis

### Installer git

sudo apt-get install git  
**git config --global user.name "YOUR_USERNAME"**  
**git config --global user.email "your_email_address@example.com"**  

### installer docker

Selon la doc de laravel, le fichier /my-site/.env (fichier caché) ne doit pas être versionné.  
Il faudra peut être le modifier et l'exclure du versionning.  

## Installation

Télécharger les sources et les dépendances du projet et modifier les droits d'accès au fichiers :  

**git clone https://github.com/loic-31/BuenoProject && cd BuenoProject**
**pwd** puis utiliser le chemin affiché pour l'insérer dans la commande suivante  
**docker run --rm -v <insérer-le-chemin-ici>/my-site:/app composer install && sudo find . -type d -exec chmod +rx {} \;** 

Lancer le container : 
**docker-compose up**

Depuis un nouveau terminal :  
**docker exec -it php /bin/bash **

Puis :
**http://localhost:80/**

## Auteurs

* **Mickael HUMPHREYS**
* **à compléter**
