# Introduction-bash

#!/bin/bash
# Script pour creer un projet selon le template suivant : #
# ~/Projets/nomDuProjet
#               |->README.md
#               |->nomDuProjet.sh

# Nom du repertoire dans lequel creer les dossiers de projet : #
rep_proj=$HOME/Projets
 
# Nom du repertoire du nouveau projet  #
rep_new_projet=$rep_proj/$1


# Test la presence d'un argument au lancement du script #
if [ "$#" -ne 1 ]; then
echo "Vous devez rentrer un argument en lancant le script"
exit 1
fi

# Tester l'existence du projet au lancement du script #
if test -d $rep_new_projet; then
echo "Le Dossier $rep_new_projet existe deja"
exit 1
fi

# Creation des dossiers de projets #
mkdir $rep_new_projet -p && touch $rep_new_projet/README.md $rep_new_projet/$1.sh
echo "Création du dossier $rep_new_projet"

# Edite des fichiers dans le dossier du projet cree #
echo "#!/bin/bash" >> $rep_new_projet/README.md
echo "Initialisation du fichier $rep_new_projet/README.md"

echo "#Projet $1" >> $rep_new_projet/$1.sh
echo "Initialisation du fichier $rep_new_projet/$1.sh"
echo "Projet $1 initialisé"
