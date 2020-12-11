<!-- .slide: data-background-image="images/risk.svg" data-background-size="700px" class="chapter" -->

## Risques et avantages liés à l'open source
Note:
Etude des risques et des avantages du passage a l'open source
%%%


<!-- .slide: data-background-image="images/risk.svg" data-background-size="600px" class="slide" -->

### Les risques de sécurité

- Code exposé et exploitation des failles applicatives<!-- .element: class="fragment" -->
- Adhérences fortes aux environnements internes<!-- .element: class="fragment" -->
- Problématiques de gestion de version (ex: Git Ransomware Attack)<!-- .element: class="fragment" -->

Note:

Code exposé : 

- injection sql et accès aux informations sur les dépendances (failles de sécurité)

Adhérences fortes: 
- mots de passes et liens. Problématiques de gestion de version.

Gestion de version : 
- Reverse engineering du code source

voir https://medium.com/swlh/hacking-git-directories-e0e60fa79a36
%%%


<!-- .slide: data-background-image="images/risk.svg" data-background-size="600px" class="slide" -->

### Les risques pour l'entreprise

- Démystification du travail, erreurs, image de l'entreprise<!-- .element: class="fragment" -->
- Compétences spécifiques pour les développeurs<!-- .element: class="fragment" -->
- Problématiques juridiques : droit des données<!-- .element: class="fragment" -->

Note:
Démystification du travail :

Risque "médiatique" en cas de bug, gestion de crises, secret statistique.
<br />
Problématiques compétences développeur: 

Le travail OS n'est pas généralisé a l'insee, il faut donc envisager la conduite du changement de ce niveau là puisse qu'il y a tout une gestion de projet associée, des risques à connaître.  

<br/>
Problématiques juridiques : 

droit des données
Exposition des données à des serveurs externes, risques pour la structure.

<br/>

Bonus : Problématique contribution admin publique 

La fonction publique utilise beaucoup de solutions open source, mais assure un suivi dans sa gestion des ressources du parc des développeurs. De ce fait, la contribution opensource est imputée à des organismes internes, il faut donc s'assurer de la dimension rh du travail et intégrer les MOA a la dynamique OS.


%%%


<!-- .slide: data-background-image="images/risk.svg" data-background-size="600px" class="slide" -->

### Avantages internes au produit

- Contribution externes au projet interne<!-- .element: class="fragment" -->
- Projet plus accessible et donc plus fiable <!-- .element: class="fragment" -->
- Réutilisation du code interne dans d'autres projets, découpage en sous projets<!-- .element: class="fragment" -->

Note:
Contribution externes au projet interne

- Gain de contributeurs, image de l'entreprise

Projet plus accessible et donc plus résistant aux erreurs 

- plus de visibilité = plus de déclaration de bugs métiers et techniques

Réutilisation du code interne dans d'autres projets, découpage en sous projets : 

- Construction en microservice, adhérence actuelle aux données métier, schéma dynamique
- Découpage application en partie tirage, définition, vtl ... Réutilisabilité

%%%


<!-- .slide: data-background-image="images/risk.svg" data-background-size="600px" class="slide" -->

### Avantages externes
- Présentation des algorithmes permettant la réalisation des chiffres<!-- .element: class="fragment" -->
- Utilisation de solutions déjà maintenues et standards<!-- .element: class="fragment" -->
- Beaucoup de solutions ont fait leurs preuves<!-- .element: class="fragment" -->

Note:
Présentation des algorithmes permettant la réalisation des chiffres :
- Respect des lois, devoir de reproductibilité des chiffres

Utilisation de solutions déjà maintenues et standards:
- Coûts moins importants et qualité.



