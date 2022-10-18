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

### Merge

Pour faire fusionner une ou plusieurs branches, on se déplace d'abord sur la branche qu'on veut fusionner avec une autre puis :

<span style="color:red;">git merge autreBranche</span>

De base, vous pouvez tomber sur trois types de fusion :

- Fusion simple "Fast Forward", les historiques de commits se lient sans conflit, car il y avait des changements seulement sur une branche.
- Fusion par récursion, lorsque il y a des commits différents sur plusieurs branches qu'on "merge", mais que ces commits ne rentrent pas en conflit.
- Fusion avec conflit, lorsqu'il y a des commits différents sur plusieurs branches que l'on "merge" et que ces commits modifient des choses similaires(ajout de code à la même ligne, changement du code initial, supression de fichiers) .

### Supprimer et rename une branche

Afin de supprimer une branche, on doit se situer sur une branche différente de celle qu'on veut supprimer, puis :

<span style="color:red;">git branch -d maBranche</span>

Afin de créer une branche et de se déplacer dessus intantanément, on éxécute :

<span style="color:red;">git switch -c maBranche</span>

Lorsqu'on veut changer le nom d'une branche, on navigue dessus, puis on lance :

<span style="color:red;">git branch -m changementDeNom</span>

### Diff

Afin de visualiser les changements qui ont eu lieu dans les fichiers modifiés, on peut éxécuter :

<span style="color:red;">git diff</span>

### Checkout

La commande git checkout possède des tonnes d'utilisations possibles.

Dans cette la vidéo précédente nous avons vu qu'elle nous permet de nous déplacer de branche en branche :

<span style="color:red;">git checkout nomDeBranche</span>

On peut aussi créer une branche avec checkout, même si on lui préfère git branch aujourd'hui :

<span style="color:red;">git checkout -b nomDeBrancheACréer</span>

Nous avons vu que nous pouvons également nous déplacer parmi les commits avec checkout :

<span style="color:red;">git checkout idDeCommit(ex: 45645645)</span>

Pour revenir en haut de la liste de commits, nous pouvons faire au chois :

<span style="color:red;">git switch nomDeLaBrancheEnCours</span>

<span style="color:red;">git checkout nomDeLaBrancheEnCours</span>