![Diagramme](Infrastructure-Design.png)

#  Web infrastructure design


## Introduction :
Concevoir une infrastructure web minimale qui permet à un utilisateur d’accéder à un site comme www.foobar.com MAIS, un point de défaillance unique (SPOF), une indisponibilité pendant les maintenances, et aucune capacité à monter en charge. Voyons plus loins maintenant, passons sur des composants séparés et équilibrage de charge et surtout une infrastructure sécurisée et surveillée .
![Diagramme](bandeau.png)


## Infrastructure :


1. *__Simple web stack__*
" Un petit web simple convient aux petits projets ou aux environnements de test. "

2. *__Distributed web infrastructure__*
" Une infrastructure web distribuée, répartit les rôles sur plusieurs serveurs pour améliorer la fiabilité et les performances. "

3. *__Secured and monitored web infrastructure__*
 " Une infrastructure web sécurisée et surveillée protège les données et garantit la disponibilité du service "

4. *__Scale up__*
" Garantir une disponibilité continue en répartissant intelligemment le trafic et en doublant les points de redondance pour éviter toute interruption. "

![Diagramme](bandeau.png)

## 1) Simple web stack

1. L'utilisateur veut accéder à un site web, par exemple, www.foobar.com.
2. Le DNS prend la résolution du nom de domaine (comme www.foobar.com) en une adresse IP (par exemple, 8.8.8.8)
3. Nginx agit comme le serveur web qui gère la requête de l'utilisateur.
4. Le serveur d'application est responsable de l'exécution de la logique métier.
5. La base de données stocke toutes les informations nécessaires à l'application

![Diagramme](0-simple_web_stack.png)
![Diagramme](bandeau.png)
## 2) Distributed web infrastructure
 le DNS résout le nom de domaine et redirige la demande vers un load balancer. Ce dernier répartit la charge entre plusieurs serveurs web. Les serveurs web, à leur tour, traitent les requêtes et les envoient aux serveurs d'application pour une logique métier.(trop de traffic)


1. IDEM
2. IDEM
3. Le Load Balancer reçoit la requête et la redirige vers l’un des serveurs disponibles dans un cluster de serveurs web.
4. IDEM
5. IDEM
6. IDEM

![Diagramme](1-distributed_web_infrastructure.png)
![Diagramme](bandeau.png)
## 3) Secured and monitored web infrastructure

1. Certificat SSL : Le trafic est chiffré à l’aide d’un certificat SSL
2. 1st Firewall :  il bloque tout accès non autorisé et protège le réseau contre des attaques
3. 2nd firwall : restreint l'accès aux ressources internes sensibles.
4. 3rd firwall :  garantit que seules les requêtes autorisées sont transmises des serveurs web aux serveurs d'application. 
![Diagramme](2-secured_and_monitored_web_infrastructure.png)
![Diagramme](bandeau.png)
## 4) Scale up

1. L'utilisateur veut accéder à un site web, par exemple, www.foobar.com.
2. Le DNS prend la résolution du nom de domaine (comme www.foobar.com) en une adresse IP (par exemple, 8.8.8.8)
3. Le Load Balancer reçoit la requête et la redirige vers le serveurs(Nginx) .

3.1 En __mode cluster__ , si un load balancer tombe en panne, le deuxième prend automatiquement le relais 
5. Nginx agit comme le serveur web qui gère la requête de l'utilisateur.
6. Le serveur d'application est responsable de l'exécution de la logique métier.
7. La base de données stocke toutes les informations nécessaires à l'application

![Diagramme](3-scale_up.png)
Ajout d'un load balancer pour rediriger le trafic en cas de défaillance du premier.
![Diagramme](bandeau.png)


## Conclusion : 

Pour une infrastructure web efficace, il est crucial d'avoir un bon équilibre entre sécurité, disponibilité, performance, évolutivité et surveillance.

