 
# Bueno project

## Pré-requis (fait sur Debian)

### Installer git

**sudo apt-get install git**  

Renseigner vos informations :    
**sudo git config --global user.name "YOUR_USERNAME"**  
**sudo git config --global user.email "your_email_address@example.com"**  

Vérifier vos informations :  
**sudo git config --global --list**  

Persister vos informations :  
**sudo git config --global credential.helper store**  

### Installer visual studio code

Télécharger vsc :  
https://code.visualstudio.com/  

Installer vsc :  
**sudo dpkg -i code_1.42.1-1581432938_amd64.deb**  

Liste des extensions Laravel VueJS

https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel-blade
https://marketplace.visualstudio.com/items?itemName=codingyu.laravel-goto-view
https://marketplace.visualstudio.com/items?itemName=stef-k.laravel-goto-controller
https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client
https://marketplace.visualstudio.com/items?itemName=octref.vetur
https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint

### Installer docker (voir aussi chapitre installation alternative) (source : https://docs.docker.com/install/linux/docker-ce/ubuntu/)  

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

### Installation alternative de docker (source : https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/)  

sudo apt-get install \  
    apt-transport-https \  
    ca-certificates \  
    curl \  
    gnupg-agent \  
    software-properties-common   

Télécharger les packages suivants :  
https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/containerd.io_1.2.6-3_amd64.deb  
https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/docker-ce-cli_19.03.6~3-0~debian-stretch_amd64.deb  
https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/docker-ce_19.03.6~3-0~debian-stretch_amd64.deb  

Installer les packages :  
sudo dpkg -i containerd.io_1.2.6-3_amd64.deb   
sudo dpkg -i docker-ce_19.03.6~3-0~debian-stretch_amd64.deb  
sudo dpkg -i docker-ce-cli_19.03.6~3-0~debian-stretch_amd64.deb  

Installer docker compose :  
sudo curl -L "https://github.com/docker/compose/releases/download/1.25.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose  
sudo chmod +x /usr/local/bin/docker-compose  

Tester l’installation:  
sudo docker run hello-world  


### Telecharger les sources et configurer le container Docker  

```diff
- Ne pas hésiter à modifier les droits sur les fichiers en cas d'erreur avec 
- sudo chmod -R 0777 ./
```

Télécharger les sources :    
**git clone https://github.com/loic-31/BuenoProject && cd BuenoProject**

Modifier les droits sur les fichiers (commande récursive à lancer depuis le dossier BuenoProject):  
**sudo chmod -R 0777 ./**  

Démarrer le container et télécharger les dépendances Docker :  
**docker-compose build**

**pwd**   
puis utiliser le chemin affiché pour l'insérer dans la commande suivante :  
<strong>docker run --rm -v INSERER_LE_CHEMIN_ABSOLU/my-site:/app composer install</strong>  

Linux : INSERER_LE_CHEMIN_ABSOLU = $(pwd)

En attendant le téléchargement des dépendances, renommer le fichier BuenoProject/my-site/**.env.exemple** en **.env**
(des adaptations sont sûrement à prévoir dans ce fichier).  

Lancer le container :  
**docker-compose up**  

Depuis un nouveau terminal :  
**docker exec -it php /bin/bash**  

Puis se positionner dans le dossier **/var/www** :  
**cd ..**  

Créer de la clé d’encryption  
**php artisan key:generate**  

Stopper le container :  
**docker-compose down**  

Modifier les droits sur les fichiers (commande récursive à lancer depuis le dossier BuenoProject):  
**sudo chmod -R 0777 ./**  

Démarrer le container :  
**docker-compose up**  

That's it :-)    
**http://localhost:80/**  

## Gestion des sources

```diff
- Penser à stopper le container avant de gérer les sources.
```
  
**docker-compose down**

### Commit  

sudo git add .  
sudo git commit -m "commentaire"  
sudo git push -u origin master

### Synchroniser le dépôt distant  

sudo git pull origin master  

## Auteurs

* **Mickael HUMPHREYS**
* **à compléter**
