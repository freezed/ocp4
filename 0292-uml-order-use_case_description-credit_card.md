# Fiche descriptive

## Cas \#2

* _Nom_ : Paiement par carte bancaire (Cas d'utilisation `creditCard`)
* _Acteur(s)_ :
    - **`buyer`**
    - **`bank`**
* _Description_ : Interface de paiment par carte bancaire
* _Auteur_ : **Frédéric Zind**
* _Date(s)_ : 31.05.2018 (rev0)
* _Pré-conditions_ : Un moyen de paiement à été choisi (Cas d'utilisation `payment`)
* _Démarrage_ : La page du paiement par carte bancaire est présentée

## Scénario nominal
1. _`buyer`_ choisi le moyen de paiement _carte bancaire_
* _`system`_ affiche le formulaire de saisie des données relative à la carte bancaire
* _`buyer`_ renseigne les informations demandées
* _`system`_ transmet les informations a _`bank`_
* _`bank`_ retourne la réponse : _`paiement accepté`_
* _`system`_ modifie le statut de la commande : [`New`]
* **Fin**

## Scénarios alternatifs
* 1.a _`buyer`_ annule le paiement : **fin**
* 3.a _`buyer`_ annule le paiement : **fin**
* 5.a _`bank`_ retourne la réponse _`paiement refusé`_ : **retour à l'étape 1**

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
* Les étapes 4 à 5 pourront dépasser ce délai exceptionnellement, sans pour autant aller au delà de 5s. Un message d'attente devra s'afficher avec un lien en cas de délai dépassé.

### Problèmes non résolus
* Combien de temps l'acheteur peut-il prendre pour finaliser une commande?
