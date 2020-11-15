<!-- .slide: data-background-image="images/cube.svg" data-background-size="600px" class="chapter" -->

## Application à un service de tirage

%%%

<!-- .slide: data-background-image="images/cube.svg" data-background-size="600px" class="slide" -->

### Description du besoin

Les fusions se produisent dans trois cas :

- intégration d’une branche
- `git merge <branche_name>`
- récupération de modifications « extérieures »
- `pull`, `cherry-pick`, `patch`
- réécriture de l’historique local
- `git rebase master`

Les techniques présentées ici sont valables dans les trois cas

**Rappel :**

- `git pull`
- `git fetch`
- `git merge origin/master`

%%%

<!-- .slide: data-background-image="images/cube.svg" data-background-size="600px" class="slide" -->

### Utilisation d'un existant open source

La fusion est toujours locale

- aucun risque de casser quoique ce soit

On peut toujours annuler l’opération

- `git merge --abort`
- `git rebase --abort`

Il est toujours préférable d’avoir une copie de travail propre

- valider : `git commit`
- ou remiser* : `git stash`

Note:
Voir bonus dans travailler en local
%%%

<!-- .slide: data-background-image="images/logo.svg" data-background-size="600px" class="slide" -->

### Réalisation d'un projet open source

Lors de la fusion on est averti qu’il y a eu des conflits :

```bash
Automatic merge failed; fix conflicts and then commit the result.
```

État de la copie locale, `git status` :

```bash
both modified:   src/main/java/fr/insee/bar/controller/AccueilController.java
```

Le code contient des marqueurs de conflits :

```java
@GetMapping("/")
<<<<<<< HEAD
@ResponseStatus(HttpStatus.MOVED_PERMANENTLY)
=======
@ResponseStatus(HttpStatus.OK)
>>>>>>> origin/develop
```

Modifiez le code pour supprimer les conflits et les marqueurs

Ajoutez les fichiers corrigés dans l’index

Commitez une fois que tout est résolu

%%%

<!-- .slide: data-background-image="images/logo.svg" data-background-size="600px" class="slide" -->

### Choisir une version

Résoudre un conflit en utilisant l’une ou l’autre version

- Globalement :

```bash
git merge <branche> # conflits
git merge --abort

git merge -Xours <branche> # garder notre version pour toutes les lignes en conflit

git merge -Xtheirs <branche> # garder leur version pour toutes les lignes en conflit
```

- Au cas par cas :

```bash
git merge <branche> # conflits

# garder notre version pour les lignes en conflit dans ce fichier :
git checkout --ours fichier_en_conflit.txt

# garder leur version pour les lignes en conflit dans ce fichier :
git checkout --theirs autre_fichier_en_conflit.txt

git add .
git commit
```

%%%

<!-- .slide: data-background-image="images/logo.svg" data-background-size="600px" class="slide" -->

### Annuler une fusion

Pas encore partagée

- le résultat de la fusion n’a pas encore été envoyé vers le dépôt distant
- il suffit de revenir au commit précédent la fusion : `git reset --hard HEAD~`

Déjà partagée

- le résultat de la fusion a déjà été envoyé vers le dépôt distant
- on ne peut pas réécrire l’historique
- on va donc faire un `git revert`
- &rarr; _revert_ = annuler un _commit_ en appliquant le _patch_ inverse

```bash
git revert --mainline 1 HEAD
```

<div class="center">
    <img src="images/undomerge-revert.png" class="boxed-img" width="500px" />
</div>

%%%

<!-- .slide: data-background-image="images/logo.svg" data-background-size="600px" class="slide" -->

### Mieux vaut éviter les conflits que les résoudre

_Commiter_ souvent

- des petits lots de modifications homogènes

Avoir des petits fichiers

- bien découper les classes selon leurs responsabilités

Communiquer avec les autres membres de l’équipe

- dire sur quoi on travaille
- bien prévenir en cas de _refactoring_ important

Mettre à jour sa copie locale régulièrement

- _pull_ ou _rebase_

Protéger sa branche main

%%%
<!-- .slide: data-background-image="images/logo.svg" data-background-size="600px" class="slide" -->
### Exercices

[C'est ici](exercices/exercice-conflits-git.html)
