<!-- .slide: data-background-image="images/nautilus.svg" data-background-size="900px" class="chapter" -->

## Application au projet Nautile

%%%

<!-- .slide: data-background-image="images/nautilus.svg" data-background-size="600px" class="slide" -->
### Contexte
L'application NAUTILE est une application de tirage d'échantillons pour les enquêtes ménages.
L'enjeu ici était l'ouverture du code pour la réalisation d'un batch en externe dans le cadre d'une prestation

%%%


<!-- .slide: data-background-image="images/nautilus.svg" data-background-size="600px" class="slide" -->
### Anonymisation et génération des données
- Anonymisation des données : données réelles dans les jeux de test
- Génération de jeux de tests pour des environnements ouverts

Note:
Le premier permet le masquage :
Solution open source pour l'accès aux données anonymisées dans un cluster interne.
PB : cluster externe, les données ne nous appartiennent plus et donc risque.

Second: 
generatedata :
Solution Open source de génération de données mysql intégrable via docker et helm.
PB : solution opensource mais pas encore trop maintenue, pas de chart officiel et du coup intégration maison..

Troisième:
Solution finalement retenue
Intégration en local, génération par script pour la simplicité et les besoins liés a l'urgence.


<table>
            <tr>
              <td>
                <a href="https://postgresql-anonymizer.readthedocs.io/en/stable/" target="_blank">
                  <img src="https://assets.gitlab-static.net/uploads/-/system/project/avatar/7709206/carre.png?width=64" style="width: 70px;" />
                </a>
              </td>
              <td>
                <a href="https://www.json-generator.com/" target="_blank">
                  <img src="images/js.png" style="width: 200px;" />
                </a>
              </td>
              <td>
                <a href="https://github.com/benkeen/generatedata" target="_blank">
                  <img src="images/generatedData.png" style="width: 120px;" />
                </a>
              </td>
             <td>
                <a href="https://www.techonthenet.com/postgresql/functions/random.php" target="_blank">
                  <img src="https://www.postgresql.org/media/img/about/press/elephant.png" style="width: 80px;" />
                </a>
              </td>
            </tr>
</table>

Bilan: 
Il y a un réel besoin de développeur de ce côté.

%%%

<!-- .slide: data-background-image="images/nautilus.svg" data-background-size="600px" class="slide" -->

### Modules INSEE et injection de dépendances (Maven)

Dans le cas de Nautile, il a été question de modulariser la partie web service rundeck de l'application, qui est adhérente a un projet interne, le Service de Soumission des Tâches.
<a href="https://maven.apache.org/guides/introduction/introduction-to-the-pom.html" target="_blank">
```xml:
<dependency>
                <groupId>fr.insee</groupId>
                <artifactId>nautile-client</artifactId>
                <version>${project.parent.version}</version>
                <type>jar</type>
                <scope>provided</scope>
</dependency>
```
</a>

Sortie de la partie adhérente du code dans un module a part: <br/>
nautile-client, disponible dans l'environnement cible par le scope provided


Note:
Illustration niveau maven
%%%
<!-- .slide: data-background-image="images/nautilus.svg" data-background-size="600px" class="slide" -->
### Modules INSEE et injection de dépendances (Spring boot)
Spring permet de définir un contexte initialisé au lancement de l'application, pour ensuite injecter a chaque besoin, le composant déjà instancié.
<a href="https://docs.spring.io/spring-boot/docs/current/api/org/springframework/boot/autoconfigure/condition/ConditionalOnProperty.html" target="_blank">

```java
@Component
@ConditionalOnProperty(value = "basic-client.enabled",havingValue = "false")
@Primary
public class SstBatchClient implements BatchClient {
``` 
</a>

On injecte ensuite un composant implémentant l'interface quand on en a besoin.
<a href="https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/beans/factory/annotation/Autowired.html" target="_blank">

```java
private BatchClient batchClient;
@Autowired
public void setBatchClient(BatchClient batchClient){
```

</a>

Note:
Illustration spring boot : inversion de contrôle
%%%

<!-- .slide: data-background-image="images/nautilus.svg" data-background-size="600px" class="slide" -->
### Versionning de base de données

Nautile est une application adhérente a un lot de données millésimées, la base FIDELI. <br/>

Intégration d'un outil de versionning de base de données dans le code source

<table>
            <tr>
              <td>
                <a href="https://www.liquibase.org/" target="_blank">
                  <img src="https://www.liquibase.org/wp-content/themes/liquibase/assets/img/cta-icon-org.svg" style="width: 70px;" />
                </a>
              </td>
              <td>
                <a href="https://github.com/flyway/flyway" target="_blank">
                  <img src="https://flywaydb.org/assets/logo/flyway-logo-tm.png" style="width: 120px;" />
                </a>
              </td>
            </tr>
</table>


Note:
Afin d'abstraire la version de l'application et la version des données, il a été décidé de gérer un modèle dynamique 
et de versionner dans le code source, la base de données. Ainsi peut importe l'environnement, la base étant adhérente au code.
Ainsi cela réduit la place de l'environnement dans le déploiement, la partie versionning de base n'étant plus adhérente a l'environnement lui même. 
=> Montées de versions assurées.
%%%

<!-- .slide: data-background-image="images/nautilus.svg" data-background-size="600px" class="slide" -->
### Historique existant
A l'origine, le dépôt de code Nautile était également utilisé pour de la documentation et du stockage de données. Ainsi, pour sortir le code, un travail de <a href="https://rtyley.github.io/bfg-repo-cleaner/" target="_blank">nettoyage</a> a été réalisé sur le dépot git.


Note:
Les scripts de suppression sont disponibles <a href="static/suppression-script.md" target="_blank">ici</a>
