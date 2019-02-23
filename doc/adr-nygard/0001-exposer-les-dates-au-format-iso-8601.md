# 1. Exposer les dates au format ISO 8601

Date : 2019-02-23

## Statut

Accepté

## Contexte

Le service expose différentes dates à ses clients (date de création du véhicule, date de début de prêt, etc.).

A l'heure actuelle, ces dates sont exposées avec des formats différents (timestamp, `dd/mm/yyyy`, `mm\dd\yyyy`), ce qui est à l'origine d'incompréhensions et d'anomalies côté client.

Pour éviter les erreurs, le format doit être clairement défini et cohérent entre les différents objets.

## Décision

Nous faisons le choix d'exposer les dates au format ISO 8601.

## Conséquences

Ce format est standard et indépendant du pays, à l'inverse des formats utilisés précédemment.

Ce format est un standard disponible par défaut dans la plupart des langages, ce qui devrait conduire à une simplification du code des applications clients.

La confusion entre le style du Royaume-Uni et celui des USA n'est plus possible.

Il est nécessaire que les clients mettent à jour leurs applications pour s'adapter au nouveau format. 
Pour donner un buffer aux clients, deux versions de l'API seront exposées pendant une période de transition d'une durée d'un mois.
