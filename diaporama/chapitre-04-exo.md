<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="chapter" -->

## Travailler avec un dépot distant entrainement

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Pusher un nouveau dépot

Vous avez créé un dépot local, vous voulez le pusher sur un dépot distant.
Vérifiez que vous avez un bon .gitignore puis :

~~~~
git push
~~~~

Toutes les modifications de l'histoire (les *commit*) que vous avez inscrites en local sont maintenant aussi inscrites dans le dépot distant.

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Hihi

Mais oups on n'a pas créé de dépot distant ^^
~~~~
fatal: No configured push destination.
Either specify the URL from the command-line or configure a remote repository using

    git remote add <name> <url>

and then push using the remote name

    git push <name>
~~~~

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Reliez votre dépot (remote) local à un dépot (remote) distant

~~~~
git remote add <name> <url>
~~~~
Dans notre cas
~~~~
git remote add origin https://git.lab.sspcloud.fr/<votre idep>/<le-nom-du-projet>.git
~~~~

On ajoute un dépot distant. <br>
Il peut y en avoir plusieurs donc il faut lui donner un nom. Vous pouvez appeler votre dépot distant *toto* mais par convention on préfère appeler *origin* le dépot distant dont l'histoire fera foi.

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

On vérifie
~~~~
git remote --verbose
~~~~
ou
~~~~
git remote -v
~~~~

ce que ça donne
~~~~
origin  https://git.lab.sspcloud.fr/<votre idep>/<le-nom-du-projet>.git (fetch)
origin  https://git.lab.sspcloud.fr/<votre idep>/<le-nom-du-projet>.git (push)
~~~~

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Pusher un nouveau dépot
Tentez un git push
~~~~
$ git push
fatal: The current branch branche has no upstream master.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master
~~~~

Git ne sait pas où pusher, ni quoi pusher.<br>

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Solutions

Deux solutions : 
* soit vous lui indiquez à chaque fois où il faut pusher (sur votre dépot distant nommé *origin*) et ce qu'il faut pusher (en général votre branche main). Fatigant.
~~~~
git push origin main
~~~~
* soit vous lui indiquez une bonne fois pour toute que votre branche main devra être pushée sur la branche main de votre dépot distant nommé *origin*
~~~~
git push --set-upstream origin main
~~~~
Dorénavant vous vous contenterez d'un *git push* pour pusher sur le dépot distant *origin* votre branche main.

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

## Que versionner ?

Seul le code doit être versionné ! <br>
Éviter les faux fichiers texte (.odt). <br>
Les data n'ont pas à être versionnées (on pourra en reparler) <br>
Pour ne versionner que ce que vous voulez : indiquez dans un fichier ce que vous ne voulez pas versionner. <br>
Ce ficher se nomme .gitignore, le plus simple est de le mettre à la racine.
[Un exemple du .gitignore](https://git.stable.innovation.insee.eu/outils-transverses/migration-svn-git/-/tree/master#cr%C3%A9er-un-fichier-gitignore) extrait d'une bonne doc déjà citée.

%%%

<!-- .slide: data-background-image="images/rocket.svg" data-background-size="600px" class="slide" -->

### Partir d'un code préexistant

~~~~
git clone <url>
git remote --verbose
~~~~

~~~~
origin  <url> (fetch)
origin  <url> (push)
~~~~
