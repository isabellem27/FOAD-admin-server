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