# Git


### Config

On initialise un nom + email, qu'on peut modifier à tout moment avec :

<span style="color:red;">git config --global user.name "John doe"</span>

<span style="color:red;">git config --global user.email "johndoe@gmail.com"</span>

### Init

On initialise un dépôt avec :

<span style="color:red;">git init</span>

### Status

On s'informe du statut de notre dépôt, par rapport aux fichiers ajoutés/modifiés avec :

<span style="color:red;">git status</span>

### Add

On rajoute les fichiers dans une zone de transit avec :

<span style="color:red;">git add index.html</span>

Pour ajouter plusieurs fichiers dans le transit:

<span style="color:red;">git add index.html style.css</span>

Pour ajouter tous les fichiers dans le transit:

<span style="color:red;">git add .</span>

### Commit

On sauvegarde l'état du dossier avec un commit :

<span style="color:red;">git commit -m "Ajout de xxx"</span>

### Log

On regarde l'historique des commits (des sauvegardes) :

<span style="color:red;">git log</span>

### Ammend

Pour rattraper un commit dans lequel on aurait oublié d'intégrer un fichier, on ajoute d'abord le ou les fichiers oubliés :

<span style="color:red;">git add fichieroublié.js</span>

Puis on exécute cette commande :

<span style="color:red;">git commit --amend</span>

Une fois sorti de l'interface qui s'affiche, c'est fait, le commit est réalisé avec le fichier manquant.

Pour changer le nom du commit head ainsi qu'add les fichiers modif:

<span style="color:red;">git commit --amend -m "nom"</span>

### Branch

Pour lister les branches :

<span style="color:red;">git branch</span>

Pour créer une branche :

<span style="color:red;">git branch maBranche</span>

Pour se déplacer sur une branche

<span style="color:red;">git switch maBranche</span>