# Comprendre et expliquer la différence en gestion centralisée et décentralisée
La gestion centralisée (type SVN) est le principe de partager sur un serveur les données. Les utilisateurs feront alors une copie de ces fichiers avant d'en mettre de nouveaux en ligne. Tandis que la gestion décentralisée (git) est le principe de se partager les données entre chaque utilisateurs. 

## Comprendre la notion de commit
Un commit est le fait de rajouter des données sur le contenu déjà existant afin de le partager avec tous les membres du projet.

## Citer des concurrents de git
SVN, Mercurial

# Les zones d'un projet Git
## Remise
Un endroit où remiser les modifications pendant que l'on travaille sur autre chose.
## Espace de travail
Espace de travail local.
## Index
Zone de transit qui maintient un instantané de l'espace de travail qui servira de base pour le prochain commit.
## Dépôt local
Sous répertoire nommé .git qui contient tous les fichiers nécessaires au référentiel. Branches typiques: master, fonction-x, correctif-y
## Dépôt distant
Version du projet qui est hébergé sur le réseau ou internet, pour mettre toutes les modifications à la disposition d'autres développeurs. Par défaut "origin". Branche typique: master, fonction-x-partagée, version-y.

# Configuration
## Configurer son nom 
````
git config --global user.name
````

## Configurer son mail 
````
git config --global user.email
````
# Créer un projet Git
## Créer un nouveau repo
```
git init
```

## Ajouter un fichier au suivi Git
````
touch README.md
git add ./README.md
````

# Ignorer un fichier
````
touch fichier-cache.txt
touch toto.js
touch yolo.js
touch .gitignore
````

Ajouter fichier-cache.txt dans le fichier .gitignore :

> **Ignorer un fichier**
> ---
> ./fichier-cache.txt

> **Ignorer un type de fichier**
> ---
> *.txt

> **Ignorer un fichier avec une règle**
> ---
> t*.js

## Voir l'état de mon répertoire de travail
````
git status
````

## Connecter le répertoire local avec le répertoire en ligne
````
git remote add origin <url-du-remote>
````

## Envoyer le projet 
````
git push -u origin master
````

# Récuperer un projet
````
git clone <url-du-remote<> <nom du dossier>
````

# Gérer des versions parallèles
## Créer une branche
````
git branch <nom-branche>
git push --set-upstream origin <nom-branche>
````

## Se déplacer sur une branche
````
git checkout ≤nom-branche>
````

## Lister les branches
````
git branch
````

## Créer et se dépalcer sur la branche
````
git checkout -b <nom-branche>
````

## Fusionner une branche
````
git merge <nom-branche>
````

## Créer une branche à partir d'un commit ancien
````
git branch <nom-branche> <id-commit>
````

## Supprimer une branche
````
git branch -d <nom-branche>
````

# Revenir à une version antérieure d'un commit
`````
git reset <id_commit>
`````

## Annuler un commit
`````
git commit -m "message"
git log (récupérer l'id du commit)
git revert <id_commit>
git commit "revert commit"
`````

## Effacer les modifications jusqu'à un commit précis
`````
git reset --hard <id_commit>
`````

## Effacer un commit en gardant les modifications dans l'espace de travail
`````
git reset --keep <id_commit>
`````

# Marquer un commit
## Nommer une version
Nomme le commit actuel
git tag <tagname>
git push origin <tagname>
## Récupérer une version nommée
git revert <tagname>

# Historique des versions
## Voir les différences entre deux commits
````
git diff
````

# Fusionner des versions parallèles
## Rebase une branche sur une autre
 ````
git checkout master
git rebase <nombranche>
````