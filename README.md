# Git Sheet

### Config

On initialise un nom + email, qu'on peut modifier à tout moment avec :

`git config --global user.name "John doe"`

`git config --global user.email "johndoe@gmail.com"`

### Init

On initialise un dépôt avec :

`git init`

### Status

On s'informe du statut de notre dépôt, par rapport aux fichiers ajoutés/modifiés avec :

`git status`

### Add

On rajoute les fichiers dans une zone de transit avec :

`git add index.html`

Pour ajouter plusieurs fichiers dans le transit:

`git add index.html style.css`

Pour ajouter tous les fichiers dans le transit:

`git add .`

### Commit

On sauvegarde l'état du dossier avec un commit :

`git commit -m "Ajout de xxx"`

### Log

On regarde l'historique des commits (des sauvegardes) :

`git log`

### Amend

Pour rattraper un commit dans lequel on aurait oublié d'intégrer un fichier, on ajoute d'abord le ou les fichiers oubliés :

`git add fichieroublié.js`

Puis on exécute cette commande :

`git commit --amend`

Une fois sorti de l'interface qui s'affiche, c'est fait, le commit est réalisé avec le fichier manquant.

Pour changer le nom du commit head ainsi qu'add les fichiers modif:

`git commit --amend -m "nom"`

### Branch

Pour lister les branches :

`git branch`

Pour créer une branche :

`git branch maBranche`

Pour se déplacer sur une branche

`git switch maBranche`

### Merge

Pour faire fusionner une ou plusieurs branches, on se déplace d'abord sur la branche qu'on veut fusionner avec une autre puis :

`git merge autreBranche`

De base, vous pouvez tomber sur trois types de fusion :

- Fusion simple "Fast Forward", les historiques de commits se lient sans conflit, car il y avait des changements seulement sur une branche.
- Fusion par récursion, lorsque il y a des commits différents sur plusieurs branches qu'on "merge", mais que ces commits ne rentrent pas en conflit.
- Fusion avec conflit, lorsqu'il y a des commits différents sur plusieurs branches que l'on "merge" et que ces commits modifient des choses similaires(ajout de code à la même ligne, changement du code initial, supression de fichiers) .

### Supprimer et rename une branche

Afin de supprimer une branche, on doit se situer sur une branche différente de celle qu'on veut supprimer, puis :

`git branch -d maBranche`

Afin de créer une branche et de se déplacer dessus intantanément, on éxécute :

`git switch -c maBranche`

Lorsqu'on veut changer le nom d'une branche, on navigue dessus, puis on lance :

`git branch -m changementDeNom`

### Diff

Afin de visualiser les changements qui ont eu lieu dans les fichiers modifiés, on peut éxécuter :

`git diff`

### Checkout

La commande git checkout possède des tonnes d'utilisations possibles.

Dans cette la vidéo précédente nous avons vu qu'elle nous permet de nous déplacer de branche en branche :

`git checkout nomDeBranche`

On peut aussi créer une branche avec checkout, même si on lui préfère git branch aujourd'hui :

`git checkout -b nomDeBrancheACréer`

Nous avons vu que nous pouvons également nous déplacer parmi les commits avec checkout :

`git checkout idDeCommit(ex: 45645645)`

Pour revenir en haut de la liste de commits, nous pouvons faire au chois :

`git switch nomDeLaBrancheEnCours`

`git checkout nomDeLaBrancheEnCours`

### Tag

Enfin dans la seconde partie nous avons vu que nous pouvions créer des tags pour mieux nous repérer.

On se déplace d'abord sur le commit que l'on veut "taguer", puis :

`git tag nomDuTag`

Nous pouvons désormais nous déplacer vers le commit du tag correspondant :

`git checkout nomDuTag`

Nous pouvons visualiser la liste de tags :

`git tag`

Nous pouvons supprimer un tag :

`git tag -d nomDuTag`

### Restore

Si on a effectué des changements et qu'ils ne nous plaisent plus :

`git restore nomDuFichier`

Cela permet de rapidement remettre à zéro un fichier sur lequel on travaillait, ça ne veut pas dire que le fichier sera forcement vide, il reaffiche simplement le contenu du commit sur lequel on se trouve.

On peut visualiser un fichier qui se situe à un ancient commit, afin de voir son code, avec :

`git restore --source HEAD~3 index.html`

Cela nous montre le code de l'index.html 3 ancêtres avant le commit sur lequel je me trouve, à vous d'ajuster le tilde(~) en fonction de ce que vous voulez visualiser.

Pour revenir à l'état de votre fichier dans le commit où vous vous trouviez :

`git restore nomDuFichier(ici index.html)`

ou

`git checkout HEAD nomDuFichier`

Nous pouvons également supprimé les fichiers en zone de transit avec :

`git restore --staged index.html`

### Reset et Revert

Pour afficher l'historique de commits sur une ligne :

`git log --oneline`

Pour supprimer des commits jusqu'à un commit passé :

`git reset idCommit`

Pour supprimer des commits jusqu'à un commit passé tout en supprimant les changements qu'il peuvent avoir été éffectués :

`git reset --hard idCommit`

Pour sauter un ou des commits et atterir dans un nouveau commit contenant le contenu d'un ancien commit :

`git revert idDuCommitÀRetrouver`

### Cherry-pick

Pour intégrer seulement un commit ou des commits qui nous intéressent mais pas une branche entière :

`git cherry-pick idDuCommit`

On se place au préalable sur la branche qui veut intégrer ces commits, comme pour un merge.

### Github

Pour lier un dépôt distant à un dépôt local :

`git remote add origin urlDepotDistant`

Pour envoyer le contenu du dépôt local vers le dépôt distant, tout en liant les branches main à main avec -u(upstream) :

`git push -u origin main`

### Clone

Pour cloner un dépôt :

`git clone urlDuDépôtÀCloner`

Afficher toutes les branches et les branches du dépôt distant en rouge(remotesBranches) :

`git branch -a`

Afficher seulement les remotes branches

`git branch -r`

### Remote

Afin de visualiser la liaison d'un dépôt local on peut faire :

`git remote -v`
