# Fiche descriptive

## Cas \#1

* _Nom_ : Paiement de la commande (Cas d'utilisation `payment`)
* _Acteur_ :
    - **`buyer`**
* _Description_ : Interface de paiement de la commande avec un ou plusieurs moyen de paiement (exclusif)
* _Auteur_ : **Frédéric Zind**
* _Date(s)_ : 31.05.2018 (rev0)
* _Pré-conditions_ :
    - une commande avec le statut [`Draft`] (Cas d'utilisation _`createOrder`_)
    - [?] connaissance de :
        - l'_acteur primaire_ dont _`buyer`_ est la spécialisation (_`employee`_ ou _`client`_)
        - ou
        - preudo-status [prepaid] ou  [postpaid]
* _Démarrage_ : Page de choix du moyen de paiement

## Scénario nominal
1. _`system`_ propose le ou les moyen(s) de paiement associé à l'_acteur primaire_ dont _`acheteur`_ est la spécalisation :
    * _`employee`_ / [postpaid]
        * carte bancaire
        * Chèques
        * Espèce
    * _`client`_ / [prepaid]
        * carte bancaire
* _`buyer`_ valide le moyen de paiement _carte bancaire_
* _`system`_ appelle le cas d'utilisation associé : _`creditCard`_
* **Fin**

## Scénarios alternatifs
* 2-a _`buyer`_ annule la commande : **fin**
* 2-b _`client`_ valide le moyen de paiement espèce
    * 3-b _`system`_ appelle le cas d'utilisation associé : _`cash`_
    * **Fin**
* 2-c _`client`_ valide le moyen de paiement chèques
    * 3-c _`system`_ appelle le cas d'utilisation associé : _`check`_
    * **Fin**

## Post-conditions
* moyen de paiement choisi
* rien si annulation

## Complements

### Ergonomie
* Chaque étape se fera sur une page dédiée
* Ne pas utiliser de pop-up

### Performance attendue
* Le passage d'une étape à une autre doit se faire en moins d'une seconde.

### Problèmes non résolus
* Combien de temps l'acheteur peut-il prendre pour finaliser une commande?
