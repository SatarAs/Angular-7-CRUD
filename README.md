# Tutoriel Angular 7 : CRUD sur application web

Je ne voyais pas comment faire quelque chose qui serait simple pour toi de vérifier.
Je place donc toutes les explications ici.


## Architecture

`api.service.ts` Il permet de connecter l'application au serveur Express via une API.

`app.component.ts` Ce fichier est le composant principal, il comporte toute la logique de notre application.

`app.module.ts` Ce fichier permet d'importer et de déclarer les composants dans notre application.

`app.routing.module.ts` Il permet de définir les routes accessibles depuis notre application.

`product.ts` Ce fichier est lié à notre objet `product` qui contient le typage de ces propriétés. 

`product-add` Permet l'ajout de produit 

`product-detail` Permet l'affichage d'un produit ainsi que la suppression de ce même produit

`product-edit` Permet l'édition d'un produit

`products` Permet l'affichage de la liste des produits


## Détails du code

- `product-add.component.ts`

Nous déclarons le groupe de formulaire pour le produit ainsi que les variables requises.
Le `constructor` ici nous permet d'injecter les dépendances nécessaires ( Api, Router et FormBuilder)

Contrairement au `constructor`, le `ngOnInit` permet d'initialiser le `component`.
Ici, il initie le formulaire d'ajout du produit avec les différentes propriétés.

A la soumission du formulaire, une réponse sera envoyé avec un déclencheur spécifié.

#

- `product-detail.component.ts`

Déclaration des variables définis depuis le `product.ts` afin d'en extraire les données depuis l'API.

Le `ngOnInit` dans le détail d'un produit, permet d'appeler la fonction `getProductDetails` au lancement du composant.

La fonction `getProductDetails` permet de récupérer les données du produit depuis l'API.

La fonction `deleteProduct` permet de supprimer un produit depuis l'API.

#

- `product-edit.component.ts`

Le `ngOnInit` ici, permet la validation quand le composant est lancer.

Le `getProduct` permet de récupérer les données d'un produit depuis l'api.

Ici, le `onFormSubmit` permet comme dans le `product-add.ts` de valider l'envoi du formulaire grâce à un déclencheur.

#

- `products.component.ts`

La propriété `displayedColumns` permet d'afficher dans un tableau les champs `prod_name`, `prod_price`

Le `constructor` permet l'appel de l'API

Le `ngOnInit` permet de récupérer la liste des produits depuis l'API.
