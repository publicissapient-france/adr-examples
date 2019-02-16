# Dupliquer les données des navires

* Statut : Déprécié
* Date : 2017-01-10

## Contexte et énoncé du problème

Les données statiques des navires (nom, pays, longueur, tirant d'eau) sont utilisées par deux services : le service de suivi de position des navires et celui de réservation d'un emplacement dans un port.

Ces deux services se veulent indépendants, mais partagent actuellement une table de la base de données pour ces informations.

## Options envisagées

* Choix d'un service propriétaire de la table et ajout d'une dépendance dans l'autre service
* Création d'un service dédié aux données statiques des navires
* Duplication des données dans deux bases
  Pour chacune des bases, le service propriétaire est clairement identifié comme le service qui l'utilise

## Décision

Option sélectionnée : Duplication des données dans les deux bases, car 

* Ajouter un nouveau service serait lourd
* Ajouter une dépendance d'un service à l'autre n'aurait pas de sens du point de vue métier
* Le volume de données est peu important
* Les données sont statiques et ne devraient donc pas diverger

### Conséquences positives

* Les deux services deviennent réellement indépendants, et peuvent faire évoluer leurs modèles respectifs en toute autonomie.

### Conséquences négatives

* Le code qui gère l'accès à cette table est également dupliqué.
  Etant donné que ce code ne contient pas de logique métier, cette conséquence est considérée comme acceptable.