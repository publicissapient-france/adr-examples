# Utiliser les Markdown Architectural Decision Records

* Statut : Accepté
* Date : 2019-02-20

## Contexte et définition du problème

Nous voulons documenter les décisions d'architecture prises dans le cadre de ce projet.

Quel format et quelle structure ces documents devraient-ils suivre ?

## Options envisagées

* [MADR](https://adr.github.io/madr/) 2.1.2 – Les Markdown Architectural Decision Records
* [Michael Nygard's template](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) – La première formalisation du terme "ADR"
* [Sustainable Architectural Decisions](https://www.infoq.com/articles/sustainable-architectural-design-decisions) – Les Y-Statements
* Autres modèles recensés sur <https://github.com/joelparkerhenderson/architecture_decision_record>
* Pas de format – Pas de convention pour le format ou la structure des fichiers

## Décision

Option sélectionnée : "MADR 2.1.2", car

* Les hypothèses implicites doivent être rendues explicites.
  La documentation de la conception est importante pour permettre aux gens de comprendre les décisions après coup.
  Cf. [A rational design process: How and why to fake it](https://doi.org/10.1109/TSE.1986.6312940).
* Le format MADR est léger et correspond à nos méthodes de développement.
* La structure MADR est compréhensible et facilite l'utilisation et la maintenance.
* Le projet MADR est vivant.
* La version 2.1.2 est la plus récente à l'heure de ces lignes.