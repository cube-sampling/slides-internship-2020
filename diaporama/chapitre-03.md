<!-- .slide: data-background-image="images/treasure-map.svg" data-background-size="800px" class="chapter" -->

## Démarches pour un projet public

%%%

<!-- .slide: data-background-image="images/treasure-map.svg" data-background-size="600px" class="slide" -->
### Présentation des enjeux principaux
L'open source consiste à l'ouverture du code pour une exposition externe. Les enjeux principaux sont donc : 
- Suppression de l'adhérence aux environnements (composants insee / non insee)
- Supression de toute donnée sensible de ces projets
- Documentation du projet sur les problématiques métier, comment contribuer

Cela est entré dans la loi pour le devenir des applications et données administratives : <a href="https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000033202746/" target="_blank">Loi pour une république numérique (2016)</a>

%%%

<!-- .slide: data-background-image="images/treasure-map.svg" data-background-size="600px" class="slide" -->
### L'environnement
Au niveau de l'architecture, il est important de décorreler construction de livrables et environnements. Au niveau global, il s'agit de pouvoir intégrer dans des environnements variés, un même livrable.
- Etude des mécanismes de génération des livrables <!-- .element: class="fragment" -->
- Modularité du code et utilisation des composants internes<!-- .element: class="fragment" -->


Note:
Archi : En fait il y a les livrables compilés du code, puis l'environnement, bdd vm jetons ...
Livrables : Cela induit des travaux sur le packaging du code, un code s'abstrayant de son environnement d'execution
Modularité du code : Mais également des travaux sur sa modularité, séparant les composants que l'on peut externaliser des autres

Ouverture:
Cela peut s'avérer compliqué dans le cas de projet legacy stateful.  => Car adhérence a environnement de déploiement / vie de la vm (c'est d'ailleurs pour cela que l'on parle de stateless depuis quelques années )


%%%
<!-- .slide: data-background-image="images/treasure-map.svg" data-background-size="600px" class="slide" -->
### Suppression des données sensibles
Par définition, le versionning est l'établissement de versions correspondant aux étapes de développement d'un projet.<br/>
- Le versionning implique donc que l'on peut accéder à d'anciennes versions du projet<!-- .element: class="fragment" -->
- Il faut donc se méfier des anciennes versions du projet et en clarifier l'historique<!-- .element: class="fragment" -->


Note:
En fait, on ne sait jamais ce qu'il y au sein des caches et volumes des serveurs cloud où seront hébergé le code à l'avenir. Et donc, il faut considérer qu'il n'y a pas de moyen de résoudre un problème de sécurité sur le dépôt de code à posteriori

Git: 
La puissance des outils de versionning comme Git permet d'accéder a l'intégralité de l'historique d'un dépôt projet 

Il est donc nécessaire de s'assurer qu'il n'y a ni données sensibles, ni mot de passes dans chacune des versions du code source du projet avant de le sortir afin d'éviter tout risque
%%%

<!-- .slide: data-background-image="images/treasure-map.svg" data-background-size="600px" class="slide" -->
### Documentation
La langue par défaut dans le monde open source est l'anglais, le code source doit donc être documenté en anglais. <br/>
Cela s'inscrit donc sur plusieurs projets pour l'ouverture du code :
- Documentation détaillée, en anglais pour construire un environnement de travail
- Code source également instruit en langue anglaise (dont les classes métier)
- Internationalisation des interfaces (i18n)