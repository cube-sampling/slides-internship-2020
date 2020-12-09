<!-- .slide: data-background-image="images/cube.svg" data-background-size="600px" class="chapter" -->

## Application à un service de tirage
Note:
Enfin nous allons étudier un cas plus particulier de nouveau projet pour le stage, cela illustre les problématiques d'utilisation et de conception d'application comme ressource open source.
%%%

<!-- .slide: data-background-image="images/cube.svg" data-background-size="500px" class="slide" -->

### Description du besoin

Pour l'élaboration d'échantillon d'unités primaires, 
l'INSEE a besoin d'une méthode de tirage équilibrée afin d'améliorer la précision des estimateurs d'Horvitz Thompson des totaux. 

Note:
Pour l'élaboration d'échantillon d'unités primaires pour le tirage de premier degré , dans le cadre de plan de sondages spécifiques à certaines enquêtes ménages, <br/>
l'INSEE nécessite, afin d'améliorer la précision des estimateurs d'Horvitz Thompson des totaux, l'utilisation d'une méthode de tirage équilibrée.
L'algorithme du cube est en cela un algorithme spécifié pour la réalisation d'un tel échantillon.

Pour la précision, c'est détaillé par exemple dans le point 7 de cette note : https://core.ac.uk/download/pdf/79426027.pdf
%%%

<!-- .slide: data-background-image="images/cube.svg" data-background-size="500px" class="slide" -->

### Utilisation d'un existant open source

Au niveau INSEE / CRAN, il existe déjà des implémentations de la méthode du cube. La macro <a href="https://www.insee.fr/fr/statistiques/fichier/2021904/documentation_cube_web.pdf" target="_blank">SAS CUBE</a>, ainsi que différents packages R comme <a href="https://www.rdocumentation.org/packages/sampling/versions/2.8/" target="_blank">sampling</a>.
- Création d'un web service indépendant pour le tirage équilibré intégrant un existant. <!-- .element: class="fragment" -->
- Intégration de l'existant par l'utilisation d'outils favorisant l'interopérabilité R/Java. <!-- .element: class="fragment" -->

Une implémentation nouvelle est également envisageable
- Développement natif avec intégrations de solutions mathématiques existantes. <!-- .element: class="fragment" -->

Note:
Méthodes existantes utilisées à l'INSEE : 
- SAS CUBE : https://www.insee.fr/fr/statistiques/fichier/2021904/documentation_cube_web.pdf
- sampling : samplecube https://www.rdocumentation.org/packages/sampling/versions/2.8/topics/samplecube

Une première idée pourrait donc être d'intégrer une de ces solutions au sein d'une api et de l'utiliser comme un service interne a l'application Nautile :
- C'est une approche microservice qui permet, par l'intermédiaire d'interfaces fonctionnelles, de faire cohabiter différents services hétérogènes puisque leurs contrats d'interfaces leurs permettent de toujours répondre et de fonctionner de manière homogène.

Une seconde idée, serait d'utiliser des moteurs favorisant l'interopérabilité entre les languages cibles et existants (R et Java) : Graal VM, Renjin. Pour ainsi intégrer directement a l'intérieur du coeur de métier de l'application Nautile, un module dédié exploitant ces algorithmes.

Troisième idée, intégration d'un matériel existant de jars open sources réalisant le travail sur différents plans : Martingales, Algorithmes de résolutions de systèmes linéaires. Meilleure maintenabilité, mais coût initial / recette plus important car solution non éprouvée et non validée.
%%%

<!-- .slide: data-background-image="images/cube.svg" data-background-size="500px" class="slide" -->

### Accès au projet

Utilisation de modes de packaging standards
<table>
    <tr>
      <td>
        <a href="https://docs.oracle.com/javase/8/docs/technotes/guides/jar/jarGuide.html" target="_blank">
          <img src="images/pngegg.png" style="width: 100px;" />
        </a>
      </td>
            <td>
        <a href="https://www.docker.com/" target="_blank">
          <img src="images/docker-image.png" style="width: 130px;" />
        </a>
      </td>
      <td>
        <a href="https://helm.sh/" target="_blank">
          <img src="https://helm.sh/img/helm.svg" style="width: 90px;" />
        </a>
      </td>
    </tr>
</table>

Note:

L'objectif étant de présenter une librairie et de communiquer par le biais d'une solution intégrée clé en main démo, permettant aux utilisateurs de mieux prendre en main l'applicatif et ainsi augmenter les chances de contribuer.
%%%

<!-- .slide: data-background-image="images/cube.svg" data-background-size="500px" class="slide" -->
### Infrastructure projet

2 types de projets : projet librairies, projets d'intégration. 

Intégrés dans une forge logicielle.


Note:

Enjeux de packaging différents de communication et de modularité.
<br/>
 Un projet d'intégration permettant de rapidement prendre en main la partie modulaire,
  <br/> le module étant le coeur du fonctionnement applicatif.

