# Fiche descriptive

## Cas \#5
* _Nom :_ Sélecteur de commande (Cas d'utilisation `selectOrder`)
* _Acteur :_  **`employee`**
* _Description :_ Sélection d'une commande existante
* _Auteur :_Frédéric Zind
* _Date(s) :_ 07.06.2018 (rev0)
* _Pré-conditions :_ Utilisateur connecté comme _`employee`_
* _Démarrage :_ Affiche un formulaire de recherche

## Scénario nominal
1. _`system`_ affiche le formulaire de recherche
* _`employee`_ renseigne/valide le formulaire
* _`system`_ retourne le résumé d'une commande
* _`employee`_ selectionne une commande
* _`system`_ appel le cas d'utilisation associé : _`viewOrder`_
* **Fin**

## Les scénarios alternatifs
* 2-a  annule la commande : **fin**
* 3-a _`system`_ retourne une liste de résumés de commandes
    * 4-a _`employee`_ selectionne une commande
    * **reprise de l'étape 5** du scénario nominal
* 4-a  annule la commande : **fin**

## Post-conditions :
* Commande séléctionnée

## Complements

### Ergonomie
L’affichage des commandes (scénario alternatif «a») devra se faire par groupe de 15. Toutefois, il devra être possible de choisir des pages avec 30, 45 ou 60 commandes.

### Performance attendue
La recherche des commandes doit se faire de façon à afficher le(s) résumé(s) de commande(s) en moins de 3 secondes.

### Problèmes non résolus
* Quels champs font partit du résumé de commande?
