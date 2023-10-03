# Titre de l'app

_L'important, c'est la formation de la pensée, pas l'exercice formel en tant que tel (Pierre Cassou-Noguès)._

- [Titre de l'app](#titre-de-lapp)
  - [Plan](#plan)
  - [Phase 0. Préparation](#phase-0-préparation)
    - [Rôles](#rôles)
    - [Environnement](#environnement)
  - [Phase 1. Cahier des charges](#phase-1-cahier-des-charges)
    - [Méthode QQCOQP](#méthode-qqcoqp)
  - [Phase 2. Conception](#phase-2-conception)
    - [Front : Composants](#front--composants)
    - [Back : Entités](#back--entités)
  - [Phase 3. Développement](#phase-3-développement)
    - [Front : Vues](#front--vues)
    - [Back : Persistence](#back--persistence)
    - [Back : API](#back--api)
    - [Front : Logique](#front--logique)
  - [MVP](#mvp)
  - [Conclusion](#conclusion)

---

## Plan

```mermaid
graph LR

subgraph Phase 0. Préparation
Rôles --> Environnement
end

Environnement --> Problématique

subgraph Phase 1. Cahier des charges - 10h max
Problématique --> Sujet --> Fonctionnalités
end

subgraph Phase 2. Conception - 11h max

subgraph 1[Front]
Composants
end

subgraph 2[Back]
Entités
end

end

subgraph Phase 3. Développement - Fin de journée 1

subgraph 3[Front]
direction LR
Vues --> Logique
end

subgraph 4[Back]
direction LR
Persistence --> API
end

Débug --> V0

end

subgraph Phase 4. Bouclage - 10h max
direction LR
V0 --> Refacto --> Test --> MVP
end

Fonctionnalités --> 1[Front] --> 3[Front] --> Débug
Fonctionnalités --> 2[Back] --> 4[Back] --> Débug

style 3 stroke:lightgreen
style 4 stroke:orange
style MVP stroke:yellow
```
---

## Phase 0. Préparation

### Rôles

```mermaid
graph TB

subgraph Full

subgraph Front
Alexis
Young-hee
end

subgraph Back
Olivier
end

Steven

end

Front --- Steven --- Back
```

### Environnement

```mermaid
graph LR
0[Organization GitHub] --- Kanban

subgraph A[Repo front]
direction LR
React --- 1[React Router]
end

subgraph B[Repo back]
direction LR
Symfony --- 2[API Platform]
end

Kanban --- A[Repo front]
Kanban --- B[Repo back]

style A stroke:lightgreen
style B stroke:orange

```

## Phase 1. Cahier des charges

### Méthode QQCOQP

```mermaid
graph LR

subgraph Problématique
0[Quel est le problème ?]
end

subgraph Sujet
1[Comment on résout ce problème ?]
2[Pourquoi cette solution ?]
end

subgraph Fonctionnalités
3[Par quels moyens ?]
end

0[Quel est le problème ?] --> 1[Comment on résout ce problème ?] --> 2[Pourquoi cette solution ?] --> 3[Par quels moyens ?]

```

## Phase 2. Conception

### Front : Composants

### Back : Entités

## Phase 3. Développement

### Front : Vues

### Back : Persistence

### Back : API

### Front : Logique

## MVP

## Conclusion

- Projet : 

- Front : React - React Router

- Back : Symfony - API Platform

- Résultats :

| Phase | Description | Compétence
| -------- | -------- | -------- |
| Préparation | Répartition des rôles et choix des technos (focus prêt à l'emploi) | Concertation |
| Préparation | Mise en place de l'environnement de travail | Organisation |
| Conception | Choix des composants/entités | Travail d'équipe |
| Réalisation | Push GitHub + tests fonctionnels | Travail d'équipe |
| Réalisation | Respect des délais | Sens des priorités |
| Pitch | Bouclage | Esprit de synthèse |

- Difficultés :