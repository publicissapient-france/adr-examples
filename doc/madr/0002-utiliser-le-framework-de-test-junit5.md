# Utiliser le framework de test JUnit 5

* Statut : Accepté
* Date : 2019-02-25

Technical Story: [JIRA-2205 Sélection d'un framework de test](https://company.atlassian.net/browse/JIRA-2205)

## Contexte et énoncé du problème

Plusieurs frameworks d'automatisation des tests pour le langage Java existent sur le marché.

A l'occasion du début du projet, nous avons l'opportunité de sélectionner celui qui convient le mieux à notre besoin.

## Critères de décision

* Le framework doit être un projet vivant, maintenu par une communauté active.
* Le framework doit être connu d'une grande partie des développeurs afin d'éviter une montée en compétence trop longue pour chaque nouvel arrivant.
* Une solution permettant de catégoriser les tests (unitaires, intégration, API) doit être disponible.
* Une solution permettant de paramétriser les tests doit être disponible.
* Le framework doit être compatible avec le framework de mock Mockito en version 2 ou supérieure.
* Le framework doit être compatible avec le langage Java en version 11 ou supérieur.

## Options envisagées

* TestNG
* JUnit 4
* JUnit 5

## Décision

Option sélectionnée: JUnit 5, car

* JUnit 5 est la solution qui répond le mieux aux critères de décision (voir ci-dessous).

## Conséquences positives

* Le mécanisme de catégorisation des tests de JUnit 5 permettra de distinguer les tests au niveau du build de manière plus dynamique.
* La migration vers des versions futures de Java sera facilitée par l'adoption de JUnit 5.

## Conséquences négatives

* Les développeurs doivent monter en compétence sur ce nouveau framework. L'organisation d'une session de présentation est recommandée.

## Points forts et points faibles des différentes options

### TestNG

[Site officiel TestNG](https://testng.org/doc)

* Mauvais, car le projet n'est plus actif.
* Mauvais, car une large majorité des développeurs Java ne connaissent que JUnit.

Les autres critères n'ont pas été étudiés.

### JUnit 4

[Site officiel JUnit 4](https://junit.org/junit4)

* Mauvais, car le projet n'est plus actif et il est recommandé de passer en version 5.
* Bon, car une large majorité des développeurs ne connait que JUnit dans sa version 4.
  Cependant, il est probable que le rapport s'inverse dans les années à venir.
* Moyen, car JUnit 4 ne permet de définir des catégories de tests.
  Toutefois, il est possible de contourner ce problème par une convention de nommage des classes des test et la configuration des plugins Maven.
* Moyen, car la solution native de paramétrisation des tests de JUnit 4 est peu utilisable.
  Toutefois, il est possible d'utiliser une librairie tierce (JUnitParams) pour répondre à ce besoin.
* Bon, car JUnit 4 est compatible avec Mockito 2.
* Moyen, car JUnit 4 est compatible avec Java 11.
  Toutefois, il est probable que l'évolution des versions finissent par ne plus être supportée.

### JUnit 5

[Site officiel JUnit 5](https://junit.org/junit5)

* Bon, car le projet est actif.
* Moyen, car une large majorité des développeurs ne connait que JUnit dans sa version 4.
  Cependant, il est probable que le rapport s'inverse dans les années à venir.
* Bon, car JUnit 5 permet nativement de définir des catégories de tests par un système d'annotations.
* Bon, car JUnit 5 intègre une solution de paramétrisation des tests très utilisable nativement.
* Bon, car JUnit 5 est compatible avec Mockito 2.
* Bon, car JUnit 5 est compatible avec Java 11.
