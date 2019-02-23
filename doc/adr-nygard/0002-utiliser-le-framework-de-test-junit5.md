# 2. Utiliser le framework de test JUnit 5

Date : 2019-02-25

## Statut

Accepté

## Contexte

Plusieurs frameworks d'automatisation des tests pour le langage Java existent sur le marché.

A l'occasion du début du projet, nous avons l'opportunité de sélectionner celui qui convient le mieux à notre besoin.

Une étude des différents frameworks nous indique que :
 * TestNG n'est plus actif et peu connu des développeurs Java.
 * JUnit 4 est le plus répandu, mais devrait décliner, ce qui présente des risques en terme de compatibilité de librairies tierces et de version du langage Java, car son développement a été arrêté au profit de JUnit 5.
 * JUnit 5 n'est pas encore pleinement adopté, mais est mature et offre de nombreuses fonctionnalités utiles telles que la catégorisation des tests ou leur paramétrisation.

## Décision

Nous faisons le choix d'utiliser JUnit 5.

## Conséquences

La migration vers des versions futures de Java sera facilitée par l'adoption de JUnit 5.

Le mécanisme de catégorisation des tests de JUnit 5 permettra de distinguer les tests au niveau du build de manière plus dynamique.

Les développeurs doivent monter en compétence sur ce nouveau framework. L'organisation d'une session de présentation est recommandée.