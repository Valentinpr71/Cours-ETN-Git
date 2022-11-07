# Résumé pratique de la séance sur Git:

## Premières configurations.

1. Installer Git:<https://git-scm.com/downloads> puis suivez les instructions

2. Configurer Git

Rendez vous sur votre terminal de commande. ('''cmd''' sur votre barre de recherche windows ou clique-droit puis "Git Bash Here" sur Windows, Ctrl+Alt+T sur Linux). 

Configuration de votre nom d'utilisateur :
```
git config --global user.name "[votre nom]"
```

Configuration de votre adresse mail :
```
git config --global user.email "[Votre email]"
```

Vous pouvez créer un dépot Git local. Rendez-vous sur le dossier qui vous intéresse puis:
```
git init
```

Si vous ne voulez pas que des fichiers présents soient suivis par Git, ajoutez-les dans le fichier .gitignore. 
D'ailleurs, si vous développez dans un langage, vous pouvez trouver des templates de .gitignore propres à votre langage pour éviter de rajouter tous les fichiers liés et inutiles.
Voici une bonne adresse pour ça: <https://github.com/github/gitignore>




Si vous souhaitez possedez un Windows et que vous souhaitez afficher des couleurs (recommandé pour visualiser les ajouts et suppressions), installez notepad++.
