# Fiche descriptive

## Cas \#1

* _Nom_ : Paiement de la commande (Cas d'utilisation `payment`)
* _Acteur_ : **`client`**
* _Description_ : Interface de paiement de la commande avec un ou plusieurs moyen de paiement (exclusif)
* _Auteur_ : **Frédéric Zind**
* _Date(s)_ : 31.05.2018 (rev0)
* _Démarrage_ : Page de choix du moyen de paiement

## Scénario nominal

1. _`client`_ accède au choix du moyen de paiement
2. _`system`_ propose le moyen de paiement _carte bancaire_
3. _`client`_ valide le moyen de paiement _carte bancaire_
4. _`system`_ appelle le cas d'utilisation associé : _`creditCard`_
5. _Pré-conditions_ : commande avec le statut [`Draft`] (Cas d'utilisation _`createOrder`_)
6. **Fin**

## Scénarios alternatifs

1. 1 _`employee`_ accède au choix du moyen de paiement
    * 1 . 2 _`system`_ propose le moyen de paiement _carte bancaire_, _espèce_ & _chèque_
    * 1 . 3 _`employee`_ valide le moyen de paiement _carte bancaire_
    * 1 . 4 _`system`_ appelle le [cas d'utilisation associé _`creditCard`_](https://github.com/freezed/ocp4/blob/master/0292-uml-order-use_case_description-credit_card.md)
    * 1 . 5 **Fin**
2. 1 _`employee`_ accède au choix du moyen de paiement
    * 2 . 2 _`system`_ propose le moyen de paiement _carte bancaire_, _espèce_ & _chèque_
    * 2 . 3 _`employee`_ valide le moyen de paiement _espèce_
    * 2 . 4 _`system`_ appelle le [cas d'utilisation associé _`cash`_](https://github.com/freezed/ocp4/blob/master/0294-uml-order-use_case_description-cash.md)
    * 2 . 5 **Fin**
3. 1 _`employee`_ accède au choix du moyen de paiement
    * 3 . 2 _`system`_ propose le moyen de paiement _carte bancaire_, _espèce_ & _chèque_
    * 3 . 3 _`employee`_ valide le moyen de paiement _chèque_
    * 3 . 4 _`system`_ appelle le [cas d'utilisation associé _`check`_](https://github.com/freezed/ocp4/blob/master/0293-uml-order-use_case_description-check.md)
    * 3 . 5 **Fin**
4. 3 _`client`_ annule la commande
    * 4 . 4 **Fin**
5. 3 _`client`_ valide le moyen de paiement espèce
    * 5 . 4 _`system`_ appelle le [cas d'utilisation associé _`cash`_](https://github.com/freezed/ocp4/blob/master/0294-uml-order-use_case_description-cash.md)
    * 5 . 5 **Fin**
6. 3 _`client`_ valide le moyen de paiement chèques
    * 6 . 4 _`system`_ appelle le [cas d'utilisation associé _`check`_](https://github.com/freezed/ocp4/blob/master/0293-uml-order-use_case_description-check.md)
    * 6 . 5 **Fin**

## Post-conditions

* nouveau cas d'utilisation appelé

## Compléments

### Ergonomie

* Chaque étape se fera sur une page dédiée
* Ne pas utiliser de pop-up

### Performance attendue

* Le passage d'une étape à une autre doit se faire en moins d'une seconde.

### Problèmes non résolus

* Combien de temps l'acheteur peut-il prendre pour finaliser une commande?
