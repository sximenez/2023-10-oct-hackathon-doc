# Titre de l'app

_L'important, c'est la formation de la pensée, pas l'exercice formel en tant que tel (Pierre Cassou-Noguès)._

- [Titre de l'app](#titre-de-lapp)
  - [Plan](#plan)
  - [Réel](#réel)
  - [Phase 0. Préparation](#phase-0-préparation)
    - [Rôles](#rôles)
    - [Environnement](#environnement)
  - [Phase 1. Cahier des charges](#phase-1-cahier-des-charges)
    - [Méthode QQCOQP](#méthode-qqcoqp)
  - [Phase 2. Conception](#phase-2-conception)
  - [Phase 3. Développement](#phase-3-développement)
    - [Sécurisation](#sécurisation)
  - [MVP](#mvp)
  - [Conclusion](#conclusion)

---

## Plan

```mermaid
graph LR

subgraph Phase 0. Préparation
Rôles --> Environnement
end

Environnement -- 8h45 --> Problématique

subgraph Phase 1. Cahier des charges - 9h45 max

subgraph 9h15 max
Problématique --> Sujet
end

Sujet --> Fonctionnalités
end

subgraph Phase 2. Conception - 10h30 max

subgraph 1[Front]
direction LR
Composants --- Pages
end

subgraph 2[Back]
direction LR
Entités --- Routes
end

end

subgraph Phase 3. Développement - 18h

subgraph 3[Front]
direction LR
Vues --> Logique
end

subgraph 4[Back]
direction LR
Persistence --> API
end

subgraph 16h30
Tests/Débug/Refacto
end

Tests/Débug/Refacto --> MVP

end

subgraph Phase 4. Bouclage - 12h max
direction LR
MVP --> 5[Test final] --> Pitch
end

Fonctionnalités --> 1[Front] --> 3[Front] --> Tests/Débug/Refacto
Fonctionnalités --> 2[Back] --> 4[Back] --> Tests/Débug/Refacto

style 3 stroke:lightgreen
style 4 stroke:orange
style MVP stroke:yellow
```
---

## Réel

```mermaid
graph LR

subgraph Phase 0. Préparation
Rôles --> Environnement
end

Environnement -- 8h45 --> Problématique

subgraph Phase 1. Cahier des charges - 9h45 max

subgraph 9h15 max
Problématique --> Sujet
end

Sujet --> Fonctionnalités
end

subgraph Phase 2. Conception - 10h30 max

subgraph 1[Front]
direction LR
Composants --- Pages
end

subgraph 2[Back]
direction LR
Entités --- Routes
end

end

subgraph Phase 3. Développement - 18h

subgraph 3[Front]
direction LR
Vues --> Logique
end

subgraph 4[Back]
direction LR
Persistence --> API
end

subgraph 16h30
Tests/Débug/Refacto
end

Tests/Débug/Refacto --> MVP

end

subgraph Phase 4. Bouclage - 12h max
direction LR
MVP --> 5[Test final] --> Pitch
end

Fonctionnalités --> 1[Front] --> 3[Front] --> Tests/Débug/Refacto
Fonctionnalités --> 2[Back] --> 4[Back] --> Tests/Débug/Refacto

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
subgraph Organization Github
Kanban

subgraph A[Repo front]
direction LR
Next.js
end

subgraph B[Repo back]
direction LR
Symfony
end
end

Kanban --- A[Repo front]
Kanban --- B[Repo back]

style A stroke:lightgreen
style B stroke:orange

```

```mermaid
graph LR
subgraph branches
direction BT
2[develop] -->|MR| 1[main]
3[feature 1] -->|MR| 2[develop]
4[feature 2] -->|MR| 2[develop]
5[feature 3] -->|MR| 2[develop] 
end
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

```mermaid
graph LR

subgraph Front
direction LR

subgraph Composants
A
B
C
end

subgraph Pages
1
2
3
end

end

subgraph Back
direction LR

subgraph Entités
D
E
F
end

subgraph Routes
4
5
6
end

end

Front --- Back

```

## Phase 3. Développement

![Architecture](architecture.png)

```mermaid
graph LR 

subgraph Next.js
1[Vues] --- 2[Logique]
end

subgraph Symfony
4{{API}} --- 3[(Persistence)]
end

2[Logique] --- 4{{API}}

```

Vues : montrer file structure

Logique : montrer exemple fetch

API : montrer les routes via Nelmio

Persistence : montrer les accès à la base

### Sécurisation

Front : sécurisation des formulaires avec DOM purify ?

Back : utilisation de `htmlspecialchars` + JWT pour protéger les routes

## MVP

## Conclusion

- Projet : 

- Front : Next.js

- Back : Symfony

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

| Phase | Description | Compétence
| -------- | -------- | -------- |
| Préparation | Mise en place de Docker avec MySql et non postgresql | Config |
| Préparation | postgresql | Autoformation |