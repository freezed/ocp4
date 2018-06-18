# Fiche descriptive

## Cas \#6

* _Nom :_ Vue d'une commande (Cas d'utilisation `viewOrder`)
* _Acteur :_  **`employee`**
* _Description :_ Affiche le contenu complet d'une commande existante
* _Auteur :_Frédéric Zind
* _Date(s) :_ 07.06.2018 (rev0)
* _Pré-conditions :_ Commande sélectionnée
* _Démarrage :_ Affiche la fiche de la commande

## Scénario nominal

1. _`system`_ affiche la fiche de la commande
2. **Fin**

## Les scénarios alternatifs

1. 2 _`employee`_ modifie & valide un (ou plusieurs) champs
    * 1 . 3 _`system`_ enregistre les modification : **retour à l'étape 1**
2. 2 _`employee`_ modifie & valide un (ou plusieurs) champs
    * 2 . 3 _`system`_ enregistre les modification : **fin**

## Post-conditions

* Commande sélectionnée
