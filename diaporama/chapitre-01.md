<!-- .slide: data-background-image="images/literature.svg" data-background-size="750px" class="chapter" -->

## Open source : concepts
%%%

<!-- .slide: data-background-image="images/literature.svg" data-background-size="600px" class="slide" -->

<h3><a href="https://opensource.org/osd" style=color:inherit target=_blank> Définition</a></h3>

Est dit open source un logiciel :
- avec un code source accessible <!-- .element: class="fragment" -->
- à libre redistribution <!-- .element: class="fragment" -->
- possédant une définition du devenir du code partagé <!-- .element: class="fragment" -->



Note:

Des questions émergent donc : 
A qui appartient le code ? 
- Par défaut, il appartient a la personne qui l'a écrit ou par extension a la société qui l'engage 

Le code est il accessible a tous, peut on créer des solutions basées sur ce code et les revendre ? 
- Tout est possible.

Quels sont les risques qui interviennent avec l'ouverture d'un code source ? 
- Les enjeux sont multiples nous en parlerons par la suite.

%%%


<!-- .slide: data-background-image="images/literature.svg" data-background-size="600px" class="slide" -->
### Les licences
Il est donc nécessaire de définir un tel contrat pour une application. <br/> 
Il se trouve de manière classique dans un projet dans le fichier <a href="https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/licensing-a-repository" target=_blank>LICENSE</a>

On retrouve ici différents concepts: 
- termes de modification et exploitabilité <!-- .element: class="fragment" -->
- définition de restrictions parent/fils   <!-- .element: class="fragment" -->
Note:

Termes modification exploitabilité : 
Définition des droits a la modification qui font de cette license une license opensource. Permettant du coup aux utilisateurs de modifier le code pour une utilisation personnalisée.

Restriction : 
Redistribution seulement selon la même license, copyleft, respect de l'origine du produit.

Le code est il accessible a tous, peut on créer des solutions basées sur ce code et les revendre ? 
Par défaut il est sous license copyright, interdit d'accès et d'utilisation.
Sinon : 
- Tout est possible.

Quels sont les risques qui interviennent avec l'ouverture d'un code source ? 
- Les enjeux sont multiples nous en parlerons par la suite.

%%%




<!-- .slide: data-background-image="images/literature.svg" data-background-size="600px" class="slide" -->

### Contribution

Une documentation de l'application propre 

Un fonctionnement propre, pour la gestion de version et la contribution : le <a href="https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow" target=_blank>Gitflow</a> et les pull requests.

Un fichier d'explication pour la contribution, le <a href="https://gist.github.com/PurpleBooth/b24679402957c63ec426#file-good-contributing-md-template-md" target=_blank>CONTRIBUTING.md</a>


Note:
Gitflow: 
Le versionning actuel est majoritairement effectué sous Git, un gestionnaire de version libre et très maintenu. De ce versionning différents usages ont émergé et parmi ceux ci, le gitflow avec l'introduction des pull requests. Le principe d'une pull request est de pouvoir contribuer en récupérant un dépot de code (fork) et en effectuant les développements dessus pour pouvoir proposer une fonctionnalité ou une correction de bug.
Contributing:
Fichier précise comment contribuer, quel formattage appliquer, qui contacter, quels sont les développeurs internes au projet qui est très souvent intégré aux projets opensource gratuits, permettant un accès simplifié des utilisateurs externes