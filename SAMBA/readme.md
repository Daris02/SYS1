Ceci est guide d'installation du serveur fichier Samba

Installation : Suivre les commande ci-dessous :
		sudo apt-get install samba
		apt install samba

Configuration : Le fichier /etc/samba/smb.conf permet de le configurer. Ce fichier est composé de sections dont le nom est 
		entre crochets : 
				- [global] : contient les paramètres généraux des différents partages
				- [printers] et [prints] sont spécifiques au partage d'imprimantes
				- [homes] est spécifique au partage du répertoire personnel d'un utilisateur (son repertoire
$HOME) il apparaîtra dans la liste des partages avec le nom d'utilisateur du client (s'il est identifié).
				- [le_nom_d'un_partage] pour caque partage

Paramétre à faire : 
	- Configuration des machines (côter serveur et côter client)
	- Création des comptes utilisateurs Unix
	- Création des répertoires logons et profiles
	- Création des comptes utilisateurs Samba
	- Création des comptes de machines
	- Création du compte administrateur de domaine 
	- Connexion au domaine

Configurer le partage de données : 
	- Autorisations générales, dans sudo gedit /etc/samba/smb.conf
	- Autorisations personnelles, dans sudo usermod -aG sambashare NOM D'UTILISATEUR
