#APACHE
Ceci est un guide pour l'installation et les configurations de fonctionnement d'apache sur Ubuntu.

Pour celà vous devez suivre les instruction suivant :

1- L'installation 

Entrer les commandes suivants :
		sudo apt update (pour le mise à jour de votre système)
		sudo apt install apache2 (pour installer les packages de apache2)
Et grâce à l' "apt" toutes les dépendances lier à apache serant également installer avec.

2- Vérification du server Web

Pour vérifier si votre serveur web fonctionne, taper : 
		sudo systemctl status apache2
Il devraient sortir plusieur ligne et sur la ligne "Active" doit afficher " active (running) "
Mais pour être sûr qu'il fonctionne en peut le vérifier avec la page d'accueil par défaut d'Apache en tapant le commande " hostaname -I " 
ainsi vous obtiendriez quelque adresse séparées par des éspaces et essayer chacune d'elles dans votre navigateur web savoir s'il fonctionne.
La page web a comme titre "Apache2 Ubuntu Default Page".

3- Configurtion du serveur web pour le domains

Le répertoire de configuration d'Apache et "/etc/apache2 " et "apache2.conf "est le fichier de configarution principal.
Chaque domaine a besoin de son propre fichier de configuration d'hôte virtuel, ces fichier utilise l'extension ".conf" 
et doivent être enregistrés dans le répertoire "/etc/apache2/sites-avaible/".
NB : le nom du domain dépend de votre choix 
	- Créer un fichier "yourdomain.com.conf" dans le "/etc/apache2/sites-avaible/" et ajouter les commandes suivant :
		nano /etc/apache2/sites-avaible/yourdomain.com.conf

		<virtualhost *:80=''>
		ServerAdmin webmaster@localhost
		ServerName yourdomain.com
		ServerAlias www.youdomain.com
		DocumentRoot /var/www/yourdomain.com
		ErrorLog ${APACHE_LOG_DIR}/error.log
		CustomLog ${APACHE_LOG_DIR}/access.log combined
		</virtualhost>

	- Créer un repertoire pour le site Web, puis céez "index.html" un fichier pour le site web:
		mkdir /var/www/yourdomain.com
		
	- Ajoutez du contenu à "index.html"
		vi /var/www/yourdomain.com/index.html
	
	- Redémarrer le service apache pour que les modificationd prennent effet.
		sudo systemctl restart apache2

	- Ouvrir le navigateur et entrer l'URL du site web 
		http://yourdomain.com
		
Il peut être également tester grâce à l'adresse IP du serveur.
Et il est bien de noter que maintenant vous pouvez l'utiliser à votre guise en modifiant 
seulement le fichier "index.html" ou en ajoutant d'autre élément à votre configuration.
