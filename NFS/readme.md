NFS
C'est un protocole permettant à un ordinateur d'accéder à des fichier extérieurs via un réseau.

Pour créer un partage NFS sous Debian, il faut avoir au moins deux machines :
	- Un serveur Debian qui jouera le rôle de serveur NFS, avec un partage : /home/nfs
	- Un post client Debian qui jouera le rôle de client NFS

1- L'installation du serveur NFS
	a- Côter serveur

Installation : il faut taper les commandes suivant sur le terminal : 
		apt-get nfs-kermel-server
		apt install nfs-kermel-server 

Configuration : Créer un fichier de partage : cd /etc/exports/
	Ensuit, configurer les adresses IP des clients dans /etc/exports/ en tapent : 
		nano /etc/exports/
		#Pour configurer l'adresse client sur l'adresse IP server
		  /home/nfs    #saisir l'adresse ip du client ici#

Redémarrer nfs-sever : En suivant le commande : 
		/etc/exports/service nfs-kermel-server restart

Récupérer l'IP serveur pour le connecter sur le machine client : Comme suit : 
		ip addr

	b- Côter client
Installation : il faut taper les commandes suivant sur le terminal : 
		apt install nfs-common


2- Vérification du connexion NFS
Taper les commandes suivant :
		shownount -e #adresse ip du serveur
Cel devrais afficher le fichier de partage avec l'adresse IP du client.
