# Fiche descriptive

## Cas \#3

* _Nom_ : Paiement par chèque (Cas d'utilisation `check`)
* _Acteur_ : **`buyer`**
* _Description_ : Interface de paiement par chèque
* _Auteur_ : **Frédéric Zind**
* _Date(s)_ : 31.05.2018 (rev0)
* _Pré-conditions_ : Un moyen de paiement à été choisi (Cas d'utilisation `payment`)
* _Démarrage_ : La page du paiement par chèque est présentée

## Scénario nominal
1. _`buyer`_ choisi le moyen de paiement _chèque_
2. _`system`_ affiche le formulaire de saisie des données relative au chèque
3. _`buyer`_ renseigne les informations demandées
4. _`system`_ retourne la réponse : _`paiement accepté`_
5. _`system`_ modifie le statut de la commande : [`New`]
6. **Fin**

## Scénarios alternatifs
1. 1 _`buyer`_ annule le paiement : **fin**
2. 3 _`buyer`_ annule le paiement : **fin**
3. 4 _`system`_ répond  _`paiement refusé`_ : **retour à l'étape 1**

## Post-conditions

* Statut de la commande à [`New`] : enregistrement en BDD

## Compléments

### Ergonomie

* Chaque étape se fera sur une page dédiée
* Ne pas utiliser de pop-up

### Performance attendue

* Le passage d'une étape à une autre doit se faire en moins d'une seconde

### Problèmes non résolus

* Combien de temps l'acheteur peut-il prendre pour finaliser une commande?
