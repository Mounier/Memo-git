
              ##########################################################################################
              ######################################## GIT MEMO ########################################
              ##########################################################################################


1. Créer un répo distant sur github.
2. Dans la console git bash, faire un "cd /c" -> cd jusqu'au workspace -> "cd workspace/" -> "git clone <lien repositoryGitHub.com>" 
3. Sur éclipse -> new java project -> décocher la case "Use default location" -> indiquer le chemin du dossier repo qui est dans workspace.
4. Aller dans le répértoire où se trouve le répo puis modifier le gitignore -> ajouter ".classpath" ".project" "gitignore"
5. Dans la console git bash se situer dans le repo puis -> git init -> git config --global user.name "mounier" -> git config --global user.email "dridri_du91@hotmail.fr"


# INITIALISATION 

## Cloner un dépot
git clone lien_github.com

## Créer un nouveau dépot
git init

# Username github
git config --global user.name "mounier"

# Adresse mail github
git config --global user.email "dridri_du91@hotmail.fr"

# Interface graphique git incluse
gitk


###### COMMANDES PRINCIPALES ######

# Mettre à jour le dépot local
git pull

# Status des fichiers
git status

# Premier commit
git add .
git commit -m "initial commit"

# Commit suivant
git add chemin_vers_mon_fichier
git commit -m "message du commit"

# Envoyer ses commit vers le dépot distant à partir de la branche sur laquelle on se trouve / d'une branche donnée
git push / git push origin nom_de_la_branche


###### BRANCHES ET CONFLITS ######

# Lister les branchs
git branch

# Créer une branch / créer une nouvelle branch et passer dessus
git branch nom_de_la_branche / git checkout -b nom_de_la_branche

# Supprimer une branche
git branch -d nom_de_la_branche

# Changer de branch
git checkout nom_de_la_branche

# Fusionner une branche avec la branche sur laquelle on se trouve
git merge nom_de_la_branche 

# En cas de conflits apres un merge, il faut régler manuellement ces confilts en éditant les fichiers indiqués par git.
# Après avoir rélgé les conflits on doit marquer les fichiers concernés comme fusionnés avec la commande suivante :
git add nom_du_fichier

# Après avoir fusionné les changements, on peut avoir un aperçu en utilisant :
git diff nom_de_la_branche_source nom_de_la_branche_ciblé


###### TAGS ######

# Pour obtenir l'id d'un commit il suffit de faire la commande suivante :
git log

# Lister les tags
git tag

# Créer un tag nommé V1.0 
git tag V1.0 id_du_commit

# Pusher un tag 
git push id_du_tag

# Pusher tous les tags
git push --tags


###### ANNULER COMMITS ######

# Pour obtenir l'id d'un commit il suffit de faire la commande suivante :
git log

#Annuler seulement un commit mais les fichiers eux, restent modifiés.
git reset id_du_commit

# Annuler les modifications d'un fichier alors qu'on a pas encore envoyer le commit et qu'on veut restaurer le fichier tel qu'il etait au dernier commit
# cela remplacera les changements dans votre arbres de travail avec le dernier contenu du HEAD. Les changements déjà ajoutés à l'index, aussi bien les novueaux fichiers, seront gardés.
git checkout nom_du_fichier 

#Supprimer tous les changements et validations locaux, récuperer le dernier historique depuis le serveur et pointer la branche principale locale dessus
git fetch origin
git reset --hard origin/master

# Annuler un commit et les modifs. /!\ Cela annulera sans confirmation tout le travail /!\
git reset --hard id_du_commit
git push --force

# Annuler/Supprimer un fichier avant un commit pour annuler un git add
git reset HEAD -- nom_du_fichier_a_supprimer

# Replay last commit with staged file.s as the same commit
git commit --amend
