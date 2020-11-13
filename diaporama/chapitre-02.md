<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px" class="chapter" -->

## Risques et avantages liés à l'open source

%%%

<!-- .slide: data-background-image="images/git-book.png" data-background-size="600px" class="slide" -->

### Les risques de sécurité

- Code exposé et exploitation des failles applicatives
- Adhérences fortes aux environnements internes
- Problématiques de gestion de version (ex: Git Ransomware Attack)

Note:
Code exposé : injection sql et accès aux informations sur les dépendances (failles de sécurité)
Adhérences fortes: mots de passes et liens. Problématiques de gestion de version.
Gestion de version : voir https://medium.com/swlh/hacking-git-directories-e0e60fa79a36
%%%

<!-- .slide: data-background-image="images/git-book.png" data-background-size="600px" class="slide" -->

### Les risques pour l'entreprise

- Démystification du travail, erreurs 
- Exposition de la responsabilité aux développeurs
- Problématiques de la contribution interne à la fonction publique

Note:

Problématique contribution fonction publique : 
La fonction publique utilise beaucoup de solutions open source, mais assure un suivi dans sa gestion des ressources du parc des développeurs. De ce fait, la contribution opensource est imputée à des organismes internes en quête de ressource et donc, elle n'est par nature pas encouragée par les responsables hiérarchiques métiers.
%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px"  class="slide" -->

### Système de gestion de versions

Il permet de :

- retrouver la dernière modification qui a pu introduire un bug
- revenir à une version spécifique
- revenir à une version antérieure d’un fichier spécifique

De plus, on peut en général :

- partager ses modifications et récupérer celles des autres

Exemple de gestionnaires de version :
- git
- SVN

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px"  class="slide" -->

### Forges

Une forge propose un système de gestion des versions (Git, SVN) et d'autres outils pour faciliter la collaboration (interface utilisateur, issues, wiki...).

Des exemples :
- Gforge : compatible avec Git et SVN (l'instance GForge Insee ferme au 1er trimestre 2021)
- Gitlab : 
    - l'instance GitLab de l'Insee : https://gitlab.insee.fr/explore
    - l'instance "officielle" : https://gitlab.com/
- [Adulact](https://adullact.org/)
- [GitHub](https://github.com/InseeFr)

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px"  class="slide" -->

### Différence entre Git et SVN

Il existe différents gestionnaires de version qui peuvent être basés sur différents modèles :

- **Modèle centralisé** : un serveur central contrôle toute la base de code du logiciel (ex : SVN)
- **Modèle distribué** : toutes les machines ont accès à la base de code, pas besoin de passer par un serveur central (ex : **Git**)

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px"  class="slide" -->

### Avantages du modèle distribué

**Avantages**

- Multiplicité des sources donc moins de risque de perte du code
- Travail en local possible et transparent par rapport au fonctionnement distant

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px"  class="slide" -->

### Pourquoi a-t-on choisi git ?

- C'est un standard
- Rapidité d'exécution
- Travail en mode déconnecté
- Utilisation documentée

%%%

<!-- .slide: data-background-image="images/logo-git.png" data-background-size="600px"  class="slide" -->

[Installation de Git](.\exercices\exercice_1-installation-git.html)