<!-- .slide: data-background-image="images/pull-illustration.jpg" data-background-size="1000px" class="chapter" -->

## Gitflow

%%%

<!-- .slide: data-background-image="images/pull-illustration.jpg" data-background-size="1000px" class="slide" -->

### Qu'est ce que le gitflow
- Git propose beaucoup d'outils pour le versionning : tagging, branches... 
<img src="images/git-workflow.png" alt="image-gitflow-simple">
- Gitflow est un modèle d'utilisation de git pour la bonne vie de votre dépot.

%%%

### Concepts du modèle gitflow : les branches
- Crée une hierarchisation des branches, un groupe de branches stables (main,release,develop)
- Pour contribuer a une branche stable, il est préférable de passer par une validation (merge request, validation du code par des collègues)
- Des branches jetables plus petites pour découper le travail, une branche = une feature
<img src="https://www.cloudways.com/blog/wp-content/uploads/Mnaaging-branches-and-resolve-conflicts.jpg" alt="image-gitflow-simple">

Note:
Exemple particulier avec nautile, refactor de tout le modèle de données, une super feature et donc il a fallu aussi la rendre stable, sinon c'est les branches filles qui se trouvaient impactées

%%%

<!-- .slide: data-background-image="images/pull-illustration.jpg" data-background-size="1000px" class="slide" -->
### Contribution à un projet et gitflow
- Etablissement de règles (validation par les pairs, qualimétrie)
<img src="https://cdn-images-1.medium.com/max/1024/1*LVqz528eRju28a6R2tgWOw.png" alt="image-exemple-regles">
- Intégration continue du code, découpage des fonctionnalités
<img src="https://delicious-insights.com/assets/images/articles/workflows-scrum.png" alt="découpage" width=75%>
%%%

<!-- .slide: data-background-image="images/pull-illustration.jpg" data-background-size="1000px" class="slide" -->

### Les commandes classiques dans l'organisation gitflow
- Prise en charge d'une feature par un développeur 

```
git checkout develop 
git checkout -b feature_branch 
```

- puis ajout des changements après validation du code 

```
# optionnel git rebase -i feature_branch
git checkout develop 
git merge feature_branch
```

- Création d'une version release (mise en recette)

```
git checkout develop 
git checkout -b v0.0.1
```

- validation d'une release (exemple avec tag)

```
git checkout master 
git merge v0.0.1
git tag -a v0.0.1 -m "version 0.0.1"
```

%%%
<!-- .slide: data-background-image="images/pull-illustration.jpg" data-background-size="1000px" class="slide" -->
### Récapitulatif sur le gitflow
<a href="https://integration-gitflow.demo.dev.sspcloud.fr/">
<img src="https://user-content.gitlab-static.net/6117813685b6d0bb952e08acc05de19d7316464e/68747470733a2f2f692e696d6775722e636f6d2f6332725a7935452e676966" alt="lien-gitflow-interactif">
</a>
%%%

<!-- .slide: data-background-image="images/pull-illustration.jpg" data-background-size="1000px" class="slide" -->

### Fork

Je veux contribuer à un projet qui ne m'appartient pas.
Un projet d'un collègue ou un projet open source : Destinie, Onyxia, LibreOffice...
Je ne peux pas pusher directement.
*Je fork*

Mon fork est mon dépot distant *origin*.
Je le mets régulièrement à jour avec les évolutions du dépot qui ne m'appartient pas (dépot *upstream*).


%%%

<!-- .slide: data-background-image="images/pull-illustration.jpg" data-background-size="1000px" class="slide" -->

### Exercices

<a href="exercices/exercice-gitflow.html" target="_blank">C'est ici</a>