<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="chapter" -->

## Open source et administration

%%%

<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->

### Créer un dépot local
- Le dépot local se situe directement sous .git à la racine de votre projet, c'est lui qui contient toutes les informations permettant à git de fonctionner correctement
```
cd .git
ls
```
- Il se construit lors de l'initialisation d'un projet git, en prenant tous les fichiers dans l'arborescence fille pour commencer le versionning
```
git init .
```
%%%
<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->
### Créer un dépot local à partir d'un dépot distant

On repart rarement de rien. Souvent, on repart d'un travail de collègue :

~~~~
git clone <url en https>
~~~~
exemple avec ce code de formation

~~~
git clone https://git.lab.sspcloud.fr/formation/git/formation-git-orleans-oct-2020.git
~~~

Vous venez de créer un dépot local avec l'ensemble de l'histoire du dépot distant

%%%
<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->

### Création d'une version

- Pour pouvoir ajouter des fichiers à une version il faut donc indiquer à git qu'il peut les référencer pour la prochaine version (en les plaçant dans son index)
```
git add fichier
git add .
```
- Pour savoir à quel état sont vos fichiers, vous pouvez également le vérifier : 
```
git status
```
- Un commit est une version d'une application à un état sauvegardé dans le dépot.
- Lorsque l'ensemble des fichiers ajoutés est cohérent pour la réalisation d'une version, on réalise donc une nouvelle version en créant un commit
```
git commit [options]
```

%%%
<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->

### Récapitulatif ajout de fichier

<img src="https://blog.axosoft.com/wp-content/uploads/2019/11/wd-sd-commit.gif" alt="travail-staging-commit">

Note:
Source : https://blog.axosoft.com/learn-git-commit/
Vous pouvez donc voir qu'un fichier de votre dépot "project", passe par une étape de staging avant d'être pérennisé par un commit

%%%
<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->

### Création de branche
- Permet de créer un sous espace dédié à une version de l'application ex: nouvelle fonctionnalité, application mise en recette, preview
```
git branch nouvelle-branche
```
- Vous pouvez naviguer entre différentes versions de l'application par un checkout
```
git checkout nouvelle-branche
```
- N'a aucun coût de stockage, donc il ne faut vraiment pas hésiter à en faire.
- Pour voir vos branches
```
git branch
```
 - Pour voir toutes vos branches
```
git branch --all
```
%%%

<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->

### Exercices

<a href="exercices/exercice-git-local.html" target="_blank">C'est ici</a>

%%%

<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->

### Gitignore : limiter le versionning
- Seul le code compte ! (Les data n'ont pas à être versionnées via git)
- Les fichiers non textuels sont lourds à versionner (attention aux faux fichiers texte .odt)
- Vous ne voulez nécessairement pas versionner tous les fichiers d'un projet, pour cela, vous pouvez définir les fichiers que vous ne voulez pas versionner à l'aide d'expressions régulières (regex) à l'intérieur d'un fichier .gitignore, ce que vous ne voulez pas versionner dans votre application
```
echo toto > toto.tmp
echo *.tmp >> .gitignore
git status
```
- Vous pouvez également définir cela au niveau de votre configuration globale git, pour par exemple, éviter d'ajouter par erreur les properties ou éviter de polluer un dépot avec votre configuration eclipse / intelliJ
Note:
1) exemple avec les fichiers .tmp
2) global gitignore, c'est vraiment pratique, lisez la doc
