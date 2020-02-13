 
# Bueno project

## Pré-requis

### Installer git

**sudo apt-get install git**  

Renseigner vos informations :    
**git config --global user.name "YOUR_USERNAME"**  
**git config --global user.email "your_email_address@example.com"**  

Vérifier vos informations :  
**git config --global --list**  

Persister vos informations :  
**git config --global credential.helper store**  

### Installer docker (copier coller de moodle)  

sudo apt-get update  
sudo apt-get install \  
    apt-transport-https \  
    ca-certificates \  
    curl \  
    gnupg-agent \  
    software-properties-common  
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
sudo apt-key fingerprint 0EBFCD88  
sudo add-apt-repository \  
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \  
   $(lsb_release -cs) \  
   stable"  
sudo apt-get update  
sudo apt-get install docker-ce docker-ce-cli containerd.io  

Tester l’installation:  
sudo docker run hello-world  


### Telecharger les sources et configurer le container Docker  

Télécharger les sources :    
**git clone https://github.com/loic-31/BuenoProject && cd BuenoProject**  
**pwd**   
puis utiliser le chemin affiché pour l'insérer dans la commande suivante :  
<strong>docker run --rm -v INSERER_LE_CHEMIN_ABSOLU/my-site:/app composer install</strong>  

Renommer le fichier BuenoProject/my-site/**.env.exemple** en **.env**
(des adaptations sont sûrement à prévoir dans ce fichier).  

Lancer le container :  
**docker-compose up**  

Depuis un nouveau terminal :  
**docker exec -it php /bin/bash **  

Puis se positionner dans le dossier **/var/www** :  
**cd ..**  

Créer de la clé d’encryption  
**php artisan key:generate**  

Stopper le container :  
**docker-compose down**  

Modifier les droits sur les fichiers (récursif):  
**chmod -R 0777 ./**  

Démarrer le container :  
**docker-compose up**  

That's it :-)    
**http://localhost:80/**  

## Gestion des sources 

### Commit  

git add .  
git commit "commentaire"  
git push -u origin master

### Synchroniser le dépôt distant  

git pull

## Auteurs

* **Mickael HUMPHREYS**
* **à compléter**
