# MEP06
Emy LIEUTAUD <br>
N° étudiant : 31818604

## Build local
L'image sera basée sur nginx, un serveur Web open source qui nous permettra d'accéder à notre application Web.<br><br>
Build l'image : 
```docker build -t mep06 .```<br>
Run l'image dans un conteneur : 
```docker run -p 8080:80 mep06```<br><br>
On peut accéder à notre application Web sur [localhost:8080](http://localhost:8080).

## Déploiment de l'application avec Mogenius
Mogenius nous permet de déployer notre application à partir d'un Dockerfile présent dans un repo Git. <br><br>
External hostname : [mep06-prod-mep06-ka22a9.mo2.mogenius.io:80](https://mep06-prod-mep06-ka22a9.mo2.mogenius.io:80)<br><br>
*Le service a été enlevé pour déployer le backend du projet FullStack.*

## Déploiment du back du projet FullStack
ProjetFullStack accessible à l'url suivante : [https://github.com/EmyLIEUTAUD/ProjetFullStack](https://github.com/EmyLIEUTAUD/ProjetFullStack)<br><br>
Sur Mogenius il nous faut créer 2 services : un service à partir du template PostgreSQL pour la base de données, et un autre service à partir du Dockerfile présent dans le repo Git pour lancer le back de l'application. <br><br>
- PostgreSQL possède 4 variables d'environnement : 
  - POSTGRES_PASSWORD : une Key Vault contenant le mot de passe pour se connecter à la base de données
  - POSTGRES_DB : le nom de la base de données 
  - VOLUME-MOUNT : le volume lié à la base de données
  - POSTGRES_USER : le username pour se connecter à la base de données 
<br>
- ProjetFullStack possède 8 variables d'environnement : 
  - SPRING_JPA_SHOW_SQL : égal à true
  - SPRING_DATASOURCE_PASSWORD : une Key Vault contenant le mot de passe pour se connecter à la base de données
  - SPRING_JPA_DATABASE_PLATEFORME : org.hibernate.dialect.PostgreSQLDialect
  - SPRING_LIQUIBASE_ENABLED : égal à false
  - SPRING_DATASOURCE_URL : url pour accéder à la base de données en spécifiant le service PostgreSQL et le nom de la base de données
  - SPRING_DATASOURCE_USERNAME : le nom de la base de données
  - SPRING_JPA_HIBERNATE_DDL_AUTO : égal à create pour recréer la base de données au lancement du conteneur
  - SPRING_MVC_PATHMATCH_MATCHING_STRATEGY : ant_path_matcher
<br>
External hostname pour accéder au back du projet FullStack : [https://projetfullstac-prod-mep06-ka22a9.mo2.mogenius.io:80](https://projetfullstac-prod-mep06-ka22a9.mo2.mogenius.io:80)<br>
On peut voir qu'un centre existe dans la base de données (endpoint /public/centres) : [https://projetfullstac-prod-mep06-ka22a9.mo2.mogenius.io/public/centres](https://projetfullstac-prod-mep06-ka22a9.mo2.mogenius.io/public/centres)
