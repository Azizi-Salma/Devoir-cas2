Devoir Module JEE – Architecture Microservices avec Spring Cloud

Étudiante: Salma Azizi  
Année : 5ᵉ année IIR11 
Module : Java Entreprise Edition (JEE)

---
##  Structure du projet
Devoir-cas2/
├── config-server/ # Spring Cloud Config Server (port 8888)
├── eureka-server/ # Service Discovery avec Eureka (port 8761)
├── api-gateway/ # API Gateway (Spring Cloud Gateway, port 8080)
├── microservice-commandes/ # CRUD Commandes + santé personnalisée (port 8082)
├── microservice-produit/ # CRUD Produits (port 8081)
└── config-repo/ # Dépôt Git local des configurations
## Pré-requis
- Java 11 (ou 17 si tu veux adapter)
- Maven
- Git (pour le repo config local)
- IntelliJ IDEA

## Préparation
1. Cloner le dépôt avec les 5 dossiers (ou copier les dossiers fournis).
2. Dans `config-repo/`, initialiser git:
   ```bash
   cd config-repo
   git init
   git add .
   git commit -m "initial config"

## Fonctionnalités clés
1. Spring Cloud Config : configurations centralisées dans config-repo/
2. Service Discovery : microservices enregistrés sur Eureka
3. API Gateway : point d’entrée unique avec routage intelligent
4. Load Balancing : transparent via Spring Cloud LoadBalancer
5. Santé personnalisée : statut "DOWN" si aucune commande, "UP" sinon
6. OpenAPI/Swagger : documentation interactive des APIs
7. Refresh dynamique : modifie config-repo/*.properties → POST /actuator/refresh

## Endpoints utiles
API Gateway – Commandes : http://localhost:8080/commandes
Eureka Dashboard: http://localhost:8761
Swagger UI – Commandes: http://localhost:8082/swagger-ui/index.html
Swagger UI – Produits: http://localhost:8081/swagger-ui/index.html
H2 Console – Commandes: http://localhost:8082/h2-console
H2 Console – Produits: http://localhost:8081/h2-console
Actuator Health – Commandes:http://localhost:8082/actuator/health
Config Server – Test: http://localhost:8888/microservice-commandes/default
