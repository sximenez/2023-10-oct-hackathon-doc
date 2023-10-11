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

Environnement -- 8h45 --> 9h15[9h15 max]

subgraph Phase 1. Cahier des charges

subgraph 9h15[9h15 max]
direction LR
Problématique --> Sujet
end

subgraph 9h30[9h30 max]
direction TB
Fonctionnalités --> Essentielles --> A[Feature 1]
Essentielles --> B[Feature 2]
Essentielles --> C[Feature 3]
Fonctionnalités --> Optionnelles
Optionnelles --> D[Feature 4]
end
end

9h15[9h15 max] --> 9h30[9h30 max]

subgraph AA[Phase 2. Cycle conception par feature - 10h max]
direction LR

subgraph 1[Front]
direction LR
Composants --- Pages
end

subgraph 2[Back]
direction LR
Entités --- Routes
end

end

subgraph BB[Phase 3. Cycle développement par feature - 18h]
direction LR

subgraph 3[Front]
Vues --> Logique
end

subgraph 4[Back]
Persistence --> API
end
 
API --> Logique

3[Front] --> 6[Test OK]
4[Back] --> 6[Test OK]

end

B1[Feature 1] --> AA[Phase 2. Cycle conception par feature - 10h max] --> B2[Feature 2] --> AA[Phase 2. Cycle conception par feature - 10h max] --> B3[Feature ...] --> BB[Phase 3. Développement par feature - 18h]
B3[Feature ...] --> AA[Phase 2. Cycle conception par feature - 10h max] 

BB[Phase 3. Développement par feature - 18h] --> A2[Feature 2] --> BB[Phase 3. Développement par feature - 18h] --> A3[Feature ...] --> BB[Phase 3. Développement par feature - 18h] 

A3[Feature ...] --> CC[Phase 4. Bouclage - 12h max]

subgraph CC[Phase 4. Bouclage - 12h max]
direction LR
5[Test final] --> MVP --> Pitch
end

style Essentielles stroke:yellow
style 3 stroke:lightgreen
style 4 stroke:orange
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