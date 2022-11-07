# Résumé pratique de la séance sur Git:

## Premières configurations.

1. Installer Git:<https://git-scm.com/downloads> puis suivez les instructions

Si vous souhaitez possedez un Windows et que vous souhaitez afficher des couleurs (recommandé pour visualiser les ajouts et suppressions), installez notepad++.


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

3. Faites ce que vous avez à faire

Pour le coup, je ne peux pas vous aider, il s'agit de coder, ajouter des fichier, en supprimer, en modifier... Si vous n'avez pas de mains, c'est complexe mais vous serez certainement en binôme.

## Gestion de votre projet.


1. Sélectionnez les fichiers qui vous interessent pour les emmener dans l'espace de <b>transit</b> ou <i>latent space</i>.

```
git add [Nom du ou des fichier(s)]
```

ou si vous voulez tout sélectionner : 

```
git add *
```

Si vous avez selectionné des fichiers que vous ne voulez pas dans l'espace de transit, vous pouvez les enlever facilement:

```
git rm --cached [Nom du ou des fichier(s)]
```

ou encore
 
```
git reset [Nom du fichier]
```

N'hesitez pas à effectuer des ```git status``` pour visualiser ou vous en êtes. C'est ici que la couleur peut vous aider.

2. Si vos changements vous conviennent, commitez

```
git commit -m "[Votre message de commit]"
```

## Gestion des branches

1. Pour créer une branche sur votre répertoire local:

```
git branch -b [Nom de la branche]
```

2. Pour changer de branche:

```
git checkout [Nom de la branche en destination]
```

3. Visualiser les branches locales et distantes

&rarr; Locales:

```
git branch
```

&rarr; Locales et distantes:
```
git branch -a
```

## Créer une branche locale, en raccord avec une branche distante

Ici, la branche distante existe et on cherche à générer une branche locale qui suit les update de la branche distante (avec des pull). Par exemple, si Xavier et Titouan ont avancé sur une branche de leur projet d'optimisation (définir la fonction objectif par exemple) à l'école depuis l'ordinateur de Xavier. Xavier peut push sa branche sur un répertoire distant et le partager à Titouan. Lorsque Titouan arrive chez lui le soir, il prefere continuer le projet. Il faut donc qu'il génère une branche sur son répertoire distant qui corresponde à cette branche "définition de la fonction objectif". Il faut les raccorder. 

D'abord, on regarde ou se situe la branche distante avec ```git branch -a```. 
Une fois le chemin de la branche distante récupéré, c'est simple:
```
git branch [Nom de la branche locale à créer] [Chemin vers la branche distante]
```

Attention à bien se mettre à jour comme sur n'importe quelle branche grâce à ```git pull```, peut-être que Xavier a avancé de son côté sur cette branche.

La meilleure pratique est la communication. Mais si vous en êtes incapables, il reste le  ```git pull``` sur la branche ainsi créée avant de créer encore une autre branche à partir de celle-ci. On évite bien des conflits de cette manière. Même si Xavier avance en même temps que Titouan, ils pourront règler leurs conflits au moment du ```merge```, et ne seront pas pris au dépourvu lors d'un ```pull``` anodin.

