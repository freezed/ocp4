# OC Pizza - Spécifications fonctionnelles

## Préambule

_La dernière version à jour de ce document est disponible sur [github](https://github.com/freezed/ocp4/blob/master/specification.md)._

_Ce document détaille les spécifications fonctionnelles du projet, pour une présentation plus rapide, voir la [synthèse de présentation](https://github.com/freezed/ocp4/blob/master/presentation.md)._


## Contexte

**OC Pizza** est un jeune groupe de pizzeria en plein essor et spécialisé dans les pizzas livrées ou à emporter. Il compte déjà ~~5 points de vente~~ et prévoit d’en ouvrir au moins ~~3 de plus d’ici la fin de l’année~~. Un des ~~responsables~~ du groupe a pris contact avec vous afin de mettre en place un système informatique, déployé dans ~~toutes ses pizzerias~~ et qui lui permettrait notamment :

- d’être plus efficace dans la ~~gestion des commandes~~, de leur ~~réception~~ à leur ~~livraison~~ en passant par leur ~~préparation~~
- de suivre en temps réel les ~~commandes~~ passées et en ~~préparation~~
- de suivre en temps réel le ~~stock d’ingrédients~~ restants pour savoir quelles ~~pizzas sont encore réalisables~~
- de proposer un site ~~Internet~~ pour que les ~~clients~~ puissent :
    * ~~passer leurs commandes~~, en plus de la ~~prise de commande~~ par ~~téléphone~~ ou ~~sur place~~,
    * ~~payer en ligne~~ leur commande s’ils le souhaitent – sinon, ils ~~paieront directement à la livraison~~
    * ~~modifier ou annuler leur commande~~ tant que celle-ci n’a pas été préparée
- de proposer un aide mémoire aux ~~pizzaiolos~~ indiquant la ~~recette de chaque pizza~~

Le ~~client~~ a déjà fait une petite prospection et les logiciels existants qu’il a pu trouver ne lui conviennent pas.

## Éléments clés

* Lieux
    - 5 points de vente, 3 de plus d’ici la fin de l’année
* Acteurs
    - manager
    - employee
    - buyer
    - client
    - bank
* Point d'entrées
    - comptoir/téléphone
    - internet
* Compte client
    * Création
        - saisie:
            - mail (x2)
            - pass
            - nom/prenom
            - adresse (livraison/facturation)
            - restaurant de préparation préféré
        - envoi mail de conf
        - vérification de l'URL de validation
    * Connection
        - username
        - password
* Commande
    * Création
        - authentification (client internet ou comptoir)
        - choix d'un restaurant de préparation
        - liste de pizza dispo
        - choix de pizza (type/taille/quantité)
        - choix livraison (domicile/comptoir)
        - paiement (CB, espèces, chq)
    * Gestion
        - affiche une commande
        - édite la commande (en préparation/dispo/en livraison/livrée)
* Ingrédients
    * Gestion
        - restaurant
        - ingrédients
        - approvisionnement du stock

---
## Modélisation UML

### Project tree
![Project tree - OC Pizza](https://raw.githubusercontent.com/freezed/ocp4/master/img/0001-uml-global-tree.png)

### Context diagram
![Context diagram - OC Pizza](https://raw.githubusercontent.com/freezed/ocp4/master/img/0002-uml-global-context_diagram.png)

---
### Package diagram
![Package diagram - OC Pizza](https://raw.githubusercontent.com/freezed/ocp4/master/img/0003-uml-global-package_diagram.png)

---
### Package [account]
_Use case diagram_:

![Use case - account](https://raw.githubusercontent.com/freezed/ocp4/master/img/0110-uml-account-use_case_diagram.png)

#### Activity [signIn] : Création d'un client
_Activity diagram_:

![Activity diagram - signIn](https://raw.githubusercontent.com/freezed/ocp4/master/img/0123-uml-account-diagram_activity-sign_in.png)

#### Activity [logInClient] : Connection d'un client
_Activity diagram_:

![Activity diagram - logInClient](https://raw.githubusercontent.com/freezed/ocp4/master/img/0122-uml-account-diagram_activity-log_in_client.png)

#### Activity [addEmployee] : Création d'un salarié
_Activity diagram_:

![Activity diagram - logInEmployee](https://raw.githubusercontent.com/freezed/ocp4/master/img/0125-uml-account-diagram_activity-add_employee.png)

#### Activity [editEmployee] : Modification d'un salarié
_Activity diagram_:

![Activity diagram - addEmployee](https://raw.githubusercontent.com/freezed/ocp4/master/img/0124-uml-account-diagram_activity-edit_employee.png)

#### Activity [logInEmployee] : Connection d'un salarié
_Activity diagram_:

![Activity diagram - editEmployee](https://raw.githubusercontent.com/freezed/ocp4/master/img/0121-uml-account-diagram_activity-log_in_employee.png)

---
### Package [order]

#### Use case [manageOrder] : Gestion des commandes

##### _Use case diagram_
![Use case - manageOrder](https://raw.githubusercontent.com/freezed/ocp4/master/img/0210-uml-order-use_case_diagram.png)

#### Activity [getAvaiablePizzas] : Pizza disponibles
_Activity diagram_:

![Activity diagram - getAvaiablePizzas](https://raw.githubusercontent.com/freezed/ocp4/master/img/0323-uml-ingredient-diagram_activity-get_avaiable_pizza.png)

#### Activity [createOrder] : Création de commande
_Activity diagram_:

![Activity diagram - createOrder](https://raw.githubusercontent.com/freezed/ocp4/master/img/0221-uml-order-diagram_activity-create.png)

#### Use case description [payment]
![Use case description - payment](https://raw.githubusercontent.com/freezed/ocp4/master/img/0291-uml-order-use_case_description-payment_1-2.png)
![Use case description - payment](https://raw.githubusercontent.com/freezed/ocp4/master/img/0291-uml-order-use_case_description-payment_2-2.png)

[_(Lien vers le fichier)_][1]

#### Use case description [creditCard]
![Use case description - creditCard](https://raw.githubusercontent.com/freezed/ocp4/master/img/0292-uml-order-use_case_description-credit_card.png)
[_(Lien vers le fichier)_][2]

#### Use case description [check]
![Use case description - check](https://raw.githubusercontent.com/freezed/ocp4/master/img/0293-uml-order-use_case_description-check.png)
[_(Lien vers le fichier)_][3]

#### Use case description [cash]
![Use case description - cash](https://raw.githubusercontent.com/freezed/ocp4/master/img/0294-uml-order-use_case_description-cash.png)
[_(Lien vers le fichier)_][4]

#### Use case description [select]
![Use case description - select](https://raw.githubusercontent.com/freezed/ocp4/master/img/0295-uml-order-use_case_description-select.png)
[_(Lien vers le fichier)_][5]

#### Use case description [view]
![Use case description - view](https://raw.githubusercontent.com/freezed/ocp4/master/img/0296-uml-order-use_case_description-view.png)
[_(Lien vers le fichier)_][6]

#### State machine diagram [Order] : États d'une commande
_State machine diagram_:

![State machine diagram - order](https://raw.githubusercontent.com/freezed/ocp4/master/img/0230-uml-order-state_diagram.png)

---
### Package [ingredient]

#### Use case [manageIngredient] : Gestion des ingrédients

_Use case diagram_:

![Use case - manageIngredient](https://raw.githubusercontent.com/freezed/ocp4/master/img/0311-uml-ingredient-use_case_diagram.png)

#### Activity [ingredientLoop] : ingredients par pizza
_Activity diagram_:

![Activity diagram - ingredientLoop](https://raw.githubusercontent.com/freezed/ocp4/master/img/0322-uml-ingredient-diagram_activity-loop.png)

#### Activity [ingredientIn] : Ajout d'ingredient
_Activity diagram_:

![Activity diagram - ingredientIn](https://raw.githubusercontent.com/freezed/ocp4/master/img/0324-uml-ingredient-diagram_activity-ingredient_in.png)

#### Activity [ingredientOut] : Mise à jour d'ingrédient
_Activity diagram_:

![Activity diagram - ingredientOut](https://raw.githubusercontent.com/freezed/ocp4/master/img/0325-uml-ingredient-diagram_activity-ingredient_out.png)

---
## Solution technique

Pour une mise en œuvre fiable, efficace et évolutive des besoins clients décrit ci dessus, il est proposé d'utiliser un ensemble de technologies web parmi les plus fiable et au développement très actif.


### [Django framework](https://www.djangoproject.com/start/overview/)

Django est un framework web libre et open-source, écrit en Python facilitant la création de sites Web complexes, reposant sur des bases de données. Django met l'accent sur la ré-utilisabilité et la "pluggabilité" des composants, moins de code, un développement rapide, et le principe DRY.


### [Apache HTTP server](https://httpd.apache.org/)

Le serveur HTTP Apache, communément appelé Apache, est un serveur web multi-plateforme libre et open-source. Il est multi-plateforme.

Il a joué un rôle clé dans la croissance initiale du World Wide Web et est resté le plus populaire depuis avril 1996. En juillet 2016, on estimait qu'il desservait 46 % de tous les sites Web actifs et 43 % des millions de sites Web les plus actifs.

### [MariaDB](https://mariadb.org/)

MariaDB Server est l'un des serveurs de bases de données les plus populaires au monde. Il s'agit d'un remplacement amélioré de MySQL. MariaDB est utilisé parce qu'il est rapide, évolutif et robuste, avec un riche écosystème de moteurs de stockage, de plugins et de nombreux autres outils qui le rendent très polyvalent pour une grande variété de cas d'utilisation. Il fournit une interface SQL pour accéder aux données.
Les principaux utilisateurs sont Wikipedia, WordPress.com et Google.



### [Debian GNU/Linux](https://debian.org)

Debian est une distribution GNU/Linux, lancée en 1993 avec le soutien de la Free Software Foundation. C'est un système d'exploitation d'ordinateur de type Unix, entièrement composé de logiciels libres. Orientée serveurs, elle est réputée pour sa stabilité et sa sécurité.

### [PayPal](https://www.paypal.com/)

PayPal est un service de paiement en ligne qui permet (entre autre) de payer des achats sans avoir à recommuniquer ses coordonnées bancaires, une adresse de courrier électronique et un mot de passe étant suffisants.
Paypal est accepté comme moyen de paiement par plus de 16 millions de commerçants dans le monde. Plus de 203 millions de particuliers se servent de PayPal pour acheter, vendre ou envoyer de l'argent.


[1]: https://github.com/freezed/ocp4/blob/master/0291-uml-order-use_case_description-payment.md "Use case description - payment"
[2]: https://github.com/freezed/ocp4/blob/master/0292-uml-order-use_case_description-credit_card.md "Use case description - creditCard"
[3]: https://github.com/freezed/ocp4/blob/master/0293-uml-order-use_case_description-check.md "Use case description - check"
[4]: https://github.com/freezed/ocp4/blob/master/0294-uml-order-use_case_description-cash.md "Use case description - cash"
[5]: https://github.com/freezed/ocp4/blob/master/0295-uml-order-use_case_description-select.md "Use case description - select"
[6]: https://github.com/freezed/ocp4/blob/master/0296-uml-order-use_case_description-view.md "Use case description - view"
