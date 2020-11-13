<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="chapter" -->

## Travailler avec un dépot distant

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Les avantages

Votre travail n'est pas stocké que à un endroit mais à plusieurs.
- vous pouvez perdre/casser votre poste ;)
- vous pouvez travailler depuis un autre poste

Et surtout, vous pouvez travailler à plusieurs !

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Les inconvénients

Deux commandes en plus : pull, push

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Zoom sur Pull

Je mets à jour ma branche local *main* avec les modifications que mes collègues ont mis sur le dépot distant :
~~~~
git pull origin main
~~~~

Prudemment, je mets à jours ma branche locale *origin/main*
Je l'inspecte avant de la merger dans ma branche locale *main*
~~~~
git fetch
git merge
~~~~


