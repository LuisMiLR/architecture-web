# DDD 

L'architecture **DDD** (*Domain-Driven Design*, ou conception pilotée par le domaine) est une approche de développement logiciel centrée sur le cœur métier de l'application et les règles qui le gouvernent. Elle est particulièrement adaptée pour des systèmes complexes et cherche à aligner étroitement les besoins métier avec le code technique.


---

### **1. Principes de base**
- **Focus sur le domaine** : Le domaine métier (les règles, concepts et processus propres à l'activité de l'entreprise) est au cœur de la conception.
- **Collaboration étroite avec les experts métier** : Les développeurs collaborent directement avec les experts métier pour comprendre et modéliser le domaine.
- **Langage ubiquitaire** (*Ubiquitous Language*) : Un langage commun (vocabulaire) est défini et utilisé à la fois dans le code et dans les discussions métier pour réduire les ambiguïtés.

---

### **2. Architecture DDD : Les couches principales**
L'architecture DDD est souvent implémentée en suivant une structure en couches. Voici les principales couches :

#### **A. Couche de Domaine**
- **Contenu** :
  - Contient la logique métier principale et les concepts clés (agrégats, entités, objets de valeur, services métier).
  - N'a pas de dépendance sur les autres couches.
- **Responsabilité** :
  - Modéliser et gérer les règles métier et les invariants.
  - Exemple : Une entité `Order` peut vérifier qu'une commande ne peut pas être validée si elle n'a pas de produits.
- **Principaux composants** :
  1. **Entités (Entities)** :
     - Objets avec une identité unique persistante.
     - Exemple : Un utilisateur, une commande.
  2. **Objets de valeur (Value Objects)** :
     - Objets sans identité unique mais définis par leurs attributs.
     - Exemple : Une adresse (ville, rue, code postal).
  3. **Agrégats (Aggregates)** :
     - Groupes d’entités et d’objets de valeur qui sont traités comme une unité logique.
     - Exemple : Une commande (agrégat) contient plusieurs lignes de commande (entités).
  4. **Domain Services** :
     - Services qui encapsulent une logique métier complexe ne relevant pas d’une seule entité ou agrégat.

#### **B. Couche d'Application**
- **Contenu** :
  - Contient la logique de coordination (orchestration).
  - Utilise les services de domaine pour exécuter les cas d’utilisation.
- **Responsabilité** :
  - Ne contient pas de logique métier elle-même.
  - Gère les flux de données entre les couches (par exemple, convertit les DTOs en entités).
  - Exemple : Un service d'application `CreateOrderService` coordonne la création d’une commande en appelant les entités et services nécessaires.

#### **C. Couche d'Infrastructure**
- **Contenu** :
  - Fournit les implémentations techniques pour les interfaces définies dans le domaine et l'application.
  - Exemple : Repositories, systèmes de stockage, bibliothèques externes.
- **Responsabilité** :
  - Gérer l'accès à la base de données, les services externes, les événements, etc.
  - Exemple : Un `OrderRepository` pour sauvegarder et récupérer des commandes.

#### **D. Couche de Présentation (ou Interface utilisateur)**
- **Contenu** :
  - Contient l'interface utilisateur et l'interaction avec l’utilisateur final.
- **Responsabilité** :
  - Interagir avec la couche application pour afficher les données ou transmettre les actions de l'utilisateur.
  - Exemple : Une API REST ou une interface web.

---

### **3. Concepts avancés de DDD**

#### **A. Bounded Context (Contexte délimité)**
- Un système complexe est divisé en contextes délimités, chacun représentant une sous-partie du domaine avec ses propres modèles et règles.
- Exemple : Dans une application e-commerce, les contextes délimités peuvent inclure :
  - **Gestion des commandes**
  - **Gestion des produits**
  - **Gestion des clients**

#### **B. Contexte partagé**
- Les différents contextes délimités interagissent via des interfaces bien définies, comme des API ou des événements.
- Exemple : Lorsqu'une commande est validée, un événement peut être envoyé pour mettre à jour le stock dans le contexte des produits.

#### **C. Domain Events**
- Des événements représentant des changements dans le domaine.
- Exemple : `OrderCreated`, `ProductOutOfStock`.

---

### **4. Avantages de DDD**
- **Modélisation précise du métier** : Le code reflète exactement les besoins métier.
- **Scalabilité organisationnelle** : Les équipes peuvent travailler sur des contextes délimités indépendants.
- **Réduction de la dette technique** : En séparant la logique métier de l'infrastructure.

---

### **5. Inconvénients**
- **Complexité initiale** : L’apprentissage de DDD demande du temps et des efforts.
- **Risque de sur-ingénierie** : Mal utilisé, DDD peut introduire une complexité inutile pour des systèmes simples.

---

### **6. Quand utiliser DDD ?**
- Lorsque le domaine métier est complexe.
- Lorsqu'il y a une forte collaboration entre développeurs et experts métier.
- Lorsque le projet nécessite une évolutivité et une maintenance à long terme.

---

Si tu veux un exemple concret ou une implémentation en code, je peux te guider davantage selon ton projet ou tes outils préférés. 😊