### Architecture monolithique 

Une **architecture monolithique** est un style d'organisation de logiciels où toutes les fonctionnalités d'une application sont regroupées dans un **seul et même codebase** (base de code) déployé en tant qu'unité unique. Contrairement aux approches distribuées comme les microservices, le monolithe implique un déploiement unifié, ce qui en fait une architecture courante pour les petites et moyennes applications ou pour des projets qui débutent.

### **Exemple d'une architecture monolithique :**
une application web traditionnelle de gestion de produits :

```
src/
│
├── controllers/
│   ├── UsersController.ts
│   ├── ProductsController.ts
│   └── OrdersController.ts
│
├── services/
│   ├── UserService.ts
│   ├── ProductService.ts
│   └── OrderService.ts
│
├── models/
│   ├── UserModel.ts
│   ├── ProductModel.ts
│   └── OrderModel.ts
│
├── views/
│   ├── user.ejs
│   ├── product.ejs
│   └── order.ejs
│
└── database/
    └── databaseConnection.ts
```

Dans cet exemple :
- Les **contrôleurs** gèrent les requêtes HTTP.
- Les **services** contiennent la logique métier.
- Les **modèles** représentent les structures de données et la logique liée aux données.
- Les **vues** définissent l'interface utilisateur.
- Le tout est regroupé dans une seule application.

### **Inconvénients de l'Architecture Monolithique :**
1. **Scalabilité limitée** : Difficile de faire évoluer uniquement certaines parties de l'application. Si une partie a besoin de plus de ressources, il faut faire évoluer l'ensemble du monolithe.
2. **Maintenance difficile** : Au fur et à mesure que le code grandit, il devient complexe, difficile à maintenir et à comprendre pour de nouvelles équipes.
3. **Déploiement risqué** : Une petite modification nécessite souvent le déploiement de l'ensemble de l'application, augmentant les risques d'erreurs.
4. **Flexibilité réduite** : Le découplage des fonctionnalités est faible, ce qui limite la flexibilité en termes de changements ou de mises à jour.
5. **Impact des défaillances** : Une erreur dans une partie de l'application peut affecter tout le système.

