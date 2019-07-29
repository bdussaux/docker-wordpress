
# Docker pour Wordpress

### Description 🧐

Voici le docker-compose que j'utilise pour mes projets Wordpress. Celui-ci utilise les conteneurs suivants :

 - La dernière version de MySQL
 - La dernière version de Wordpress
 - La dernière version de phpMyAdmin

 
### Installation de Docker 🐳 

Pour installer Docker, il faut suivre les étapes suivantes :

1. Intaller Docker :

     * <a href="https://docs.docker.com/installation/mac/" target="_blank">installation sur Mac OS X</a> (s'occupe d'installer Docker et Docker Compose)
     
     * <a href="https://docs.docker.com/installation/ubuntulinux/" target="_blank">installation sur Ubuntu</a>
     
     * <a href="https://docs.docker.com/installation/" target="_blank">installation sur d'autres systèmes</a>
 
2. Les utilisateurs Mac OS X ont finit l'installation. Les autres doivent continuer avec les étapes suivantes.
   
3. Aller sur le <a href="https://github.com/docker/compose/releases" target="_blank">repository des versions de Docker</a>.

### Installation de Docker Compose 🐳 

Pour installer Docker Compose, il faut suivre les étapes suivantes :

1. Saisir la commande `curl` suivante dans le terminal.

     La commande a le format suivant :

        curl -L https://github.com/docker/compose/releases/download/VERSION_NUM/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
   
     Si vous avez des problèmes d'installation avec `curl`, il est possible d'utiliser `pip` à la place : `pip install -U docker-compose`
      
2. Appliquer les permissions d'exécution sur le binaire suivant :

		$ chmod +x /usr/local/bin/docker-compose

3. Tester si l'installation s'est bien passée.

        $ docker-compose --version
        docker-compose version: 1.4.0

### Modification du fichier docker-compose.yml 🖊

Pour que le container Wordpress utilise le bon volume pour charger ses fichiers, il faut adapter la ligne 22 du fichier docker-compose.yml :

	/chemin/vers/app/www:/var/www/html/

En modifiant simplement le `/chemin/vers/app/www` (la partie de la ligne 22 à gauche des : ) par le répertoire dans le lequel vous voulez mettre les fichiers du Wordpress, vous aurez terminé l'adaptation du fichier docker-compose.yml.

### Fonctionnement ⚙️

1. Démarrer les conteneurs :
     
Il faut tout d'abord se placer avec le terminal à la racine du dossier du jeu où le fichier docker-compose.yml se trouve en tapant :

		$ cd /chemin/vers/app/

Pour ensuite démarrer les 3 conteneurs, il faut taper la ligne suivante dans le terminal :

		$ docker-compose up

Une fois démarrés 🚀 :

 - phpMyAdmin est accessible depuis votre hôte sur l’adresse [http://localhost:8080/index.php](http://localhost:8080/index.php)
 - Wordpress est accessible sur l'adresse [http://localhost/index.php](http://localhost/index.php) 
 - Les fichiers du Wordpress se situent dans le répertoire /www/ du projet

