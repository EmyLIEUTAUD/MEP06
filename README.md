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
