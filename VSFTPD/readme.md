#VSFTPD

Guide d'installation  de FTP server (vsftpd) sur Ubuntu

Installation : En tapant les commandes suivant sur le terminal :
		sudo apt update
		sudo apt install vsftpd
Vérification du status  par le commande suivant : 
		sudo service vsftpd status 

Configuration du pare-feu : En suivant les instruction suivant : 
		sudo ufw allow OpenSSH

Pour ensuit ouvrir les  ports 20 et 21 pour le FTP: sudo ufw allow 20/tcp  &&  sudo ufw allow 21/tcp
			port 40000 et 50000 pour le FTP passif : sudo ufw allow 40000:50000/tcp
			port 990 pour le TLS : sudo ufw allow 990/tcp
Activer le pare-feu : sudo ufw enable
