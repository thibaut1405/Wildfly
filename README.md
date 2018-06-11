# Wildfly-server
Création d'un serveur Wildfly dans un conteneur LXC avec ansible

Pour créer un serveur Wildfly, il faut suivre les étapes suivantes :

* Lancer le script de création du conteneur Ubuntu en passant en paramètre le nom du conteneur :

    ./01_create_ubuntu.sh [nom du conteneur]

  Le script réalise une mise à jour automatique du système et crée dans le nouveau système un utilisateur
  portant le même nom que l'utilisateur courant (vous devrez préciser le mot de passe
  pour cet utilisateur à la fin de la procédure). 

* Vérifier que le conteneur est accessible en ssh. Cette étape est obligatoire pour valider
  l'empreinte du serveur.
  
    ssh [IP du conteneur]

* Modifier l'inventaire Ansible. Pour cela, éditez le fichier inventory.ini et ajoutez l'adresse
  IP du conteneur dans le groupe ci-server

* Lancer le playbook Ansible à l'aide du second script :

    ./02_run_playbook.sh

* Vous pouvez accéder au serveur Wildfly à partir d'un navigateur Web à l'adresse :

    http://[ip conteneur]:8080
    

