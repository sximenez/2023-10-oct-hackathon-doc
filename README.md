# Adopte ton festival !

_L'important, c'est la formation de la pensée, pas l'exercice formel en tant que tel (Pierre Cassou-Noguès)._

- [Adopte ton festival !](#adopte-ton-festival-)
  - [Résumé](#résumé)
  - [Cas d'utilisation](#cas-dutilisation)
  - [Demo](#demo)
  - [Méthodologie de travail](#méthodologie-de-travail)
  - [Phase 0. Préparation](#phase-0-préparation)
    - [Rôles](#rôles)
    - [Environnement](#environnement)
  - [Phase 1. Cahier des charges](#phase-1-cahier-des-charges)
    - [Méthode QQCOQP](#méthode-qqcoqp)
    - [Backlog de l'application](#backlog-de-lapplication)
  - [Phase 2. Conception](#phase-2-conception)
  - [Phase 3. Développement](#phase-3-développement)
    - [Base de données](#base-de-données)
    - [Backend](#backend)
    - [Frontend](#frontend)
  - [Conclusion](#conclusion)

---

## Résumé

- Besoin : Proposer une solution pour consulter des données publiques avec la possibilité de mise à jour par l'utilisateur. 

- Projet : Création d'un site aggrégant les festivals actifs en France, permettant une recherche facile avec la possibilité de signaler des erreurs.

## Cas d'utilisation

```mermaid
graph LR

Utilisateur --> App --> 0[Page d'accueil : liste des festivals]
0[Page d'accueil : liste des festivals] --> 1[Rechercher un festival]
0[Page d'accueil : liste des festivals] --> 2[Visualiser des données + carte] 
0[Page d'accueil : liste des festivals] --> 3[Se connecter]
0[Page d'accueil : liste des festivals] --> S'enregistrer
3[Se connecter] --> 4[Recevoir une newsletter]
3[Se connecter] --> 5[Tagger en favori]
3[Se connecter] --> 6[Historique des recherches]
3[Se connecter] --> 7[Modifier son compte]
3[Se connecter] --> 8[Effacer son compte]
3[Se connecter] --> 9[Réserver un billet]

style 1 stroke:lightgreen
style 2 stroke:lightgreen
style 3 stroke:lightgreen
style S'enregistrer stroke:lightgreen

style 4 stroke:orange
style 5 stroke:orange
style 6 stroke:orange
style 7 stroke:orange
style 8 stroke:orange

```

## Demo

## Méthodologie de travail

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

style Essentielles stroke:yellow

```

```mermaid
graph LR

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
API
end
 
API --> Logique

Logique --> 6[Test fonctionnel OK]

end

00[Liste des fonctionnalités] --> AA[Phase 2. Cycle conception par feature - 10h max] --> BB[Phase 3. Cycle développement par feature - 18h]

subgraph CC[Phase 4. Bouclage - 12h max]
direction LR
5[Test final / MVP] --> Pitch
end

BB[Phase 3. Cycle développement par feature - 18h] --> CC[Phase 4. Bouclage - 12h max]

style 5 stroke:yellow
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

![kanban](kanban.png)

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

### Backlog de l'application

| Type | Description | Route |
| -------- | -------- | -------- |
| Essentielle - OK | Affichage des cartes page Home | api/festivals GET |
| Essentielle - OK | Barre de recherche | api/search GET |
| Essentielle | Recherche par catégories (select) | api/categories/{id} GET | 
| Essentielle - OK | Page festival | api/festivals/{id} GET |
| Essentielle - OK | Log in | api/login_check POST |
| Essentielle - OK | Register | api/users POST |
| Essentielle | Signaler une arreur | api/festivals/{id} PUT |
| Optionnelle | Affichage de l'historique des recherches |  |
| Optionnelle | Affichage de cartes selon géolocalisation IP |  |

## Phase 2. Conception

<!-- ```mermaid
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

``` -->

- Maquettage sur papier

- Routes sur papier

## Phase 3. Développement

### Base de données

- API Festivals en France
- BDD relationnelle mySQL
- Insertion table via CSV

![BDD](bdd.png)

### Backend

- API REST avec route JWT

![API](api_routes.png)

### Frontend

- Consommation API et visualisation des données
- Interface responsive
- Ajout d'un user (axe d'amélioration : password hashing)
- Authentification

<!--

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

## MVP -->

## Conclusion

- Stack : 

  - Front : Next.js

  - Back : Symfony

- Résultats :

| Phase | Description | Compétence
| -------- | -------- | -------- |
| Préparation | Répartition des rôles et choix des technos (focus prêt à l'emploi) | Concertation |
| Préparation | Mise en place de l'environnement de travail | Organisation |
| Conception | Choix des composants/entités | Travail d'équipe |
| Réalisation | Push GitHub + tests fonctionnels | Travail d'équipe |
| Réalisation | Features essentielles / optionnelles | Sens des priorités |
| Pitch | Bouclage | Esprit de synthèse |

- Difficultés :

| Phase | Description | Compétence
| -------- | -------- | -------- |
| Préparation | Mise en place de Docker avec MySql et non postgresql | Config |
| Préparation | postgresql | Autoformation |
| Réalisation | Plan | Cycle de développement par feature exigeant dans les délais --> tendance à avancer sur toutes les features pour respecter les délais |
| Réalisation | Mentors | Profiter davantage de leurs avis |
<!-- | Réalisation | Next.js | Moins bien adapté pour une petite appli |
| Réalisation | Symfony | Prioriser API Platform pour respecter les délais | -->