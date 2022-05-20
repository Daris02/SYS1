#NGINX

Guide d'installation de Nginx sur Debian (Linux)

Pour l'installer, suiver les commandes :
		sudo apt-get update
		sudo install nginx

Il se lance automatiquement après installation ou bien le lancer en utilisant la commande : 
		sudo service nginx start

Il est à noter que les fichier de configuration se trouve par défaut dans le répertoire /isr/local/nginx/conf ou 
/etc/nginx ou /usr/local/etc/nginx celà dépend de la machine utiliser.

Si le logiciel de serveur Web fonctionne, vous pouvez le contrôler en déterminant les processus avec le paramètre -s 
et en indiquant un certain signal. Cela peut se faire avec la commande : 
		sudo nginx -s signal 
		sudo nginx -s stop (pour interrompre immédiatement ngnix)
		sudo nginx -s quit (pour interrompre ngnix après que  tout les requêtes en obtenu une réponse)
		sudo nginx -s reload (le fichier de configuration est à nouveau chargé)
		sudo nginx -s reopen (les Log-Files sont relancés)
