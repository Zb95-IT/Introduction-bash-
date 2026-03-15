# Introduction-bash

1	#!/bin/bash
 2	# Script pour creer un projet selon le template suivant :
 3	# ~/Projets/nomDuProjet
 4	#               |->README.md
 5	#               |->nomDuProjet.sh
 6	
 7	# Nom du repertoire dans lequel creer les dossiers de projet :
 8	rep_proj=$HOME/Projets
 9	
 10	# Nom du repertoire du nouveau projet
 11	rep_new_projet=$rep_proj/$1
 12	
 13	
 14	# Test la presence d'un argument au lancement du script
 15	if [ "$#" -ne 1 ]; then
 16	echo "Vous devez rentrer un argument en lancant le script"
 17	exit 1
 18	fi
 19	
 20	# Tester l'existence du projet au lancement du script
 21	if test -d $rep_new_projet; then
 22	echo "Le Dossier $rep_new_projet existe deja"
 23	exit 1
 24	fi
 25	
 26	# Creation des dossiers de projets
 27	mkdir $rep_new_projet -p && touch $rep_new_projet/README.md $rep_new_projet/$1.sh
 28	echo "Création du dossier $rep_new_projet"
 29	
 30	# Edite des fichiers dans le dossier du projet cree
 31	echo "#!/bin/bash" >> $rep_new_projet/README.md
 32	echo "Initialisation du fichier $rep_new_projet/README.md"
 33	
 34	echo "#Projet $1" >> $rep_new_projet/$1.sh
 35	echo "Initialisation du fichier $rep_new_projet/$1.sh"
 36	echo "Projet $1 initialisé"
