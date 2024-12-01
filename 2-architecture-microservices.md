### Architecture en microservices

Une architecture en **microservices** est principalement de type **vertical**, bien qu'elle puisse avoir des aspects horizontaux dans la façon dont les microservices interagissent entre eux.

### **Pourquoi l'architecture microservices est-elle considérée comme verticale ?**
En microservices, chaque service représente généralement une fonctionnalité ou un domaine métier spécifique et est **autonome**. Cela signifie que chaque microservice contient **toutes les couches nécessaires** pour son propre fonctionnement, y compris l'interface utilisateur, la logique métier, et l'accès aux données. Cela correspond à une organisation verticale où chaque microservice est comme un module indépendant gérant sa propre partie du système.

#### **Caractéristiques d'une architecture en microservices :**
1. **Modularité forte** : Chaque microservice est un module distinct, dédié à une fonctionnalité ou à un domaine métier spécifique.
2. **Isolation complète** : Les microservices sont indépendants les uns des autres. Chaque microservice possède ses propres bases de données, ses services et sa logique métier.
3. **Déploiement indépendant** : Chaque microservice peut être déployé, mis à jour ou remplacé sans affecter les autres services, ce qui permet une grande agilité et scalabilité.
4. **Communication par API** : Les microservices communiquent entre eux via des API (généralement REST ou GraphQL) ou des messages (avec des systèmes de file d'attente comme Kafka ou RabbitMQ).

#### **Exemple d'organisation en microservices :**
une application e-commerce :

- **User Service** : Gère les utilisateurs, l'authentification, et l'autorisation.
- **Product Service** : Gère les produits, les catégories, et les inventaires.
- **Order Service** : Gère les commandes, les paiements, et les factures.
- **Shipping Service** : Gère les expéditions, les livraisons, et les retours.

Chaque service a son propre **dépôt de code**, sa **base de données** et son **pipeline de déploiement**.

### **Aspect Horizontal en Microservices :**
Bien que les microservices soient majoritairement considérés comme verticaux, ils incluent aussi des éléments d'**architecture horizontale** :

- **Services transversaux** : Parfois, certaines fonctionnalités partagées (comme l'authentification ou la journalisation) sont gérées par des services communs appelés "cross-cutting concerns" ou "services transversaux".
- **Observabilité** : La surveillance, la gestion des logs et les métriques peuvent être centralisées, ce qui amène un aspect horizontal.
- **Réseau de communication** : Les microservices utilisent des passerelles API, des systèmes de messages ou des bus de services pour la communication, ce qui introduit une couche horizontale dans l'architecture.

### **Comparaison avec Monolithes :**
- **Monolithe** : Organisé en couches horizontales (frontend, backend, base de données) où toutes les fonctionnalités sont regroupées dans un seul projet.
- **Microservices** : Découpé verticalement par fonctionnalités, chaque service étant autonome et indépendant.

### **Avantages de l'Architecture Microservices :**
- **Scalabilité** : On peut faire évoluer uniquement les services nécessitant plus de ressources.
- **Agilité** : Les équipes peuvent travailler sur des services indépendants sans se bloquer les unes les autres.
- **Résilience** : Une panne dans un service n'affecte pas forcément l'ensemble du système.

### **Inconvénients :**
- **Complexité** : La gestion de nombreux services, des communications entre eux, et la surveillance globale du système augmentent la complexité.
- **Déploiement** : La coordination du déploiement de plusieurs services nécessite une infrastructure DevOps solide.

### Conclusion :
L'architecture en microservices est avant tout verticale, avec des éléments horizontaux pour les services et fonctionnalités transversales. Elle permet de structurer les applications en fonction de domaines métiers, offrant ainsi une grande flexibilité et scalabilité pour les applications modernes.