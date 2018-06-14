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
2. _`employee`_ renseigne/valide le formulaire
3. _`system`_ retourne le résumé d'une commande
4. _`employee`_ sélectionne une commande
5. _`system`_ appel le cas d'utilisation associé : _`viewOrder`_
6. **Fin**

## Les scénarios alternatifs
1. 2  annule la commande : **fin**
2. 3 _`system`_ retourne une liste de résumés de commandes
    * 2 . 4 _`employee`_ sélectionne une commande
    * 2 . 5 **reprise de l'étape 5** du scénario nominal
3. 4  annule la commande : **fin**

## Post-conditions

* Commande sélectionnée

## Compléments

### Ergonomie

L’affichage des commandes (scénario alternatif «a») devra se faire par groupe de 15. Toutefois, il devra être possible de choisir des pages avec 30, 45 ou 60 commandes.

### Performance attendue

La recherche des commandes doit se faire de façon à afficher le(s) résumé(s) de commande(s) en moins de 3 secondes.

### Problèmes non résolus

* Quels champs font partit du résumé de commande?
