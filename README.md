 
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

Télécharger les sources et les dépendances du projet puis modifier les droits d'accès au fichiers :  

**git clone https://github.com/loic-31/BuenoProject && cd BuenoProject**
**pwd** puis utiliser le chemin affiché pour l'insérer dans la commande suivante  
**docker run --rm -v <insérer-le-chemin-ici>/my-site:/app composer install && sudo find . -type d -exec chmod +rx {} \;** 

Créer le fichier /my-site/.env |

exemple de fichier .env |
-------------
APP_NAME=Laravel |
APP_ENV=local |
APP_KEY=base64:u0MBHpstAnDAFVRLwxOmhzHRgVsqZuoAYZ5sEWG5JZw= |
APP_DEBUG=true |
APP_URL=http://localhost |
 |
LOG_CHANNEL=stack |
 |
DB_CONNECTION=mysql |
DB_HOST=127.0.0.1 |
DB_PORT=3306 |
DB_DATABASE=laravel |
DB_USERNAME=bueno |
DB_PASSWORD=bueno |
 |
BROADCAST_DRIVER=log | |
CACHE_DRIVER=file |
QUEUE_CONNECTION=sync |
SESSION_DRIVER=file |
SESSION_LIFETIME=120 |
 |
REDIS_HOST=127.0.0.1 |
REDIS_PASSWORD=null |
REDIS_PORT=6379 |
 |
MAIL_DRIVER=smtp |
MAIL_HOST=smtp.mailtrap.io |
MAIL_PORT=2525 |
MAIL_USERNAME=null |
MAIL_PASSWORD=null |
MAIL_ENCRYPTION=null |
 |
AWS_ACCESS_KEY_ID= |
AWS_SECRET_ACCESS_KEY= |
AWS_DEFAULT_REGION=us-east-1 |
AWS_BUCKET= |
 |
PUSHER_APP_ID= |
PUSHER_APP_KEY= |
PUSHER_APP_SECRET= |
PUSHER_APP_CLUSTER=mt1 |
 |
MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}" |
MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}" |


Lancer le container : 
**docker-compose up**

Depuis un nouveau terminal :  
**docker exec -it php /bin/bash **



Puis :
**http://localhost:80/**

## Auteurs

* **Mickael HUMPHREYS**
* **à compléter**
