# OC Pizza - Présentation

_Ce document est une synthèse de présentation du projet, pour plus de détails, vous pourrez suivre les liens proposé ou plus simplement consulter le [document de spécification fonctionnelles](https://github.com/freezed/ocp4/blob/master/specifications.md)._

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

* [Activity diagram - signIn](https://raw.githubusercontent.com/freezed/ocp4/master/img/0123-uml-account-diagram_activity-sign_in.png)
* [Activity diagram - logInClient](https://raw.githubusercontent.com/freezed/ocp4/master/img/0122-uml-account-diagram_activity-log_in_client.png)
* [Activity diagram - logInEmployee](https://raw.githubusercontent.com/freezed/ocp4/master/img/0125-uml-account-diagram_activity-add_employee.png)
* [Activity diagram - addEmployee](https://raw.githubusercontent.com/freezed/ocp4/master/img/0124-uml-account-diagram_activity-edit_employee.png)
* [Activity diagram - editEmployee](https://raw.githubusercontent.com/freezed/ocp4/master/img/0121-uml-account-diagram_activity-log_in_employee.png)

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

* [Use case description - payment][1]
* [Use case description - creditCard][2]
* [Use case description - check][3]
* [Use case description - cash][4]
* [Use case description - select][5]
* [Use case description - view][6]

#### State machine diagram [Order] : États d'une commande
_State machine diagram_:

![State machine diagram - order](https://raw.githubusercontent.com/freezed/ocp4/master/img/0230-uml-order-state_diagram.png)

---
### Package [ingredient]

#### Use case [manageIngredient] : Gestion des ingrédients

_Use case diagram_:

![Use case - manageIngredient](https://raw.githubusercontent.com/freezed/ocp4/master/img/0311-uml-ingredient-use_case_diagram.png)

* [Activity diagram - ingredientIn](https://raw.githubusercontent.com/freezed/ocp4/master/img/0324-uml-ingredient-diagram_activity-ingredient_in.png)
* [Activity diagram - ingredientOut](https://raw.githubusercontent.com/freezed/ocp4/master/img/0325-uml-ingredient-diagram_activity-ingredient_out.png)
* [Activity diagram - ingredientLoop](https://raw.githubusercontent.com/freezed/ocp4/master/img/0322-uml-ingredient-diagram_activity-loop.png)

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
