_L'important, c'est la formation de la pensée, pas l'exercice formel en tant que tel (Pierre Cassou-Noguès)._

## Plan

```mermaid
graph LR
subgraph Prévisionnel
Equipe --> Environnement --> Roadmap
end
subgraph Développement
Roadmap --> CDC --> Conception --> Réalisation --> Front --> Vues --> Logique --> MVP
Réalisation --> Back --> Persistence --> API --> MVP
end
MVP --> Démo --> Conclusion
style Vues stroke:lightgreen
style Persistence stroke:orange
style API stroke:orange
style Logique stroke:lightgreen
```

## Résumé

- Projet : dans le cadre du Hackathon 2023, développement intensif en équipe de quatre développeurs d'une application web X.

- Front : Next.js

- Back : Symfony - API Platform

- Résultat :

  - Organisation de l'environnement de travail

  - Conception et réalisation de l'application

  - Collaboration en équipe

  - Mise en pratique des connaissances sur un délai de développement très court

### Objectifs

Conformément au cahier des charges (CDC) :

- Lister les attendus du projet

- Lister les contraintes du projet

- Concevoir le projet

- Réaliser si possible une première version du projet

- Présenter les résultats

## Prévisionnel

### Equipe

- Frontend : Young-hee et Alexis

- Backend : Olivier

- Fullstack : Steven

### Environnement de développement

Etant donné le délai très court du projet, nous avons estimé pertinent d'anticiper la mise en place du cadre organisationnel et technique.

- GitHub : mise en place d'une équipe, un tableau Kanban et deux dépôts

```mermaid
graph TD
Organization --- Kanban
Kanban --- A[Repo front]
Kanban --- B[Repo back]

```

- Choix des technologies : nous avons opté pour des technologies offrant des composants prêts à l'emploi, afin de gagner du temps et de nous concentrer sur la satisfaction du besoin (business logic) :

  - Front : React, avec Material UI (MUI), Next.js ?

  - Back : PHP Symfony + API Platform

### Roadmap

Nous avons également anticipé les grandes étapes du projet :

- Une fois la consigne connue, brainstorming et définition du CDC (méthode QQCOQP).
- 
```mermaid
graph TD
Projet --> A[Quoi ? Objectif<br>Ce projet vise à ...]
Projet --> B[Quand ? Deadline <br>13 octobre]
Projet --> C[Qui ? Cible<br>Les utilisateurs sont ...]
Projet --> D[Comment ?<br>Les fonctionnalités, interfaces ...]
D --> F[Front]
F --> G[Charte graphique]
F --> Thème
D --> H[Back]
H --> Entités
Projet --> E[Pourquoi ?<br>Justifier nos choix ...]

```

- Puis, une phase de conception et de réalisation, découpée en quatre grandes couches de responsabilité.


```mermaid
graph LR
0{{Conception}} --> 1{{Vues}}
subgraph Développement
subgraph Equipe front : Young-hee et Alexis
1{{Vues}} --> 4{{Logique}}
end
subgraph Equipe back : Olivier et Steven
2{{Persistence}} --> 3{{API}}
end
3{{API}} --> 10{{Test}} --> 4{{Logique}}
end
0{{Conception}} --> 2{{Persistence}}
4{{Logique}} --> 5{{Test}} --> 6{{Refacto}} --> 7{{Deploiement}}
6{{Refacto}} --> 8{{Documentation}}
style 1 stroke:lightgreen
style 2 stroke:orange
style 3 stroke:orange
style 4 stroke:lightgreen
```

## Cahier des charges

## Conception et architecture

## Réalisation

## Demo

## Conclusion
