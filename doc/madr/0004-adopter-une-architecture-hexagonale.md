# Adopter une architecture hexagonale

* Statut : Accepté
* Date : 2019-01-10

## Contexte et énoncé du problème

Le code métier et le boilerplate technique sont interdépendants, ce qui rend les migrations des outils techniques comme les évolutions de logique métier coûteuses.

## Options envisagées

* Architecture hexagonale
* Clean architecture
* Architecture en couches "classique"

## Décisions

Option sélectionnée: architecture hexagonale, car

* L'architecture hexagonale rend la logique métier indépendante du boilerplate technique.
* L'architecture hexagonale est moins contraignante que Clean architecture.

## Liens

* [L'architecture hexagonale](https://blog.xebia.fr/2016/03/16/perennisez-votre-metier-avec-larchitecture-hexagonale/)

