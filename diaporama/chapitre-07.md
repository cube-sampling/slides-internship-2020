<!-- .slide: data-background-image="images/logo-gitlab.svg" data-background-size="600px" class="chapter" -->

## GitLab

%%%

<!-- .slide: data-background-image="images/logo-gitlab.svg" data-background-size="600px" class="slide" -->

## Gitlab

Le code de Gitlab est open source.
N'importe qui peut se créer une instance de Gitlab.

A l'Insee :
- une instance pour les développeurs et les selfeurs d'AUS : gitlab.insee.fr

Pour tout le monde :
- l'instance "officielle" : gitlab.com

*Pour ces projets open source, l'Insee utilise GitHub*

%%%

<!-- .slide: data-background-image="images/logo-gitlab.svg" data-background-size="600px" class="slide" -->

## Merge request
- C'est l'implémentation gitlab des pull request
- Permet de proposer des développements et d'échanger sur les bugs / fonctionnalités concernées.

%%%

<!-- .slide: data-background-image="images/logo-gitlab.svg" data-background-size="600px" class="slide" -->

## Rebase et conflits

- Gitlab permet également de gérer les conflits 
<img src="https://about.gitlab.com/images/8_11/resolve_mc.gif">
- L'option de squasher les commits est également très appréciable, puisqu'elle permet d'éviter d'aller en local, de rebase puis de force push.

%%%

<!-- .slide: data-background-image="images/logo-gitlab.svg" data-background-size="600px" class="slide" -->

## Partie pratique

<a href="exercices/exercice-gitlab.html" target="_blank">C'est ici</a>

%%%

<!-- .slide: data-background-image="https://about.gitlab.com/images/ci/ci-cd-integrated_2x.png" data-background-size="1500px" class="slide" -->
## Bonus : intégration continue

- Gitlab embarque également un moteur d'intégration continue / déploiement continu
<img src="https://about.gitlab.com/images/blogimages/cicd_pipeline_infograph.png">
- Configuré dans le fichier .gitlab-ci.yml à la racine du projet : <a href="https://docs.gitlab.com/ee/ci/" target="_blank">plus d'informations</a>
