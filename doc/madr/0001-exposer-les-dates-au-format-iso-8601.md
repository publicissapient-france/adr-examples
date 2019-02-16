# Exposer les dates au format ISO 8601

* Statut : Accepté
* Date : 2019-02-23

## Contexte et énoncé du problème

Le service expose différentes dates à ses clients (date de création du véhicule, date de début de prêt, etc.).

A l'heure actuelle, ces dates sont exposées avec des formats différents (timestamp, `dd/mm/yyyy`, `mm\dd\yyyy`), ce qui est à l'origine d'incompréhensions et d'anomalies côté client.

Pour éviter les erreurs, le format doit être clairement défini et cohérent entre les différents objets.

## Critères de décision

* Il est préférable de disposer d'un format qui n'est pas propre à un pays donné.

## Options envisagées

* timestamp
* USA : `dd/mm/yyyy`
* Royaume-Uni : `mm\dd\yyyy`
* ISO 8601 : `yyyy-mm-dd`

## Décision

Option sélectionée : ISO 8601, car

* Seul les formats timestamp et ISO 8601 sont standards et indépendants du pays.
* Les timestamps fournissent un niveau d'information trop détaillé.

### Conséquences positives

* Ce format est un standard disponible par défaut dans la plupart des langages, ce qui devrait conduire à une simplification du code des applications clients.
* La confusion entre le style du Royaume-Uni et celui des USA n'est plus possible.

### Conséquences négatives

* Il est nécessaire que les clients mettent à jour leurs applications pour s'adapter au nouveau format. 
  Pour donner un buffer aux clients, deux versions de l'API seront exposées pendant une période de transition d'une durée d'un mois.

## Liens

* [Format ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)
* [Parsing du format ISO 8601 en Python](https://codeyarns.com/2017/10/12/how-to-convert-datetime-to-and-from-iso-8601-string/)