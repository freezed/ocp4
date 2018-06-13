# Fiche descriptive

## Cas \#4

* _Nom_ : Paiement par espèces (Cas d'utilisation `cash`)
* _Acteur_ : **`buyer`**
* _Description_ : Interface de paiment par espèces
* _Auteur_ : **Frédéric Zind**
* _Date(s)_ : 31.05.2018 (rev0)
* _Pré-conditions_ : Un moyen de paiement à été choisi (Cas d'utilisation `payment`)
* _Démarrage_ : La page du paiement par espèces est présentée

## Scénario nominal
1. _`buyer`_ choisi le moyen de paiement _espèces_
* _`system`_ affiche le formulaire de saisie des données relative aux espèces
* _`buyer`_ renseigne les informations demandées
* _`system`_ retourne la réponse : _`paiement accepté`_
* _`system`_ modifie le statut de la commande : [`New`]
* **Fin**

## Scénarios alternatifs
* 1.a _`buyer`_ annule le paiement : **fin**
* 3.a _`buyer`_ annule le paiement : **fin**
* 4-a _`system`_ répond  _`paiement refusé`_ : **retour à l'étape 1**

## Post-conditions
* Commande annulée :
    - pas d'enregistrement en BDD
* Statut de la commande à [`New`] :
    - enregistrement en BDD

## Complements

### Ergonomie
* Chaque étape se fera sur une page dédiée
* Ne pas utiliser de pop-up

### Performance attendue
* Le passage d'une étape à une autre doit se faire en moins d'une seconde

### Problèmes non résolus
* Combien de temps l'acheteur peut-il prendre pour finaliser une commande?
