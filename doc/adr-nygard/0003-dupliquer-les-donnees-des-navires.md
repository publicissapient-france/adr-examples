# 3. Dupliquer les données des navires

Date: 2017-01-10

## Statut

Déprécié

## Contexte

Les données statiques des navires (nom, pays, longueur, tirant d'eau) sont utilisées par deux services : le service de suivi de position des navires et celui de réservation d'un emplacement dans un port.

Ces deux services se veulent indépendants, mais partagent actuellement une table de la base de données pour ces informations.

## Décision

Nous faisons le choix de dupliquer les données des navires.

### Conséquences

Les deux services deviennent réellement indépendants, et peuvent faire évoluer leurs modèles respectifs en toute autonomie.

Le volume nécessaire pour le stockage des données des navires est doublé.
Etant donné qu'il s'agit d'un volume de données faible, cette conséquence est considérée comme acceptable.

Les données disponibles pour chacun des services sont susceptibles d'être différentes à un moment donné.
Etant donné que ces données n'évoluent que très peu dans le temps, cette conséquence est considérée comme acceptable.

Le code qui gère l'accès à cette table est également dupliqué.
Etant donné que ce code ne contient pas de logique métier, cette conséquence est considérée comme acceptable.