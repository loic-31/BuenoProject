 
# Bueno project

## Pré-requis

* git (avec nom et email renseigné https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html#add-your-git-username-and-set-your-email)  
* docker

Selon la doc de laravel, le fichier /my-site/.env (fichier caché) ne doit pas être versionné.  
Il faudra peut être le modifier et l'exclure du versionning.  

## Installation

Télécharger les sources et les dépendances du projet et modifier les droits d'accès au fichiers :  

**git clone https://github.com/loic-31/BuenoProject && cd BuenoProject**
**pwd** puis utiliser le chemin affiché pour l'insérer dans la commande suivante  
**docker run --rm -v <insérer-le-chemin-ici>/my-site:/app composer install && sudo find . -type d -exec chmod +rx {} \;** 

Lancer le container : 
**docker-compose up**

Puis :
**http://localhost:80/**

## Auteurs

* **Mickael HUMPHREYS**
* **à compléter**
