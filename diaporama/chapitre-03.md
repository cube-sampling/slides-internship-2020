<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="chapter" -->

## Démarches pour un projet public

%%%

<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->
### Enjeux pour un projet public
L'open source consiste à l'ouverture du code pour une exposition externe. Les enjeux principaux sont donc : 
- Suppression de l'adhérence aux environnements (composants insee / non insee)
- Supression de toute donnée sensible de ces projets
- Génération de jeux de tests pour des environnements ouverts
- Documentation du projet sur les problématiques métier, comment contribuer

Cela est entré dans la loi pour le devenir des applications et données administratives : <a href="https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000033202746/">Loi pour une république numérique (2016)</a>

%%%

<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->
### L'environnement
Au niveau de l'architecture, il est important de décorreler construction de livrables et environnements. Au niveau global, il s'agit de pouvoir intégrer dans des environnements variés, un même livrable.
- Cela induit des travaux sur la modularité du code, un code s'abstrayant de son environnement d'execution
- Il se construit lors de l'initialisation d'un projet git, en prenant tous les fichiers dans l'arborescence fille pour commencer le versionning
```
git init .
```

Note:
Modularité : En fait il y a les livrables compilés du code, puis la dynamique d'état 
Cela peut s'avérer compliqué dans le cas de projet legacy stateful.  => Car adhérence a environnement de déploiement / vie de la vm
%%%
<!-- .slide: data-background-image="images/submarine.svg" data-background-size="600px" class="slide" -->
### Suppression des données sensibles

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
### Géneration des données 

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
### Documentation
La langue par défaut dans le monde open source est l'anglais, le code source doit donc être documenté en anglais. <br/>
Cela s'inscrit donc sur plusieurs projets pour l'ouverture du code :
- Documentation détaillée, en anglais pour construire un environnement de travail
- Code source également construit en langue anglaise
- Internationalisation des interactifs (i18n)