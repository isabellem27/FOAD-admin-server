# PROJET 1:

## Description:
Aller sur la plateforme : Play with Docker Classroom et faire le parcours tutoriel : Getting Started Walk-through for Developers > Stage 1: The Basics > Docker for Beginners - Linux
Créer un container contenant un fichier index.html. Le transformer en image docker et la déposer sur hub.docker.com

## Réalisation:
 Etape 1: créer un contenant, le laisser ouvert pour y ajouter le fichier html: docker container run -it /bin/sh
 Etape 2: Créer le fichier index.html et y écrire quelques lignes de html: 
    apk add nano
    echo "<!DOCTYPE html>" > index.html
    ls (le fichier est bien présent)
    nano index.html (pour compléter le code html , enregistrement des modifications)
    exit
Etape 3: transformer mon container en image: 
    docker ps -a (pour repérer le nom du container - relaxed_banzai)
    docker commit relaxed_banzai isabellem27/docker_projet1
Etape 4: Déposer l'image sur hub.docker.com: 
    docker login    (copier le code connexion fourni par le système dans la page https://login.docker/activate pour accéder au dépot)
    docker push isabellem27/docker_projet1

## médias:
    FAL_00.png : copie d'écran de l'étape 4
    PROJET1.png : copie d'écran de mon dépot sur hub.docker.com

# PROJET 2:

## Description:
Installer un serveur avec les spécifications suivantes , libre à vous de choisir l'outil (Vagrant,VirtualBox) :
    Systéme d'exploitation: Debian (12 ou 13)
    CPU : 2
    RAM : 2Go
    Disque dur : 20Go
    Ajouter un utilisateur nommé foad avec des droits sudo , permettre à l'utilisateur foad de ne pas entrer son mot de passe à chaque fois qu'il accede aux droits administrateur
    Installer les applications suivantes : ufw,docker
Securiser le serveur:
    Créer un script bash pour mettre à jour le systeme d'exploitation du serveur , le rendre éxécutable et le mettre dans /usr/local/bin/
    Sécuriser votre serveur en générant des clefs SSH
    Ne pas permettre à root de se connecter à la machine
    Ajouter les régles nécessaires pour le pare feu ufw pour sécuriser votre serveur
    Installer et lancer l'application à travers docker :
        Récupérer l'image que vous uploader sur hub.docker.com
        Créer un container avec votre image pour lancer votre application



## Réalisation:
 Création de la VM-FOAD, redirection des ports 22 (2222) et 80 (8080)
 Création de l'utilisateur foad
 Création de la clé ssh ed25519_VM_FOAD et ajout dans le fichier .ssh/config du poste 
 Suppression du fichier known_hosts du poste et envoi de la clé ssh publique au serveur
 Installation de ufw, réglage de la sécurité
 Modification du fichier /etc/ssh/sshd_config pour ne plus demander le mot de passe et interdire l'accès à root
 

## médias:
    FAL_01.png : copie d'écran de l'étape 4
    FAL_01.png : copie d'écran de la VM-FOAD
    FAL_02.png : copie d'écran de la réponse de hostnamectl dans le terminal du serveur.
    FAL_03.png : copie d'écran du bloc host pour la connexion ssh à la VM-FOAD
    reglage-ufw.png : copie d'écran du réglage de la sécurité
    sshd_config : copie du fichier sshd_config du serveur