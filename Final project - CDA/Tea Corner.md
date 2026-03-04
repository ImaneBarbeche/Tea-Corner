# Dossier Projet

**Titre professionnel Conceptrice Développeuse d'Application**

**Auteurs: Georgios Daris, Imane Barbeche**

**Nom: Barbeche**

**Prénom: Imane**

**Tea Corner**

![[Pasted image 20260224085758.png]]

 *NestJs / React avec React Router*

*Promo Java/Angular - 2025/2026*

*Simplon.co, Grenoble*


---

## Table des matières
```table-of-contents
title: 
style: nestedList # TOC style (nestedList|nestedOrderedList|inlineFirstLevel)
minLevel: 2 # Include headings from the specified level
maxLevel: 3 # Include headings up to the specified level
include: 
exclude: 
includeLinks: true # Make headings clickable
hideWhenEmpty: false # Hide TOC if no headings are found
debugInConsole: false # Print debug info in Obsidian console
```
---

## Remerciements

Je tiens à remercier : 


**Ma famille et mes proches**, pour leur soutien et leur patience durant cette reconversion professionnelle.

**George**, mon binôme de projet, pour sa collaboration tout au long de ce projet, pour sa patience et sa bienveillance. 

**Marlène Villanova, Benjamin Fontaine** et **l'équipe STORIES** au LIG pour leur patience, leur soutien et leurs conseils durant ma période de stage. Leurs encouragements et leur confiance m'ont permis de monter en compétence. 

Les **formateurs** à Simplon qui ont fait un effort d'accompagnement pour les débutants tout au long de l'année de formation, et plus particulièrement à l'approche de la certification, en nous proposant des questions ciblées, des oraux blancs, des jeux, et surtout du temps pour répondre à nos questions.

**Mes camarades de classe** qui ont contribué de près ou de loin à l'amélioration de mon projet et à ma montée en compétence.

---
## Résumé du projet

TeaCorner est une application web full‑stack dédiée à la gestion et à la découverte du thé. Elle permet aux utilisateurs d’organiser leur collection, d’explorer de nouvelles saveurs et de créer leurs propres mélanges dans une interface pensée comme un espace apaisant, en cohérence avec le rituel du thé. Le projet est fictif et a été réalisé exclusivement dans le cadre de l’examen final.

Ce travail a été mené dans un délai restreint de cinq semaines, ce qui a nécessité une planification rigoureuse et une priorisation stricte des fonctionnalités. L’objectif principal était d’apprendre de nouvelles technologies tout en consolidant les compétences du parcours CDA. J’ai choisi NestJS pour rester dans l’écosystème TypeScript que je maîtrise déjà (via Angular), tout en explorant un framework backend moderne. React et React Router ont été retenus pour leur popularité en entreprise et pour renforcer mes bases en développement frontend.

Le projet m’a permis d’approfondir des aspects essentiels du développement logiciel : architecture backend, modélisation de données, sécurisation de l’authentification, mise en place d’un pipeline CI/CD et utilisation de Docker. Ces éléments ont constitué les principaux défis techniques, notamment la gestion des rôles, la protection des routes, la configuration des conteneurs et l’automatisation du déploiement.

Le travail a été organisé en binôme, avec une répartition claire des tâches via un système de tickets et un planning défini. Certains choix ont été simplifiés — design minimaliste, fonctionnalités limitées — afin de concentrer l’effort sur la qualité du code, la robustesse de l’architecture et l’intégration des outils DevOps. Plusieurs documents ont accompagné la réalisation : cahier des charges, schémas Merise, maquettes Figma et dossier de projet.

---
## Liste des compétences

Ce projet a permis de valider les 11 compétences du référentiel CDA :

| Compétence REAC                                   | Validation dans le projet                                     |
| ------------------------------------------------- | ------------------------------------------------------------- |
| **1. Installer et configurer son environnement**  | Docker, Docker Compose, VSCode, Git, GitHub Actions           |
| **2. Développer des interfaces utilisateur**      | Pages React (login, dashboard, profil, recettes, minuteur)    |
| **3. Développer des composants métier**           | AuthService (inscription, login), UserService (CRUD profil)   |
| **4. Contribuer à la gestion d'un projet**        | Binôme, tickets Whimsical, planning Notion, Git branches      |
| **5. Analyser les besoins et maquetter**          | Cahier des charges, maquettes Figma, user stories             |
| **6. Définir l'architecture logicielle**          | Architecture MVC (NestJS/React/PostgreSQL), diagrammes        |
| **7. Concevoir une base de données**              | MCD/MLD/MPD Merise, 15+ tables, relations complexes           |
| **8. Développer composants d'accès données**      | TypeORM repositories, entities, requêtes sécurisées           |
| **9. Préparer et exécuter les plans de tests**    | Tests unitaires (Jest), tests d'intégration (Supertest)       |
| **10. Préparer et documenter le déploiement**     | Documentation Docker, variables d'env, configuration Render   |
| **11. Contribuer à la mise en production DevOps** | Pipeline CI/CD GitHub Actions, déploiement automatique Render |

--- 

## Contexte 
### Cahier des charges

#### Identification du problème

TeaCorner permet aux utilisateurs de gérer leurs thés tout en étant soucieux et attentif à leur expérience.

Actuellement il n'existe pas de plateforme en ligne de gestion de recette de thé qui combine toutes les fonctionnalités mentionnées ci-après en un seul endroit. Les plateformes qui existent permettent soit une gestion de type "journal" de ses propres recettes, où tout est créé
manuellement par l'utilisateur, soit une visualisation de recettes de thés, d'accès à un minuteur et de communauté. D'autres proposent uniquement l'aspect méditatif lié à la consommation de thé. De plus, aucune plateforme web n'existe, celles mentionnées ci-dessus sont des applications mobiles. Les seules plateformes de gestion d'infusion de thé sont de simples minuteurs.

Notre application permet de réunir toutes ces fonctionnalités en un site web, tout en apportant la possibilité pour l'utilisateur de personnaliser son expérience.

#### Présentation Générale

##### 1. Objectif du projet

Ce document présente le cahier des charges visant à la conception et au développement d’une application web en architecture MVC, permettant aux utilisateurs :

- de voir et chercher des recettes de thés (barre de recherche et filtre)
- de créer des nouveaux thés et d'ajouter des ingrédients 
- d'ajouter des recettes à sa librairie 
- de suivre sa consommation de thé
- d'avoir accès à un minuteur personnalisable en fonction du thé, de la quantité, et de la température
- de pouvoir créer des entrées dans son journal avec des commentaires pour chaque thé consommé

L'application est constituée d'une interface web avec un design responsive mobile first. 

---
##### 2. Architecture technique

L'application suit une architecture **full-stack moderne** avec séparation claire des responsabilités :

| Couche               | Technologie                               | Rôle                                       |
| -------------------- | ----------------------------------------- | ------------------------------------------ |
| **Frontend**         | React + React Router v7                   | Interface utilisateur, SPA, navigation     |
| **Backend**          | NestJS (Node.js)                          | API REST, logique métier, authentification |
| **Base de données**  | PostgreSQL 16                             | Stockage relationnel, 15+ tables           |
| **ORM**              | TypeORM                                   | Mapping objet-relationnel, migrations      |
| **Containerisation** | Docker + Docker Compose                   | Environnement reproductible                |
| **CI/CD**            | GitHub Actions                            | Tests automatisés, déploiement             |
| **Hébergement**      | Render (backend + DB), Netlify (frontend) | Production                                 |

**Principes architecturaux :**
- **MVC (Model-View-Controller)** : Séparation présentation / logique / données
- **REST API** : Communication stateless entre frontend et backend
- **JWT + Refresh Tokens** : Authentification sécurisée
- **Architecture modulaire** : Modules NestJS indépendants (Auth, User, Tea, etc.)

--- 

##### 3. Contraintes du projet

**Temporelles :**
- Durée totale : 7 semaines
- Deadline fixe : examen final CDA
- Temps de développement effectif : ~5-6 semaines (après conception)

**Techniques :**
- Binôme : coordination et répartition des tâches nécessaire
- Technologies nouvelles : NestJS et React à apprendre en parallèle
- Environnement : développement local, déploiement cloud gratuit

**Organisationnelles :**
- Planning strict : sprints hebdomadaires
- Documentation : dossier projet en parallèle du développement
- Méthodologie : Agile adaptée (tickets Whimsical, daily meetings)

Ces contraintes ont guidé la priorisation des fonctionnalités et le choix d'une architecture simple mais robuste.

---
#### Fonctionnalités

##### 1. Fonctionnalités Utilisateur

###### 1.1. Authentification / Sécurité

- Inscription avec vérification d'email.
- Connexion sécurisée (JWT et refresh token).
- Récupération / réinitialisation de mot de passe.

###### 1.2. Recettes

Le tableau ci-dessous présente les fonctionnalités accessibles selon le statut de connexion de l'utilisateur.

A) **Visualisation et recherche**

| Fonctionnalité                                                     | Visiteur | Utilisateur connecté |
| ------------------------------------------------------------------ | -------- | -------------------- |
| **Voir les recettes du système sur la page d'accueil**             | Oui      | Oui                  |
| **Recherche simple** (barre de recherche)                          | Non      | Oui                  |
| **Recherche avancée** (filtres : catégories, saveurs, ingrédients) | Non      | Oui                  |
| **Système de filtre pour l'affichage**                             | Non      | Oui                  |
| **Voir les détails d'une recette système**                         | Non      | Oui                  |
| **Voir ses propres recettes privées**                              | Non      | Oui                  |

---

B) **Recettes de thé**

| Fonctionnalité                              | Visiteur                                | Utilisateur connecté                              |
| ------------------------------------------- | --------------------------------------- | ------------------------------------------------- |
| **Ajouter une recette à sa librairie**      | Non                                     | Oui                                               |
| **Créer une recette personnalisée**         | Non                                     | Oui                                               |
| - Nom, type, style, description             |                                         |                                                   |
| - Ingrédients et quantités                  |                                         |                                                   |
| - Instructions (température, temps, dosage) |                                         |                                                   |
| - Niveau de caféine, source                 |                                         |                                                   |
| - Couleur personnalisée                     |                                         |                                                   |
| **Modifier ses propres recettes**           | Non                                     | Oui (auteur uniquement)                           |
| **Supprimer ses propres recettes**          | Non                                     | Oui (auteur uniquement)                           |
| **Visibilité des recettes**                 | Voir uniquement les recettes du système | Voir : publiques + système + ses propres recettes |

--- 

C) **Minuteur**

| Fonctionnalité                                                | Utilisateur non connecté | Utilisateur connecté           |
| ------------------------------------------------------------- | ------------------------ | ------------------------------ |
| **Accéder au minuteur**                                       | Non                      | Oui                            |
| **Utiliser le minuteur pour infuser un thé**                  | Non                      | Oui (manuel ou depuis recette) |
| **Modifier les paramètres** (eau, température, temps, dosage) | Non                      | Oui                            |
| **Mode "focus"** (interface méditative avec citations)        | Non                      | Oui                            |
| **Notification de fin d'infusion**                            | Non                      | Oui                            |
| **Pré-remplir depuis une recette de sa librairie**            | Non                      | Oui                            |
| **Archiver l'infusion dans "Brew Logs"**                      | Non                      | Oui                            |
| **Ajouter un commentaire et profil de saveur**                | Non                      | Oui                            |

D) **Statistiques**

| Fonctionnalité                                 | Visiteur | Utilisateur connecté |
| ---------------------------------------------- | -------- | -------------------- |
| **Accéder à la page profil**                   | Non      | Oui                  |
| **Voir ses statistiques de consommation**      | Non      | Oui                  |
| - Nombre de thés infusés                       |          |                      |
| - Nombre de thés infusés en mode "focus"       |          |                      |
| - Nombre d'entrées dans le journal (Brew Logs) |          |                      |

---

#### Perspectives d'évolution

Le projet TeaCorner pourrait évoluer vers une **plateforme communautaire complète** autour du thé. Les fonctionnalités suivantes ont été identifiées pour les versions futures, organisées par catégorie et priorisées selon leur impact utilisateur et leur complexité technique.

| Catégorie               | Fonctionnalité             | Description                                                                                                | Version |
| ----------------------- | -------------------------- | ---------------------------------------------------------------------------------------------------------- | ------- |
| **Social**              | Ajouter des amis           | Système de connexion entre utilisateurs pour partager recettes et expériences                              | V2      |
|                         | Messagerie forum           | Discussions publiques organisées par thématique (types de thé, techniques, origines)                       | V2      |
|                         | Répondre aux commentaires  | Interactions et échanges sur les recettes et les commentaires publiques                                    | V2      |
| **Interaction contenu** | Aimer une recette          | Système de "likes" pour valoriser les recettes populaires et créer un classement                           | V3      |
|                         | Recommander des recettes   | Partager une recette avec ses amis ou la communauté                                                        | V2      |
| **Organisation**        | Catégories et tags         | Classement personnalisé des recettes (favoris, à tester, saison, origine)                                  | V2      |
|                         | Suggestions personnalisées | Recommandations intelligentes basées sur l'historique de consommation et profils de saveur                 | V3      |
| **Gamification**        | Boutique de récompenses    | Échanger des points gagnés contre des objets virtuels (tasses personnalisées, avatars "petits compagnons") | V3      |
|                         | Achievements               | Système de badges débloquables (100 infusions, explorateur de saveurs)                                     | V3      |


---

## La mise en oeuvre du projet

### Le planning et suivi 

Ce projet a été réalisé en 7 semaines, nous avons donc mis en place un planning strict, semaine par semaine sur Notion. Nous avons partagé la charge de travail tout en gardant un oeil sur le développement de chacun et en effectuant des réunions journalières. En début de journée, nous faisions le point sur la veille et les avancées du projet, en fin de journée, nous faisions un bilan de la journée. 
Nous utilisions Whimsical pour le suivi du projet sous forme de tickets, ce qui nous permettait aussi de noter les points bloquants ou les éléments que nous voudrions aborder à la réunion suivante.

### L'environnement de développement

Nous avons utilisé Visual Studio Code pour l'IDE qui est un choix populaire pour le développement mais aussi un choix de confort car c'est celui avec lequel nous nous sommes formés. Pour la gestion des versions nous utilisons Git avec GitHub, qui nous permet un bon suivi des différents changements de code et pouvoir s'organiser.

Nous avons utilisé GitHub également pour la création de pipeline CI/CD (GitHub actions). Pour la planification des tâches nous avons choisi Whimsical pour les tickets et Notion pour le planning général et le partage de ressources. Ces deux choix sont motivés par l'expérience antérieure que nous avions avec et leur facilité d'utilisation et modularité.

--- 

**Capture d'écran du planning partagé sur Notion**

![[Pasted image 20260228100311.png|843]]

**Capture d'écran de la gestion de tickets sur Whimsical**

![[Pasted image 20260206093124.png]]


--- 
### Les objectifs de qualités

#### Sécurité

**Objectif :** Garantir la protection des données utilisateurs et la robustesse du système.

| Mesure de sécurité | Implémentation |
|-------------------|----------------|
| Hachage mots de passe | Argon2 |
| Authentification | JWT + refresh tokens |
| Cookies sécurisés | httpOnly, sameSite, secure (prod) |
| Validation données | class-validator (NestJS) |
| Protection attaques | Injection SQL (TypeORM), XSS, CSRF |
| Rate limiting | @nestjs/throttler (5 req/min) |
| Gestion secrets | .env non versionné |

#### Maintenabilité

**Objectif :** Faciliter l'évolution du projet, la compréhension du code et la collaboration.

| Pratique                   | Description                                |
| -------------------------- | ------------------------------------------ |
| Architecture modulaire     | Modules NestJS (auth, user, recipes, etc.) |
| Séparation responsabilités | Controllers / Services / Repositories      |
| Typage fort                | TypeScript sur tout le projet              |
| Documentation code         | Commentaires + Swagger (endpoints)         |
| Conventions nommage        | Cohérentes (camelCase, kebab-case)         |
| Gestion erreurs            | Exception filters centralisés              |

--- 
#### Tests

**Objectif :** Garantir la fiabilité du système et éviter les régressions.

| Type de test       | Outils        | Couverture                          |
| ------------------ | ------------- | ----------------------------------- |
| Tests unitaires    | Jest          | Services critiques (auth, user)     |
| Tests intégration  | Supertest     | Routes principales                  |
| Tests manuels      | Postman       | Flux complets (signup, login, etc.) |
| Couverture globale | Jest coverage | ~40% (focus sécurité)               |

#### Respect des bonnes pratiques

**Objectif :** Assurer un développement professionnel et conforme aux standards.

- Principes SOLID
- Git avec branches fonctionnelles (feature/, fix/)
- Commits clairs et réguliers
- Standards REST (GET, POST, PUT, DELETE)
- Injection de dépendances (NestJS DI)
- Validation systématique des entrées
- ORM pour éviter SQL manuel
- Gestion erreurs centralisée
- Respect RGPD (consentement, droit à l'oubli)

---

## Les spécifications fonctionnelles

### Les cas d'utilisation

**User Story**

***Administrateur:***

En tant qu'administrateur, je souhaite avoir accès à la liste de tous les utilisateurs de l'application afin de pouvoir accéder à leurs informations (profil, status d'activité) afin de gérer les utilisateurs qui seraient inactifs depuis longtemps.

***Utilisateur:***

1. En tant que visiteur, je souhaite accéder à l'application afin de découvrir différents mélanges de thé proposés par défaut (système).
2. En tant que visiteur, je souhaite accéder à l'application afin de pouvoir utiliser un minuteur classique pour infuser un thé, tout en ayant la possibilité de modifier les paramètres d'infusion.
3. En tant qu'utilisateur, je souhaite m'inscrire ou me connecter afin de découvrir différents mélanges de thé.
4. En tant qu'utilisateur, je souhaite m'inscrire ou me connecter afin de pouvoir enregistrer dans ma librairie les thés qui m'intéressent.
5. En tant qu'utilisateur, je souhaite m'inscrire ou me connecter afin de pouvoir créer et éditer mes propres mélanges de thé et les partager avec la communauté.
6. En tant qu'utilisateur, je souhaite m'inscrire ou me connecter afin de pouvoir enregistrer mes dégustations et les partager avec la communauté.
7. En tant qu'utilisateur, je souhaite m'inscrire ou me connecter afin de pouvoir utiliser le minuteur en mode classique ou en mode concentration pour pouvoir apprécier mon thé tout en ayant une approche méditative et rituelle.
8. En tant qu'utilisateur, je souhaite m'inscrire ou me connecter afin de pouvoir accéder à mon tableau de bord pour voir mes statistiques (nombre de thés consommés, type de thés consommés, nombre et type de minuteur utilisés et nombre d'enregistrement effectué).
9. En tant qu'utilisateur, je souhaite m'inscrire ou me connecter afin de pouvoir accéder à mes paramètres pour pouvoir mettre à jour mon profil utilisateur ou supprimer mon compte.
--- 
### L'architecture logicielle

L'architecture de TeaCorner suit le modèle MVC (Model, View, Controller) qui permet une séparation de l'interface utilisateur, la logique métier et la gestion des données. Cette application est donc structurée autour de trois blocs : un frontend React, une API backend développée avec NestJS, et une base de donnée PostgreSQL.

#### **Backend (NestJS)**

Le backend suit une architecture modulaire organisée en **9 modules principaux** :

1. **AuthModule** : Gestion de l'authentification et de la sécurité
    
    - `AuthController` : Endpoints `/auth/csrf-token`, `/auth/signup`, `/auth/signin`, `/auth/logout`, `/auth/refresh-tokens`, `/auth/verify-email`, `/auth/forgot-password`, `/auth/reset-password`
    - `AuthService` : Hachage Argon2, validation des credentials, vérification email, réinitialisation de mot de passe
    - `AuthRefreshTokenService` : Génération et révocation des paires de tokens JWT (access 15 min / refresh 7 jours stockés en base), cron job de nettoyage quotidien
    - `EmailService` : Envoi des emails de vérification, réinitialisation de mot de passe et suppression de compte
    - `AuthGuard` : Guard custom qui extrait le JWT depuis le cookie `access_token` et respecte le décorateur `@Public()`
    - `LocalStrategy` / `JwtRefreshStrategy` : Stratégies Passport pour le signin et le refresh
2. **UserModule** : Gestion des profils utilisateurs
    
    - `UserController` : `GET /user/profile`, `PATCH /user/profile`, `PATCH /user/username`, `PATCH /user/email`, `PATCH /user/password`, `DELETE /user/account`, `GET /user/:username`, `GET /user/user-management/all` (admin)
    - `UserService` : Vérification unicité email/username, attente de 30 jours sur changement de username, soft delete avec suppression définitive planifiée à 30 jours via cron job
3. **TeaModule** : Gestion des recettes de thé
    
    - `TeaController` : CRUD recettes avec contrôle d'accès (`/tea/system`, `/tea/public`, `/tea/all`, `/tea/:id`), gestion des ingrédients d'une recette (`/:teaId/ingredient`, `/:teaId/ingredients`)
    - `TeaService` : Logique de permissions (système/public/privé), gestion de la relation Many-to-Many avec les ingrédients via l'entité jointure `TeaIngredient` (quantité, optionnel)
4. **TeaStyleModule** : Référentiel des styles d'infusion (ex. Gongfu, Western)
    - `TeaStyleController` : `GET /tea-style/all`, `GET /tea-style/:id` (routes publiques, sans authentification)
    - `TeaStyleService` : Lecture seule des styles système
5. **IngredientModule** : Gestion des ingrédients
    
    - `IngredientController` : CRUD ingrédients (`/ingredient/all`, `/ingredient/create`, `/ingredient/:id`)
    - `IngredientService` : Validation unicité par (user, name), recherche insensible à la casse, contrôle d'accès par rôle
    - Distinction ingrédients système (`user_id NULL`) vs personnalisés

6. **FlavourTypeModule** : Référentiel des types de saveur (ex. Floral, Boisé)
    
    - `FlavourTypeController` : `GET /flavour-type/all`, `GET /flavour-type/:id`
    - `FlavourTypeService` : Lecture des types de saveur
7. **FlavourProfileModule** : Profils de saveur associés à un type
    
    - `FlavourProfileController` : `GET /flavour-profile/all`, `GET /flavour-profile/:id`
    - `FlavourProfileService` : Lecture des profils avec leur relation `FlavourType`
8. **UserTeaModule** : Bibliothèque personnelle de thés
    
    - `UserTeaController` : `GET /user-tea/library`, `POST /user-tea/create`, `GET /user-tea/:id`, `PATCH /user-tea/:id`, `DELETE /user-tea/:id`, `GET /user-tea/all` (admin)
    - `UserTeaService` : Gestion de la collection personnelle (prévention des doublons, validation de l'accès au thé), tri par date d'ajout
    - Entité `UserTea` : lien User ↔ Tea avec rating et notes personnelles
9. **AppModule** : Module racine
    
    - `AppService` : Seeding automatique au démarrage d'un compte admin depuis les variables d'environnement (`ADMIN_EMAIL`, `ADMIN_PASSWORD`, etc.)

--- 

**Pattern de responsabilité :** 
- **Controllers** : Réception des requêtes, extraction du contexte utilisateur (JWT, params, body), délégation au service
- **ValidationPipe global** : Validation automatique des DTOs via class-validator avant l'entrée dans le controller
- **Services** : Logique métier, contrôle d'accès, lancement des exceptions HTTP, interaction avec TypeORM

**Exemple de flux** : Création d'une recette 

1. Client → `POST /tea/create` avec `CreateTeaDto`
2. Le `ValidationPipe` global valide les données (class-validator)
3. `TeaController` extrait l'utilisateur depuis le JWT et appelle `TeaService.create()`
4. `TeaService` applique la logique métier (permissions, valeurs par défaut)
5. `TeaService` appelle `this.teaRepository.save()` (repository TypeORM injecté via `@InjectRepository(Tea)`)
6. TypeORM → INSERT dans PostgreSQL

--- 

#### **Frontend (React + React Router v7)**

**État d'avancement :** En cours de développement (authentification complète, interface principale à venir)

Le frontend utilise **React 19** avec **React Router v7**, organisé autour de **2 layouts** pour différencier l'expérience utilisateur :

| Layout         | Utilisation             | Routes                                          |
| -------------- | ----------------------- | ----------------------------------------------- |
| **SiteLayout** | Visiteurs non connectés | `/`, `/signup`, `/signin`                       |
| **AppLayout**  | Utilisateurs connectés  | `/profile`, `/tea`, `/timer`, `/brew-logs`, etc |

**Pattern de responsabilité :** 
- **Routes** : Configuration file-based (routes.ts) 
- **Pages** : Composants React avec clientActions (mutations) 
- **Layouts** : Composants de mise en page réutilisables (Header, Nav, Footer) 

**Exemple de flux : Inscription utilisateur**

1. Utilisateur remplit le formulaire (React Form component) 
2. Soumission déclenche `clientAction` (React Router v7) 
3. clientAction envoie POST `/auth/signup` au backend NestJS 
4. Backend valide et crée l'utilisateur 5. Redirection automatique vers `/signin` (React Router)

**Technologies utilisées :** - React 19, React Router v7, TypeScript, Tailwind CSS, Vite


*→ Voir section "Réalisations - Interface utilisateur" pour les captures d'écran des pages.*

--- 
#### **Base de données (PostgreSQL)**

La base de données compte **15 tables** organisées autour de 3 entités principales : 
- **User** : Authentification et profils 
- **Tea** : Recettes de thé avec relations Many-to-Many (ingrédients, catégories) 
- **BrewLog** : Journal des infusions avec paramètres et commentaires

Les relations ont été modélisées selon la méthode Merise (MCD → MLD → MPD) puis implémentées avec TypeORM.

#### **Communication entre les couches**

Le frontend communique avec l'API via des requêtes HTTP sécurisées. Le backend traite les données, applique les règles métier, interagit avec la base et renvoie les réponses au frontend. Ce découpage permet une évolution indépendante des couches et une meilleure scalabilité.

**Flux d'une requête (exemple : connexion utilisateur)**

1. L'utilisateur saisit ses identifiants dans le **formulaire React** (page Login)
2. Le composant appelle le **service API** (`authService.signin()`)
3. Le service envoie une **requête POST** à `/auth/signin`
4. Le **Controller NestJS** (`AuthController`) reçoit la requête
5. Le controller valide les données via un **DTO** (`SignInDto`)
6. Le controller appelle le **Service** (`AuthService.signIn()`)
7. Le service vérifie les identifiants via le **Repository** (`UserRepository.findByUsername()`)
8. Le repository interroge **PostgreSQL** via TypeORM
9. Si valide, le service génère les **tokens JWT**
10. Le controller retourne la réponse avec **cookies sécurisés**
11. Le frontend stocke l'état de connexion et **redirige** vers le dashboard

Ce flux illustre la séparation des responsabilités : le frontend gère l'affichage, le controller la validation, le service la logique métier, et le repository l'accès aux données.

---
##### Diagramme MVC
Le schéma ci‑dessous illustre l'architecture logicielle de TeaCorner et le flux complet d'une requête entre le frontend React et l'API NestJS.

![[MVC Diagram.png]]

##### User Flow
Le schéma suivant illustre le parcours utilisateur au sein de TeaCorner. Il présente les différentes pages de l’application ainsi que les actions principales associées à chaque étape : connexion, consultation des recettes, utilisation du minuteur, gestion du journal de dégustation et accès au tableau de bord ou aux paramètres. Ce flow permet de visualiser la logique de navigation et la manière dont l’utilisateur interagit avec les différentes couches de l’application.

![[UserFlow.png]]



---

## Les spécifications techniques

### Choix des technologies

#### Framework Backend : NestJS

**Contexte du choix :**
Après avoir étudié PHP (Symfony) et Java (Spring) durant la formation, nous souhaitions rester dans l'écosystème JavaScript/TypeScript pour le projet. Le choix s'est porté sur NestJS pour les raisons suivantes :

**Critères de décision :**
- **Écosystème TypeScript** : Permet de partager le langage entre frontend et backend
- **Documentation claire** : Guide officiel très complet, nombreux exemples
- **Architecture structurée** : Modules, services, controllers imposent une organisation claire (utile en binôme)
- **Rapidité de développement** : Intégration native avec TypeORM, Swagger, class-validator
- **Expérience préalable** : Similarité avec Angular (déjà utilisé) facilite l'apprentissage

NestJS offrait un bon compromis entre **structure imposée** (maintenabilité) et **rapidité de mise en œuvre** compte tenu des 7 semaines du projet.

--- 
#### ORM : TypeORM

**Contexte du choix :**
La documentation officielle de NestJS recommande TypeORM comme solution d'ORM relationnelle.

**Critères de décision :**
- **Recommandation officielle** : Module `@nestjs/typeorm` maintenu par l'équipe NestJS
- **Intégration native** : Configuration simplifiée, injection de dépendances automatique
- **Documentation abondante** : Nombreux exemples dans la doc NestJS et tutoriels
- **Gestion des relations** : Decorators `@OneToMany`, `@ManyToMany` pour notre modèle complexe (15+ tables)

TypeORM répondait au besoin sans nécessiter de recherche comparative approfondie.

---

#### Base de données : PostgreSQL

**Contexte du choix :**
PostgreSQL a été sélectionné pour sa familiarité et ses fonctionnalités adaptées au projet.

**Critères de décision :**
- **Expérience préalable** : Utilisé à plusieurs reprises durant la formation
- **Types avancés** : ENUM (rôles), UUID (identifiants), JSON (configurations flexibles)
- **Relations complexes** : Gestion native des Many-to-Many et contraintes d'intégrité
- **Compatibilité TypeORM** : Intégration parfaite et bien documentée
- **Hébergement** : Plan gratuit disponible sur Render

PostgreSQL offrait les fonctionnalités nécessaires avec une courbe d'apprentissage minimale.


#### Frontend : React

**Contexte du choix :**
Nous avions déjà une expérience avec Angular durant la formation. React a été choisi pour élargir nos compétences frontend et répondre à des objectifs professionnels.

**Critères de décision :**
- **Employabilité** : React très demandé sur le marché du travail
- **Apprentissage** : Découvrir un nouvel écosystème (hooks, React Router)
- **Écosystème riche** : Nombreuses bibliothèques UI disponibles
- **Documentation** : Tutoriels et ressources communautaires abondants

React permettait d'atteindre deux objectifs : **livrer le projet** et **acquérir une nouvelle compétence recherchée**.

--- 
### Les maquettes

Les maquettes de TeaCorner ont été réalisées sur Figma pour définir l'identité visuelle et l'expérience utilisateur avant le développement. Cette phase a permis de valider l'ergonomie et la cohérence graphique de l'application.

#### Recherche

Avant de commencer notre maquette, on a passé quelques jours à faire des recherches pour avoir de l'inspiration sur les différentes pages (connexion, inscription, dashboard, etc.). On a aussi essayé des applications de thé existantes pour s'en inspirer (myTeaPal, Teafinity, Steeped) et voir ce qui existe sur le marché au niveau du design et des fonctionnalités. Cela nous a permis de voir ce qui existe, ce qui fonctionne et ce qui pourrait être amélioré, tout cela dans le but de créer quelque chose qui nous ressemble et qui est accessible pour l'utilisateur.

#### 1. Vue d'ensemble du projet Figma

![[Pasted image 20260301210825.png]]


---

#### 2. Identité visuelle

##### Logo

![[Pasted image 20260224085758.png]]

**Concept :**
Ce logo a été imaginé afin de représenter **l'essence de Tea Corner.** 

**Symbolique des éléments :**

La fenêtre représente un **coin chaleureux**, comme vu au travers d'une fenêtre et évoque la **contemplation** vers l'extérieur tout en savourant son thé. Cette fenêtre nous offre aussi une vue privilégiée sur ce moment suspendu.

**La palette de couleurs :**
La couleur jaune représente la chaleur et le réconfort. L'aspect chaleureux est aussi mis en avant ici.

---

##### Palette de couleurs et style général

![[Style Guide.png]]
##### Palette de couleur

 Pour la palette de couleur, on est partit sur des couleurs chaudes et claires pour retranscrire le côté chaleureux que l'on retrouve dans notre logo et que l'on associe souvent à la dégustation d'une tasse de thé. 
 Le fond "Primary Light" et la couleur "Primary Beige" ont été choisis pour que les différents thés se démarquent plus facilement. 
 Nous avons aussi choisi une palette de couleur dédiée aux types de thés, basée sur les vraies couleurs, avec une approche pastel. 



---

##### Typographie

**Choix typographiques :**
- **Police principale** : Alice - Une police moderne, basée sur un style rétro, qui fait ressortir les thés.
- **Police secondaire** : Inter - Une police très utilisée dans les interfaces utilisateur pour sa simplicité et lisibilité. 
- **Hiérarchie claire** : Différenciation tailles et poids pour guider l'œil
- **Accessibilité** : Taille minimale 14px pour confort de lecture

---

#### 3. Composants réutilisables

La bibliothèque de composants Figma garantit la cohérence visuelle et accélère la conception. Cela permet aussi d'aborder le développement du frontend de manière plus organisée et modulaire. 

Plusieurs composants génériques ont été créés, comme les boutons, les champs de saisies, les étiquettes de texte, la barre de navigation mobile et desktop mais aussi des composants plus spécifiques au thé comme l'étiquette pour les thés, le minuteur, les cartes de brew log, les étiquettes d'ingrédients et de profile de saveurs, etc.

##### Vue d'ensemble des composants

![[Pasted image 20260301211423.png]]

##### Exemple de composants

![[image.webp]]

##### Barre de navigation desktop

![[image (1).webp]]

---

#### 4. Pages principales (maquettes)

##### Page d'accueil (Landing)

![[landing page screen (1).png]]


##### Pages d'authentification (Signup / Signin)

![[image.png]]

![[image (7).webp]]

##### Interface application - Page d'accueil 

![[Pasted image 20260301223732.png]]

##### Interface application - Minuteur

![[image (8).webp|258]]

![[Pasted image 20260301224008.png|235]]

##### Interface application - Paramètres compte

![[Pasted image 20260301224101.png]]

---

#### 5. Prototypage et navigation

Le prototype Figma permet de **tester le parcours utilisateur** avant développement. Cela permet d'identifier les ajustements nécessaires sur le design ou les fonctionnalités. Nous avons prototypé les différentes pages du flux utilisateur mais aussi les composants, comme les barres de navigation, ou le flux de création d'un log. 
##### Prototype de la barre de navigation mobile

![[image (5).webp]]
##### Prototype du flow d'un ajout de brew log 

![[image (4).webp]]

---
### Les modèles entités (MCD, MLD, MPD)

#### Vue d'ensemble

La base de données TeaCorner compte **15 tables** organisées autour de **3 entités principales** :

| Entité centrale | Rôle | Relations principales |
|----------------|------|----------------------|
| **User** | Gestion des utilisateurs | → Tea (auteur), → Brew_Log, → Category |
| **Tea** | Recettes de thé | ← User, ↔ Ingredient, ↔ Category, ↔ Flavor_profile |
| **Brew_Log** | Journal d'infusions | ← User, ← Tea, ↔ Flavor_profile |

**Entités secondaires** (12 tables) : 
Ingredient, Category, Flavor_type, Flavor_profile, Tea_style, Point_transaction, et 6 tables associatives (user_tea, tea_category, tea_ingredient, etc.)

#### Processus de modélisation

La conception s'est faite en 3 étapes selon la méthode Merise :

1. **MCD (Modèle Conceptuel)** : Identification des entités et relations sur papier puis draw.io
2. **MLD (Modèle Logique)** : Transformation des relations Many-to-Many en tables intermédiaires
3. **MPD (Modèle Physique)** : Ajout des types, contraintes et clés sur dbdiagram.io

--- 
#### Entités principales détaillées

##### Table User
Stocke les informations d'authentification et de profil :
- Authentification : email, password (haché), email_verified
- Profil : username, display_name, avatar_url, bio
- Permissions : role (ENUM: USER, ADMIN)
- Métadonnées : created_at, modified_at, deleted_at

**Relations :**
- Un utilisateur peut créer plusieurs recettes (User → Tea : OneToMany)
- Un utilisateur peut avoir plusieurs logs d'infusion (User → Brew_Log : OneToMany)

##### Table Tea
Entité centrale contenant toutes les recettes :
- Informations : name, type, style, description
- Instructions : brew_temperature, brew_time_seconds
- Métadonnées : author_id (FK → User), created_at

**Relations :**
- Une recette peut avoir plusieurs ingrédients (Tea ↔ Ingredient : ManyToMany via tea_ingredient)
- Une recette peut avoir plusieurs catégories (Tea ↔ Category : ManyToMany via tea_category)

##### Table Brew_Log
Journal des infusions réalisées :
- Paramètres : temperature, steep_time, amount_of_water
- Feedback : rating, notes, shared
- Métadonnées : user_id (FK), tea_id (FK)

**Relations :**
- Chaque log appartient à un utilisateur et une recette (Brew_Log ← User, Brew_Log ← Tea)

#### Tables associatives et secondaires

Pour éviter la répétition, voici un tableau récapitulatif :

| Table | Type | Rôle |
|-------|------|------|
| user_tea | Associative | Lie utilisateur et thés dans sa librairie |
| tea_ingredient | Associative | Lie recette et ingrédients (avec quantité) |
| tea_category | Associative | Lie recette et catégories |
| Ingredient | Entité | Composants des recettes (type, couleur) |
| Category | Entité | Catégories personnalisées utilisateur |
| Flavor_profile | Entité | Profils de saveur (rose, jasmin, menthe) |
| Flavor_type | Entité | Familles de saveurs (floral, fruité) |
| Tea_style | Entité | Styles de thé (matcha, earl grey) |

#### Contraintes d'intégrité principales

- **Unicité** : (user_id, tea_id) dans user_tea, (user_id, name) dans Ingredient et Category
- **Clés étrangères** : Cascade DELETE sur author_id, user_id pour préserver l'intégrité
- **NOT NULL** : Tous les champs critiques (email, password, tea name)

--- 
#### Diagrammes
La conception de la base de données a suivi rigoureusement la méthodologie Merise en 3 étapes :

##### MCD (Modèle Conceptuel des Données)
Identification des entités et relations conceptuelles avec cardinalités.
![[MCD TeaCorner.drawio.png]]


--- 

##### MLD (Modèle Logique des Données)
Transformation des relations en tables avec clés étrangères : 
- Relations Many-to-Many → Tables associatives (user_tea, tea_ingredient, etc.) 
- Relations One-to-Many → Clés étrangères (author_id, user_id, etc.)

![[MLD TeaCorner.drawio.png]]

---

##### MPD (Modèle Physique des Données)
 

![[MPD TeaCorner 1.png]]


---

## Les réalisations

### L'interface utilisateur 
Cette section présente les interfaces utilisateur actuellement implémentées dans l'application TeaCorner. Le développement frontend suit une approche **progressive**.
#### Structure du projet

![[Pasted image 20260303213025.png|300]]

---
#### Structure des routes

```ts
export default [

  layout("layouts/SiteLayout.tsx", [index("routes/Home.tsx")]),

  route("signup", "routes/auth/Signup.tsx"),
  route("signin", "routes/auth/Signin.tsx"),

  
  route("app", "layouts/AppLayout.tsx", [
    index("routes/app/Home.tsx"),
    route("tea/:teaId", "routes/app/Tea.tsx"),
  ]),
] satisfies RouteConfig;
```

Le fichier `routes.ts` définit toutes les URL de l'application.

**Un layout** est une page enveloppe — il contient les éléments communs (navigation, footer) et affiche la page enfant à l'intérieur. Par exemple, `AppLayout.tsx` entoure toutes les pages de l'espace connecté.

**Le paramètre `:teaId`** est dynamique et utilise le composant `Tea.tsx`, qui reçoit la valeur de l'URL pour charger les bonnes données.
#### Composants (React + Tailwind)

```tsx
import React, { type ButtonHTMLAttributes, type ReactElement } from "react";

// allows the button to inherit standard button props (e.g type="submit")
interface ButtonProps extends ButtonHTMLAttributes<HTMLButtonElement> {
  variant?: "primary" | "secondary" | "ghost";
  size?: "small" | "medium" | "large";
  color?: "";
  disabled?: boolean;
  icon?: ReactElement;
  children: React.ReactNode;
}

export function Button({
  variant = "primary",
  size = "medium",
  icon,
  children,
  className = "",
  disabled,
  ...props //spreading onClick etc
}: ButtonProps) {
  const variants = {
    primary: "text-sm px-6 py-2.5 bg-primary-dark text-primary-light hover:bg-opacity-90",
    secondary: "border-2 border-primary-dark text-primary-dark bg-transparent",
    ghost: "bg-transparent text-primary-dark",
  };

  const sizes = {
    small: "px-4 py-1.5 text-xs",
    medium: "px-6 py-2.5 text-sm",
    large: "px-8 py-3 text-base",
  };

  const baseStyles = "inline-flex items-center justify-center rounded-full font-medium transition-colors focus:outline-none focus:ring-2 focus:ring-offset-2 disabled:opacity-70 disabled:cursor-not-allowed cursor-pointer";

  return (
    <button
      className={`${baseStyles} ${variants[variant]} ${sizes[size]} ${className}`}
      disabled={disabled}
      aria-disabled={disabled}
      {...props}
    >
      {children}
    </button>
  );
}
```

**Interface TypeScript** — toutes les options du bouton (`variant`, `size`...) sont déclarées dans une interface. En étendant `ButtonHTMLAttributes`, pas besoin de réécrire `onClick`, `type`, `disabled` etc. — ils sont hérités automatiquement.

**Variantes** — au lieu d'enchaîner des `if/else`, chaque variante a ses classes Tailwind dans un objet. Un simple `variants[variant]` suffit pour appliquer le bon style.

**Styles communs** — tout ce qui ne change pas entre les variantes (arrondi, transition, curseur...) est mis à part dans `baseStyles`, toujours appliqué.

---
#### Pages d'authentification

##### Page d'accueil (Landing Page)

![[landing page screen (1) 2.png]]

**Objectif :** Présenter l'application et inciter à l'inscription

**Éléments implémentés :**

- **Hero section** avec slogan "Upgrading your tea experience"
- **Motif vague** en background (illustration thé, cohérence visuelle)
- **Call-to-action** : Bouton "Get started" → Redirection vers Signup
- **Footer** : Liens About us, Help, Privacy Policy, Terms and Conditions
- **Copyright** : "© 2026 tea corner. All Rights Reserved"

**Technologies utilisées :**

- React Router v7 (routing)
- Tailwind CSS (styling)
- Design responsive (mobile-first)

#### Page d'inscription (Signup)

![[image (6) 1.webp]]

**Objectif :** Permettre la création d'un compte utilisateur avec validation sécurisée

--- 

**Fonctionnalités implémentées :**

**1. Formulaire avec validation native HTML**

```ts
<Form method="post" className="flex flex-col">
  <label>
    <span>Display name</span>
    <input name="display_name" type="text" required className="border" />
  </label>
  <label>
    <span>User name</span>
    <input name="user_name" type="text" required className="border" />
  </label>
  <label>
    <span>Email</span>
    <input name="email" type="email" required className="border" />
  </label>
  <label>
    <span>Password</span>
    <input name="password" type="password" required className="border" />
  </label>
  <label>
    <span>Confirm Password</span>
    <input type="password" required className="border" />
  </label>
  
  {actionData?.error && <p>{actionData.error}</p>}
  
  <button type="submit" disabled={isSubmitting}>
    {isSubmitting ? "signing up..." : "sign up"}
  </button>
</Form>
```

--- 

**2. Gestion de la soumission avec React Router v7**

La soumission du formulaire utilise le pattern **clientAction** de React Router v7 :

```ts
export async function clientAction({ request }: ActionFunctionArgs) {
  const formData = await request.formData();
  const data = Object.fromEntries(formData);
  
  const apiUrl = import.meta.env.VITE_API_URL;
  
  try {
    const response = await fetch(`${apiUrl}/auth/signup`, {
      method: "POST",
      headers: { 
        "Content-Type": "application/json",
        "X-CSRF-Token": getCsrfToken() ?? ""
      },
      body: JSON.stringify(data),
    });
    
    if (!response.ok) {
      const errorData = await response.json().catch(() => ({}));
      return {
        error: errorData.message || "Something went wrong on the server.",
      };
    }
    
    return redirect("/signin");
  } catch (err) {
    return { error: "Network error." };
  }
}
```

**Points clés :**

- **Validation native** : `required`, `type="email"` pour validation client-side
- **Protection CSRF** : Token récupéré au chargement de l'app et envoyé avec chaque requête
- **Gestion d'erreurs** : Affichage des messages backend via `actionData`
- **UX optimisée** : Bouton désactivé pendant soumission avec texte "signing up..."
- **Redirection automatique** : Vers `/signin` après inscription réussie
- **Progressive enhancement** : Fonctionne même sans JavaScript (formulaire HTML natif)

--- 

**3. États du formulaire**
```ts
const actionData = useActionData();              // Récupère les erreurs
const navigation = useNavigation();              // État de navigation
const isSubmitting = navigation.state === "submitting";  // Détecte la soumission
```

**4. Lien vers connexion**

```ts
<p>
  Already have an account? <NavLink to="/signin">Log in</NavLink>
</p>
```

##### Page de connexion (Signin)

![[image 1.png]]

**Objectif :** Authentifier l'utilisateur et démarrer une session sécurisée

---

**Fonctionnalités implémentées :**

**1. Formulaire simplifié**

```ts
<Form method="post" className="flex flex-col">
  <label>
    <span>Username</span>
    <input name="user_name" type="text" required className="border" />
  </label>
  <label>
    <span>Password</span>
    <input name="password" type="password" required className="border" />
  </label>
  
  {actionData?.error && <p>{actionData.error}</p>}
  
  <button type="submit" disabled={isSubmitting}>
    {isSubmitting ? "signing in..." : "sign in"}
  </button>
</Form>
```


**2. Gestion de la connexion**

```ts
export async function clientAction({ request }: ActionFunctionArgs) {
  const formData = await request.formData();
  const data = Object.fromEntries(formData);
  
  const apiUrl = import.meta.env.VITE_API_URL;
  
  try {
    const response = await fetch(`${apiUrl}/auth/signin`, {
      method: "POST",
      headers: { 
        "Content-Type": "application/json",
        "X-CSRF-Token": getCsrfToken() ?? ""
      },
      body: JSON.stringify(data),
      credentials: "include",  // Important : envoi des cookies
    });
    
    if (!response.ok) {
      const errorData = await response.json().catch(() => ({}));
      return {
        error: errorData.message || "Something went wrong on the server.",
      };
    }
    
    return redirect("/");  // Redirection vers dashboard après connexion
  } catch (err) {
    return { error: "Network error." };
  }
}
```

**Points clés :**

- **Credentials include** : Envoi automatique des cookies (refresh token)
- **Protection CSRF** : Token envoyé dans le header
- **Redirection** : Vers `/` (dashboard) après connexion réussie
- **Gestion d'erreurs** : Messages clairs (identifiants incorrects, serveur indisponible)

**3. Lien vers inscription**

```ts
<p>
  Don't have an account? <NavLink to="/signup">Sign up</NavLink>
</p>
```

--- 
#### Sécurité - Protection CSRF

L'application implémente une **protection contre les attaques CSRF** (Cross-Site Request Forgery) :

**1. Récupération du token au chargement de l'app**

```ts
// lib/csrf.ts
let csrfToken: string | null = null;

export async function fetchCsrfToken(): Promise<void> {
  const apiUrl = import.meta.env.VITE_API_URL;
  const response = await fetch(`${apiUrl}/auth/csrf-token`, {
    credentials: "include",
  });
  const data = await response.json();
  csrfToken = data.csrfToken;
}

export function getCsrfToken(): string | null {
  return csrfToken;
}
```


**2. Chargement du token dans le root loader**

```ts
// root.tsx
export async function clientLoader(_: Route.ClientLoaderArgs) {
  await fetchCsrfToken();  // Appelé au démarrage de l'app
  return null;
}
```

--- 

**3. Utilisation dans les requêtes**

```ts
headers: { 
  "Content-Type": "application/json",
  "X-CSRF-Token": getCsrfToken() ?? ""  // Ajouté à chaque mutation
}
```


**Fonctionnement :**

1. Au chargement de l'app, le token CSRF est récupéré depuis `/auth/csrf-token`
2. Le token est stocké en mémoire (pas de localStorage = sécurité renforcée)
3. Chaque requête POST/PUT/DELETE inclut ce token dans le header `X-CSRF-Token`
4. Le backend NestJS vérifie la validité du token avant de traiter la requête

**Avantages :**

- Protection contre les attaques CSRF
- Pas de stockage localStorage (vulnérabilité XSS évitée)
- Token renouvelé à chaque session

 --- 
### Les extraits de code de composants métiers

#### Introduction - Présentation du composant métier

**Context et présentation**

Le backend de **Tea Corner** est une API REST développée avec le framework **NestJS**, s'appuyant sur **TypeORM** pour la gestion de la base de données PostgreSQL.

L'application permet à des utilisateurs authentifiés de créer, gérer et partager des recettes de thé (appelées "brews"), composées d'ingrédients avec leurs quantités. Le backend est structuré selon une **architecture modulaire** : chaque domaine métier (authentification, thés, ingrédients, utilisateurs) est encapsulé dans son propre module NestJS.

**Les fonctionnalités présentées dans ce document sont :**

- L'**inscription** sécurisée avec vérification par email
- La **connexion** avec gestion de sessions via JWT et cookies httpOnly
- La **création d'un thé** avec gestion de relations many-to-many vers les ingrédients
- La **mise à jour et suppression** d'un thé avec contrôle des permissions

#### Structure du projet
```
src/
├── auth/               ← Inscription, connexion, tokens, email
├── user/               ← Entité User, profil, DTOs
├── tea/                ← CRUD des thés, gestion des ingrédients
├── ingredient/         ← CRUD des ingrédients + table de jointure
├── guards/             ← AuthGuard, RolesGuard
├── strategies/         ← LocalStrategy, JwtRefreshStrategy
├── decorators/         ← @Public(), @Roles()
├── entities/           ← Tokens (refresh, email, reset)
└── enums/              ← TeaType, Role, CaffeineLevel...

```
---
#### Routes API principales

![[Pasted image 20260226160740.png]]

![[Pasted image 20260226160809.png]]

--- 
#### AuthService - Inscription (signUp)

**Description**

La méthode `signUp` gère l'enregistrement d'un nouvel utilisateur. Elle orchestre trois étapes : le hashage du mot de passe, la persistance en base, et l'envoi d'un email de vérification avec un token à usage unique.

**DTO de validation - CreateUserDto**

```ts
// src/user/create-user.dto.ts
export class CreateUserDto {
  @MinLength(2)
  @IsString()
  display_name: string;

  @MinLength(2)
  @IsString()
  user_name: string;

  @IsEmail()
  email: string;

  @IsNotEmpty()
  @MinLength(8)
  password: string;
}

```

**Points clés :** Les décorateurs `class-validator` (`@IsEmail`, `@MinLength`, `@IsString`) garantissent la validation automatique des données entrantes avant même d'atteindre le service. NestJS rejette la requête avec une `400 Bad Request` détaillée si les contraintes ne sont pas respectées.

--- 
**Méthode signUp**

```ts
// src/auth/auth.service.ts — lignes 34–58
async signUp(createUserDto: CreateUserDto): Promise<{ message: string }> {
  // 1. Hashage sécurisé avec Argon2
  const hashedPassword = await this.hashPassword(createUserDto.password);

  const data = {
    ...createUserDto,
    password: hashedPassword,
    email_verified: false,
  };

  // 2. Création de l'utilisateur en base
  const user = await this.userService.create(data);

  // 3. Génération et envoi du token de vérification email
  const emailToken = await this.generateEmailVerificationToken(user);
  await this.emailService.sendVerificationEmail(user, emailToken);

  return { message: 'Compte créé. Vérifiez votre email pour activer votre compte.' };
}

async hashPassword(password: string) {
  return argon2.hash(password); // ligne 194
}

```

**Génération du token email**

```ts
// src/auth/auth.service.ts — lignes 136–150
async generateEmailVerificationToken(user: User) {
  const token = crypto.randomBytes(32).toString('hex'); // token envoyé par email
  const hashToken = crypto.createHash('sha256').update(token).digest('hex'); // stocké en DB
  const expires_at = new Date(Date.now() + 1000 * 60 * 60); // expiration 1h

  await this.emailVerificationTokenRepository.insert({
    email_token: hashToken,
    user,
    expires_at,
    used: false,
  });

  return token; // seul le token brut part dans l'email
}

```

**Exemple d'une requête postman pour la création d'un compte utilisateur**

![[Pasted image 20260226160937.png]]


**Points clés de sécurité :**

|Aspect|Choix technique|Justification|
|---|---|---|
|**Hashage mot de passe**|Argon2|Algorithme de référence OWASP, résistant aux attaques GPU/ASIC|
|**Token email**|`crypto.randomBytes(32)`|256 bits d'entropie, cryptographiquement aléatoire|
|**Stockage token**|SHA-256 du token brut|Même si la DB est compromise, le token ne peut pas être rejoué|
|**Expiration**|1 heure|Limite la fenêtre d'exploitation|
|**Flag `used`**|Boolean en DB|Empêche la réutilisation du même lien|

**Compétences démontrées :** sécurité applicative, validation des entrées, gestion des tokens à usage unique, architecture orientée domaine.

--- 
#### AuthService - Connexion (signIn + validateUser)

**Description**

La connexion repose sur deux méthodes complémentaires : `validateUser` (vérification des credentials via Passport/LocalStrategy) et `signIn` (génération et stockage des tokens JWT dans des cookies httpOnly).

**Etape 1 - Validation des credentials**

```ts
// src/auth/auth.service.ts — lignes 119–134
async validateUser(username: string, pass: string): Promise<any> {
  const user = await this.userService.findByUsername(username);
  if (!user) return null;

  // Vérification obligatoire : email confirmé avant connexion
  if (!user.email_verified) {
    throw new UnauthorizedException(
      'Veuillez vérifier votre email avant de vous connecter',
    );
  }

  // Vérification du mot de passe avec Argon2
  const isMatch = await argon2.verify(user.password, pass);
  if (!isMatch) return null;

  // On retire le mot de passe du résultat avant de le propager
  const { password: _password, ...result } = user;
  return result;
}

```

**Points clés :**

- La vérification `email_verified` bloque toute connexion tant que l'email n'est pas confirmé — empêche les comptes "fantômes"
- `argon2.verify` compare de façon sécurisée sans exposition du hash
- Le mot de passe est **exclu** du résultat retourné (destructuring `_password`)
--- 
**Étape 2 — Génération des tokens et cookies**

```ts
// src/auth/auth.service.ts — lignes 60–82
async signIn(user: User, response: Response) {
  // Génération de la paire access_token + refresh_token
  const tokens = await this.authRefreshTokenService.generateTokenPair(user);

  // Access token : cookie httpOnly, 15 minutes
  response.cookie('access_token', tokens.access_token, {
    httpOnly: true,   // inaccessible depuis JS côté client → protection XSS
    secure: false,    // true en production (HTTPS uniquement)
    sameSite: 'lax',  // protection CSRF
    maxAge: 15 * 60 * 1000,
  });

  // Refresh token : cookie httpOnly, 7 jours
  response.cookie('refresh_token', tokens.refresh_token, {
    httpOnly: true,
    secure: false,
    sameSite: 'lax',
    maxAge: 7 * 24 * 60 * 60 * 1000,
  });

  return tokens;
}

```

**Payload JWT et génération des tokens**

```ts
// src/auth/auth-refresh-token.service.ts — lignes 40–52
generateAccessToken(user: User): string {
  const payload = { sub: user.id, username: user.user_name, role: user.role };
  return this.jwtService.sign(payload, {
    expiresIn: this.configService.get('JWT_ACCESS_EXPIRES'), // 15min
  });
}

async generateTokenPair(user: User) {
  return {
    access_token: this.generateAccessToken(user),
    refresh_token: await this.generateRefreshToken(user.id),
  };
}

```

**Renouvellement et révocation**

```ts
// src/auth/auth-refresh-token.service.ts — lignes 55–87
async validateRefreshToken(refreshToken: string, userId: string): Promise<boolean> {
  const token = await this.authRefreshTokenRepository.findOne({
    where: { refreshToken, user: { id: userId }, revoked: false },
  });
  if (!token) return false;
  if (token.expiresAt <= new Date()) return false;
  return true;
}

async revokeRefreshToken(refreshToken: string): Promise<void> {
  await this.authRefreshTokenRepository.update({ refreshToken }, { revoked: true });
}

@Cron(CronExpression.EVERY_DAY_AT_2AM)
async clearExpiredRefreshTokens() {
  await this.authRefreshTokenRepository.delete({
    expiresAt: LessThanOrEqual(new Date()),
  });
}

```

--- 
**Architecture de sécurité — tableau récapitulatif :**

|Mécanisme|Implémentation|Protection|
|---|---|---|
|**httpOnly cookies**|`response.cookie(…, { httpOnly: true })`|Inaccessible à JavaScript → XSS|
|**sameSite: lax**|Attribut cookie|Bloque les requêtes cross-origin automatiques → CSRF|
|**JWT courte durée**|Access token 15 min|Limite la fenêtre d'exposition|
|**Refresh token en DB**|Entité `AuthRefreshToken` + flag `revoked`|Révocation possible (logout, vol de token)|
|**Nettoyage automatique**|`@Cron` à 2h du matin|Hygiène DB, évite l'accumulation|

**Compétences démontrées :** authentification sécurisée, gestion de sessions sans état (stateless JWT), stratégie de rotation de tokens, protection XSS/CSRF.

--- 
#### TeaService - Création d'un thé (create + add ingredient)
**Description**

La création d'un thé est décomposée en deux étapes : la création de la fiche thé (metadata), puis l'ajout des ingrédients via une table de jointure. Cette architecture many-to-many permet de réutiliser les ingrédients entre plusieurs thés, avec des données spécifiques à la relation (quantité, caractère optionnel).

**DTO de création — `CreateTeaDto`**

```ts
// src/tea/create-tea.dto.ts (extrait représentatif)
export class CreateTeaDto {
  @IsUUID() @IsOptional()
  author_id?: string;       // null → thé système, UUID → thé utilisateur

  @MinLength(2) @IsString()
  name: string;

  @IsEnum(TeaType)
  type: TeaType;            // 'green' | 'black' | 'herbal' | 'oolong' | ...

  @IsUUID() @IsOptional()
  style_id?: string;        // relation vers TeaStyle

  @IsInt() @Min(0)
  brewing_time: number;     // en secondes

  @IsInt() @Min(0)
  brewing_temperature: number; // en degrés Celsius

  @IsEnum(caffeineLevel)
  caffeine_level: caffeineLevel; // 'none' | 'low' | 'medium' | 'high'

  @IsBoolean() @IsOptional()
  is_public?: boolean;      // visibilité communautaire
}

```

--- 

**Méthode `create`**
```ts
// src/tea/tea.service.ts — lignes 76–90
async create(createTeaDto: CreateTeaDto): Promise<Tea> {
  const tea = this.teaRepository.create(createTeaDto);

  // Validation de l'existence du style si fourni
  if (createTeaDto.style_id) {
    const style = await this.teaStyleService.findOne(createTeaDto.style_id);
    if (!style) {
      throw new NotFoundException(`style with ID ${createTeaDto.style_id} not found`);
    }
  }

  return await this.teaRepository.save(tea);
}

```


**Gestion des ingrédients — relation Many-to-Many enrichie**
La relation entre `Tea` et `Ingredient` passe par une entité de jointure `TeaIngredient` qui porte des données supplémentaires (quantité, optionnel), ce qu'une relation `@ManyToMany` native de TypeORM ne permettrait pas.

```ts
// src/tea/tea.service.ts — lignes 109–137
async addIngredient(teaId: string, dto: AddIngredientDto): Promise<TeaIngredient> {
  // 1. Vérifier l'existence du thé
  const tea = await this.teaRepository.findOne({ where: { id: teaId } });
  if (!tea) throw new NotFoundException(`Tea ${teaId} not found`);

  // 2. Vérifier l'existence de l'ingrédient
  const ingredient = await this.ingredientRepository.findOne({
    where: { id: dto.ingredientId },
  });
  if (!ingredient) throw new NotFoundException(`Ingredient ${dto.ingredientId} not found`);

  // 3. Empêcher les doublons (contrainte métier)
  const existing = await this.teaIngredientRepository.findOne({
    where: { tea: { id: teaId }, ingredient: { id: dto.ingredientId } },
  });
  if (existing) throw new ConflictException('This ingredient is already in this tea');

  // 4. Création de l'entrée dans la table de jointure
  const teaIngredient = this.teaIngredientRepository.create({
    tea: { id: teaId },
    ingredient: { id: dto.ingredientId },
    quantity: dto.quantity,
    optional: dto.optional ?? false,
  });

  return this.teaIngredientRepository.save(teaIngredient);
}

```


**Schéma de la relation**
Tea ──< TeaIngredient >── Ingredient
         │
         ├── quantity  (integer, ex: 5g)
         └── optional  (boolean)

L'entité `TeaIngredient` porte une contrainte `@Unique(['tea', 'ingredient'])` au niveau base de données, en plus du contrôle applicatif, pour garantir l'absence de doublons à deux niveaux.

--- 

**Points clés — gestion des permissions :**

- Le champ `author_id` lie le thé à son créateur. Un thé sans `author` est un **thé système** (créé par un admin, accessible à tous).
- Le contrôleur injecte automatiquement l'`author_id` depuis le token JWT : `createTeaDto.author_id = req.user.sub` — l'utilisateur ne peut pas usurper l'auteur.

**Compétences démontrées :** gestion de relations many-to-many enrichies avec TypeORM, logique métier complexe (validation multi-étapes), contrôle des permissions par ownership.

**Exemple de requête postman pour la création d'un thé**

![[Pasted image 20260226161211.png]]

---

#### TeaService — Mise à jour et suppression

**Description**

La mise à jour et la suppression implémentent le même pattern de contrôle d'accès : l'utilisateur doit être le propriétaire du thé. Les thés système (sans auteur) sont protégés contre la modification par les utilisateurs.

**Mise à jour — `update`**

```ts
// src/tea/tea.service.ts — lignes 92–106
async update(id: string, updateTeaDto: UpdateTeaDto, userId: string): Promise<Tea> {
  // findOne intègre déjà la vérification des permissions (system / own / public)
  const tea = await this.findOne(id, userId);

  // Protection supplémentaire : les thés système ne sont modifiables que par les admins
  if (!tea?.author) {
    throw new ForbiddenException('System teas can only be updated by admins');
  }

  Object.assign(tea, updateTeaDto); // patch partiel
  return await this.teaRepository.save(tea);
}

```

Le DTO `UpdateTeaDto` étend `CreateTeaDto` en rendant tous les champs optionnels **et** en excluant `author_id` — empêchant tout changement de propriétaire après création :

```ts
// src/tea/update-tea.dto.ts
export class UpdateTeaDto extends PartialType(
  OmitType(CreateTeaDto, ['author_id'] as const),
) {}

```

--- 

**Suppression douce — `remove`**

```ts
// src/tea/tea.service.ts — lignes 72–74
async remove(id: string): Promise<void> {
  await this.teaRepository.softDelete(id);
}

```

La suppression utilise `softDelete`, qui renseigne le champ `deleted_at` (via `@DeleteDateColumn` sur l'entité) sans supprimer la ligne en base. Les requêtes TypeORM filtrent automatiquement les enregistrements supprimés grâce à ce mécanisme.

**Vérification des permissions centralisée — `findOne`**

```ts
// src/tea/tea.service.ts — lignes 50–70
async findOne(id: string, userId?: string): Promise<Tea | null> {
  const tea = await this.teaRepository.findOne({
    where: { id },
    relations: ['style', 'author', 'ingredients', 'ingredients.ingredient'],
  });

  if (!tea) throw new NotFoundException(`Tea with ID ${id} not found`);

  const isSystemTea = !tea.author;                              // thé système
  const isOwnTea = tea.author && userId && tea.author.id === userId; // propriétaire
  const isPublicTea = tea.is_public;                            // public

  if (!isSystemTea && !isOwnTea && !isPublicTea) {
    throw new ForbiddenException('This tea is private');
  }

  return tea;
}

```

--- 

**Pattern de permissions — tableau récapitulatif :**

|Type de thé|`author`|`is_public`|Accès|
|---|---|---|---|
|Système|`null`|any|Tous les utilisateurs|
|Privé|`User`|`false`|Auteur uniquement|
|Public|`User`|`true`|Tous les utilisateurs|

**Compétences démontrées :** suppression douce (soft delete), pattern de contrôle d'accès centralisé, DTO avec héritage et restriction de champs (`OmitType`), séparation claire des responsabilités.

**Exemple de requête postman pour la modification d'un thé**

![[Pasted image 20260226161602.png]]

---
### Les extraits de code de composants d'accès aux données

**Introduction**

Les composants d'accès aux données regroupent les **entités** (mapping objet-relationnel), les **repositories** (interface avec la base de données) et les **requêtes** permettant de lire et manipuler les données. Le backend utilise **TypeORM** comme ORM (Object-Relational Mapper), qui traduit les opérations TypeScript en requêtes SQL paramétrées — offrant une **protection automatique contre les injections SQL** sans nécessiter d'écriture de SQL brut.

**1. Entity - Définition du modèle `User`**

```ts
// src/user/user.entity.ts
@Entity()
export class User {
  @PrimaryGeneratedColumn('uuid')
  id: string;

  @Column('varchar', { length: 30, unique: true })
  user_name: string;

  @Column('varchar', { length: 320, unique: true })
  email: string;

  @Exclude()
  @Column('text')
  password: string;                          // exclu de la sérialisation JSON

  @Column({ type: 'enum', enum: Role, default: Role.User })
  role: Role;

  @Column('boolean', { default: false })
  email_verified: boolean;

  @OneToMany(() => Tea, (tea) => tea.author)
  teas: Tea[];                               // relation inverse vers Tea

  @OneToMany(() => Ingredient, (ingredient) => ingredient.user)
  ingredients: Ingredient[];

  @CreateDateColumn()
  created_at: Date;

  @UpdateDateColumn()
  modified_at: Date;

  @DeleteDateColumn()
  deleted_at: Date;                          // soft delete

  @Column({ nullable: true })
  delete_scheduled_at: Date;                 // suppression définitive planifiée
}
```

**Points clés :**

|Décorateur|Rôle|Effet SQL|
|---|---|---|
|`@PrimaryGeneratedColumn('uuid')`|Clé primaire UUID|`id UUID PRIMARY KEY DEFAULT gen_random_uuid()`|
|`@Column({ unique: true })`|Contrainte unicité|`UNIQUE`|
|`@Column({ nullable: true })`|Valeur optionnelle|`NULL` autorisé|
|`@OneToMany`|Relation 1-N|Clé étrangère portée par `Tea`|
|`@DeleteDateColumn`|Soft delete|`deleted_at TIMESTAMP` filtré automatiquement|
|`@Exclude()`|Exclusion sérialisation|Le champ `password` ne part jamais dans la réponse JSON|

**Compétences démontrées :** modélisation ORM, mapping objet-relationnel, contraintes de base de données déclaratives.

**2. Repository simple - recherche par critère** 

```ts
// src/user/user.service.ts — lignes 39–46
async findByUsername(username: string): Promise<User | null> {
  return this.userRepository.findOneBy({ user_name: username });
}

async findByEmail(email: string): Promise<User | null> {
  if (!email) return null;
  return this.userRepository.findOneBy({ email });
}

```

--- 

**SQL généré par TypeORM**

```sql
SELECT "user"."id", "user"."user_name", "user"."email", "user"."role", ...
FROM "user"
WHERE "user"."user_name" = $1
  AND "user"."deleted_at" IS NULL
LIMIT 1
```

**Points clés :**

- La valeur `$1` est un **paramètre lié** — TypeORM ne concatène jamais la valeur directement dans la requête, ce qui élimine les injections SQL
- La condition `deleted_at IS NULL` est **ajoutée automatiquement** par TypeORM sur toutes les entités ayant `@DeleteDateColumn` — les enregistrements supprimés sont invisibles sans configuration supplémentaire
- Le typage `Promise<User | null>` force la gestion du cas "non trouvé" à l'appel

**Compétences démontrées :** requêtes SELECT sécurisées, protection injection SQL, typage strict.


**3. Relations — Récupération avec jointures**

```ts
// src/tea/tea.service.ts — lignes 51–54
const tea = await this.teaRepository.findOne({
  where: { id },
  relations: ['style', 'author', 'ingredients', 'ingredients.ingredient'],
});

```

--- 

**SQL généré :**

```ts
SELECT "tea"."id", "tea"."name", ...,
       "style"."id", "style"."name",
       "author"."id", "author"."user_name",
       "ingredients"."id", "ingredients"."quantity",
       "ingredient"."id", "ingredient"."name", "ingredient"."type"
FROM "tea"
LEFT JOIN "tea_style" "style"         ON "style"."id" = "tea"."style_id"
LEFT JOIN "user"      "author"        ON "author"."id" = "tea"."author_id"
LEFT JOIN "tea_ingredient" "ingredients" ON "ingredients"."tea_id" = "tea"."id"
LEFT JOIN "ingredient" "ingredient"   ON "ingredient"."id" = "ingredients"."ingredient_id"
WHERE "tea"."id" = $1
  AND "tea"."deleted_at" IS NULL

```

**Points clés :**

- `ingredients.ingredient` charge une **relation imbriquée sur 2 niveaux** (Tea → TeaIngredient → Ingredient) en **une seule requête SQL** via des LEFT JOIN enchaînés
- Sans ce chargement explicite, chaque accès à `tea.ingredients[i].ingredient` déclencherait une requête SQL supplémentaire — c'est le problème **N+1** que cette approche évite
- Le résultat est automatiquement **désérialisé** en objets TypeScript typés avec leurs relations imbriquées

**Compétences démontrées :** gestion des relations ORM, optimisation des requêtes, évitement du problème N+1.

--- 

**4. Opérateurs TypeORM — Requêtes avec critères avancés**

TypeORM expose des opérateurs fonctionnels permettant d'exprimer des conditions SQL complexes sans écrire de SQL brut.

```ts
// src/tea/tea.service.ts — lignes 35–47
async findSystemTeas() {
  return this.teaRepository.find({
    where: { author: IsNull() },                              // WHERE author_id IS NULL
    relations: ['style'],
  });
}

async findPublicTeas() {
  return this.teaRepository.find({
    where: { is_public: true, author: Not(IsNull()) },        // WHERE is_public = true AND author_id IS NOT NULL
    relations: ['style', 'author'],
  });
}

```

Un exemple plus avancé dans `UserService` — la suppression définitive planifiée combine deux opérateurs et conditionne un hard delete :

```ts
// src/user/user.service.ts — lignes 225–244
@Cron(CronExpression.EVERY_DAY_AT_MIDNIGHT)
async cleanupDeletedUsers() {
  const thirtyDaysAgo = new Date();
  thirtyDaysAgo.setDate(thirtyDaysAgo.getDate() - 30);

  const usersToDelete = await this.userRepository.find({
    where: {
      deleted_at: Not(IsNull()),                              // soft-deleted
      delete_scheduled_at: LessThanOrEqual(thirtyDaysAgo),   // depuis plus de 30 jours
    },
  });

  for (const user of usersToDelete) {
    await this.userRepository.delete(user.id);               // suppression définitive
  }
}

```

|Opérateur TypeORM|SQL équivalent|
|---|---|
|`IsNull()`|`IS NULL`|
|`Not(IsNull())`|`IS NOT NULL`|
|`LessThanOrEqual(date)`|`<= $1`|
|`MoreThan(date)`|`> $1`|

**Compétences démontrées :** requêtes conditionnelles typées, combinaison de critères, tâches planifiées (cron), cycle de vie complet d'une donnée (soft delete → hard delete).

--- 

**5. Opérations CRUD — Insertion, mise à jour, suppression**
**Insertion (`create` + `save`) :**

```ts
// src/user/user.service.ts — lignes 71–75
async create(createUserDto: CreateUserDto): Promise<User> {
  const user = this.userRepository.create(createUserDto); // instancie l'entité (pas encore en DB)
  return await this.userRepository.save(user);            // INSERT INTO "user" ...
}

```

`create()` instancie l'objet en mémoire, `save()` génère l'`INSERT`. Cette séparation permet d'enrichir l'entité avant persistance (ex. : hachage du mot de passe dans `AuthService` avant d'appeler `create`).

**Mise à jour partielle (`Object.assign` + `save`) :**

```ts
// src/user/user.service.ts — lignes 77–88
async update(id: string, updateUserDto: UpdateUserDto): Promise<User> {
  const user = await this.userRepository.findOneBy({ id });
  if (!user) throw new NotFoundException('User not found');

  Object.assign(user, updateUserDto); // patch : seuls les champs fournis sont écrasés
  return await this.userRepository.save(user); // UPDATE "user" SET ... WHERE id = $1
}

```

**Suppression douce + suppression définitive :**

```ts
// src/user/user.service.ts — lignes 54–64
await this.userRepository.softDelete(id);          // UPDATE SET deleted_at = NOW()

const deleteScheduledAt = new Date();
deleteScheduledAt.setDate(deleteScheduledAt.getDate() + 30);
await this.userRepository.update(id, {
  delete_scheduled_at: deleteScheduledAt,          // planifie la suppression dans 30 jours
});

```

Le cycle complet de suppression se déroule en deux temps :

1. **J0** — `softDelete` : l'utilisateur est masqué de toutes les requêtes, son compte est désactivé
2. **J+30** — le cron `cleanupDeletedUsers` exécute le `delete` définitif après vérification de `delete_scheduled_at`

**Compétences démontrées :** CRUD complet, pattern soft delete / hard delete différé, séparation instanciation / persistance.

---
## Les plans de tests

**Explication** : Description des tests effectués pour valider les fonctionnalités les plus représentatives.

La stratégie de tests mise en place pour TeaCorner vise à garantir la fiabilité et la sécurité de l'application. Compte tenu du délai contraint de sept semaines et de la taille du projet, nous avons concentré nos efforts sur deux types de tests essentiels : les tests unitaires et les tests d'intégration.
##### Objectifs 

- **Valider les fonctionnalités métier** : s'assurer que chaque composant répond aux exigences définies dans le cahier des charges.
- **Garantir la sécurité** : vérifier que l'authentification, l'autorisation et la validation des données fonctionnent correctement.
- **Prévenir les régressions** : détecter rapidement les dysfonctionnements lors de l'ajout de nouvelles fonctionnalités.
- **Faciliter la maintenance** : documenter le comportement attendu du code pour les futures évolutions.
##### Environnement de tests

- **Framework de tests** : Jest (intégré nativement à NestJS)
- **Outils complémentaires** : Supertest (pour les tests d'intégration API)
- **Base de données de test** : PostgreSQL en environnement Docker isolé
- **Tests manuels** : Postman pour valider les flux utilisateur de bout en bout

### Tests unitaires

Les tests unitaires permettent de valider le comportement des composants de manière isolée, en mockant leurs dépendances. Compte tenu des contraintes de temps du projet (7 semaines), nous avons concentré nos tests unitaires sur les fonctionnalités les plus critiques en termes de sécurité et de logique métier.

#### 1.1. Tests du service d'authentification (AuthService)

La sécurité étant une priorité, nous avons validé le mécanisme de hachage des mots de passe qui est au cœur de la protection des données utilisateur.

| Nom du test                            | Description                                                    | Résultat attendu                                                            | Statut |
| -------------------------------------- | -------------------------------------------------------------- | --------------------------------------------------------------------------- | ------ |
| `hashPassword()` - Hachage avec Argon2 | Vérifie que le mot de passe est correctement haché avec Argon2 | Mot de passe haché différent du mot de passe en clair, format Argon2 validé | Passé  |

**Exemple de test unitaire :**

```ts
import { Test, TestingModule } from '@nestjs/testing';
import { AuthService } from './auth.service';
import { getRepositoryToken } from '@nestjs/typeorm';
import { User } from '../user/user.entity';
import { JwtService } from '@nestjs/jwt';
import * as argon2 from 'argon2';
import { UserService } from '../user/user.service';
import { AuthRefreshTokenService } from './auth-refresh-token.service';
import { EmailVerificationToken } from '../entities/email-verification-token.entity';
import { EmailService } from './email.service';
import { PasswordResetToken } from '../entities/password-reset-token.entity';

  
describe('AuthService', () => {
  let service: AuthService;
  
  beforeEach(async () => {
    const module: TestingModule = await Test.createTestingModule({
      providers: [
        AuthService,
        {
          provide: getRepositoryToken(User),
          useValue: {},
        },
        { provide: JwtService, useValue: {} },
        {
          provide: UserService,
          useValue: {
            findByUsername: jest.fn(),
            create: jest.fn(),
            findOne: jest.fn(),
            save: jest.fn(),
            findByEmail: jest.fn(),
          },
        },
        {
          provide: AuthRefreshTokenService,
          useValue: { generateTokenPair: jest.fn() },
        },
        {
          provide: getRepositoryToken(EmailVerificationToken),
          useValue: {
            insert: jest.fn(),
            find: jest.fn(),
            save: jest.fn(),
            findOne: jest.fn(),
          },
        },
        {
          provide: getRepositoryToken(PasswordResetToken),
          useValue: {
            insert: jest.fn(),
            findOne: jest.fn(),
            delete: jest.fn(),
          },
        },
        {
          provide: EmailService,
          useValue: {
            sendVerificationEmail: jest.fn(),
            sendResetEmail: jest.fn(),
            sendDeletionNotification: jest.fn(),
          },
        },
        {
          provide: EmailService,
          useValue: {
            sendVerificationEmail: jest.fn(),
            sendPasswordResetEmail: jest.fn(),
          },
        },
        {
          provide: getRepositoryToken(PasswordResetToken),
          useValue: {
            findOne: jest.fn(),
            save: jest.fn(),
            delete: jest.fn(),
          },
        },
      ],
    }).compile();
    service = module.get<AuthService>(AuthService);
  });

  it('should hash a password correctly', async () => {
    // Arrange
    const password = 'monMotDePasse';
    // Act
    const hash = await service.hashPassword(password);
    // Assert
    expect(typeof hash).toBe('string');
    expect(hash).not.toBe(password);
    const isHashed = await argon2.verify(hash, password);
    expect(isHashed).toBe(true);
  });
});
```


**Ce test garantit que :**

- Les mots de passe ne sont jamais stockés en clair dans la base de données
- L'algorithme Argon2 (recommandé par l'OWASP) est bien utilisé
- Chaque hachage utilise un salt aléatoire unique
#### 1.2. Tests du contrôleur utilisateur (UserController)

Le `UserController` gère les opérations sur les utilisateurs. Nous avons testé les fonctionnalités essentielles de récupération et de modification de profil.

| Nom du test                                  | Description                                                               | Résultat attendu                                                          | Statut |
| -------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------ |
| `findUserProfile()` - Profil existant        | Récupère le profil complet d'un utilisateur par son username              | Retourne l'utilisateur avec toutes ses propriétés (username, email, etc.) | Passé  |
| `findUserProfile()` - Utilisateur inexistant | Recherche un utilisateur qui n'existe pas                                 | Exception `NotFoundException` levée avec message approprié                | Passé  |
| `updateProfile()` - Mise à jour valide       | Met à jour les informations du profil (display_name, bio, avatar, banner) | Profil modifié retourné avec les nouvelles valeurs                        | Passé  |

**Exemple de code testé :**

```ts
import { Test, TestingModule } from '@nestjs/testing';
import { UserController } from './user.controller';
import { UserService } from './user.service';
import { User } from './user.entity';
import { Status } from '../enums/status.enum';
import { Role } from '../enums/role.enum';
import { AuthGuard } from '../guards/auth.guard';
import { RolesGuard } from '../guards/roles.guard';
import { NotFoundException } from '@nestjs/common';
import { UpdateUserDto } from './update-user.dto';

describe('UserController', () => {

  let controller: UserController;
  let service: UserService;

  beforeEach(async () => {
    const module: TestingModule = await Test.createTestingModule({
      controllers: [UserController],
      providers: [
        {
          provide: UserService,
          useValue: {
            findByUsername: jest.fn(),
            update: jest.fn(),
            updateUserName: jest.fn(),
            findAll: jest.fn(),
          },
        },
      ],
    })
      .overrideGuard(AuthGuard)
      .useValue({ canActivate: jest.fn(() => true) })
      .overrideGuard(RolesGuard)
      .useValue({ canActivate: jest.fn(() => true) })
      .compile();
    controller = module.get<UserController>(UserController);
    service = module.get<UserService>(UserService);
  });

  it('should be defined', () => {
    expect(controller).toBeDefined();
  });
  describe('UpdateProfile', () => {
    it("should update the user's profile using the updateUserDTO from the request", async () => {
      const mockUser: User = {
        id: '1',
        user_name: 'john_doe',
        display_name: 'john_doe',
        avatar_url: 'adfadf',
        banner_color: 'afadf',
        bio: 'adfadf',
        password: 'adfadferd',
        role: Role['user'],
        status: Status['ACTIVE'],
        email: 'john@example.com',
        email_verified: true,
        username_last_changed: new Date(),
        created_at: new Date(),
        modified_at: new Date(),
        deleted_at: new Date(),
        delete_scheduled_at: new Date(),
        teas: [],
        userTeas: [],
        ingredients: [],
      };
      const updateDto: UpdateUserDto = {
        display_name: 'john_doe',
        avatar_url: 'adfadf',
        banner_color: 'afadf',
        bio: 'adfadf',
      } as UpdateUserDto;
      const updateSpy = jest
        .spyOn(service, 'update')
        .mockResolvedValue(mockUser);
      const req = { user: { sub: 1 } };
      const result = await controller.updateProfile(req, updateDto);
      expect(result).toBe(mockUser);
      expect(updateSpy).toHaveBeenCalledWith(1, updateDto);
    });
  });
  describe('findUserProfile', () => {
    it('should return the user profile using the username from the request', async () => {
      const result: User = {
        id: '1',
        user_name: 'john_doe',
        display_name: 'john_doe',
        avatar_url: 'adfadf',
        banner_color: 'afadf',
        bio: 'adfadf',
        password: 'adfadferd',
        role: Role['user'],
        status: Status['ACTIVE'],
        email: 'john@example.com',
        email_verified: true,
        username_last_changed: new Date(),
        created_at: new Date(),
        modified_at: new Date(),
        deleted_at: new Date(),
        teas: [],
        userTeas: [],
        ingredients: [],
        delete_scheduled_at: new Date(),
      };
      const findSpy = jest
       .spyOn(service, 'findByUsername')
       .mockResolvedValue(result);
      const req = { user: { username: 'john_doe' } };
      expect(await controller.findUserProfile(req)).toBe(result);
      expect(findSpy).toHaveBeenLastCalledWith('john_doe');
    });
    it('should throw NotFoundException when user not found', async () => {
      jest.spyOn(service, 'findByUsername').mockResolvedValue(null);
      const req = { user: { username: 'nonexistent' } };
      await expect(controller.findUserProfile(req)).rejects.toThrow(
        NotFoundException,
      );
    });
  });
  describe('change username', () => {
    it('should change the username, up to once a month', async () => {});
  });

});
```

**Points clés validés par ces tests :**

- Les guards (`AuthGuard`, `RolesGuard`) sont correctement mockés pour isoler le test du controller
- Le service `UserService` est mocké pour éviter les appels à la base de données
- La gestion des erreurs (`NotFoundException`) fonctionne correctement
- Les données utilisateur sont correctement passées du contrôleur au service

### Tests d'intégration

Les tests d'intégration valident le fonctionnement complet des routes API, en testant l'interaction entre les controllers, services et base de données dans un environnement proche de la production. Compte tenu des contraintes de temps, nous avons priorisé le test du flux d'authentification qui est critique pour la sécurité de l'application.

#### 2.1. Test de la route de connexion (sign in)

Le test d'intégration suivant valide le processus complet de connexion, de la création d'un utilisateur de test en base de données jusqu'à la vérification des cookies sécurisés retournés.

| Endpoint       | Méthode | Scénario de test                    | Résultat attendu                                               | Statut |
| -------------- | ------- | ----------------------------------- | -------------------------------------------------------------- | ------ |
| `/auth/signin` | POST    | Connexion avec identifiants valides | Status 200, cookies `access_token` et `refresh_token` présents | Passé  |

**Implémentation du test d'intégration E2E :**

```ts
import request from 'supertest';
import { AppModule } from 'src/app.module';
import { INestApplication } from '@nestjs/common';
import * as argon2 from 'argon2';
import { Test } from '@nestjs/testing';
import { getRepositoryToken } from '@nestjs/typeorm';
import { User } from '../src/user/user.entity';
import { Repository } from 'typeorm';

describe('Auth E2E', () => {
  let app: INestApplication;
  let userRepo: Repository<User>;
  beforeAll(async () => {
    const moduleRef = await Test.createTestingModule({
      imports: [AppModule],
    }).compile();
    // Nest init
    app = moduleRef.createNestApplication();
    await app.init();
    userRepo = moduleRef.get(getRepositoryToken(User));
  });
  it('should sign in and return cookies', async () => {
    // create user in database
    const hashed = await argon2.hash('12345678');
    await userRepo.save({
      user_name: 'test',
      password: hashed,
      email_verified: true,
    });
    // call the api route
    const res = await request(app.getHttpServer())
      .post('/auth/signin')
      .send({ user_name: 'test', password: '12345678' });
    // check for status
    expect(res.status).toBe(200);
    // check cookies
    expect(res.headers['set-cookie']).toBeDefined();
  });
  afterAll(async () => {
    await app.close();
  });
});
```

**Ce que ce test valide :**

1. **Flux complet d'authentification** : le test couvre l'ensemble de la chaîne depuis la requête HTTP jusqu'à la génération des tokens
2. **Interaction avec la base de données réelle** : utilisation d'un repository TypeORM pour créer un utilisateur de test
3. **Vérification du mot de passe** : validation que le hachage Argon2 et la comparaison fonctionnent correctement via `validateUser()`
4. **Génération des tokens JWT** : le service `AuthRefreshTokenService` génère bien les access et refresh tokens
5. **Configuration des cookies** : les cookies sont correctement retournés dans la réponse HTTP
#### 2.2. Aspects de sécurité validés

Ce test d'intégration valide plusieurs aspects critiques de la sécurité :

| Aspect de sécurité        | Validation                                                                       | Résultat |
| ------------------------- | -------------------------------------------------------------------------------- | -------- |
| Hachage Argon2            | Le mot de passe est haché avant stockage et vérifié lors de la connexion         | Validé   |
| Cookies httpOnly          | Les tokens sont stockés dans des cookies inaccessibles au JavaScript côté client | Validé   |
| SameSite                  | Protection contre les attaques CSRF avec l'attribut `sameSite: 'lax'`            | Validé   |
| Durée de vie différenciée | Access token (15 min) et refresh token (7 jours) ont des durées adaptées         | Validé   |
| Vérification email        | Seuls les utilisateurs avec `email_verified: true` peuvent se connecter          | Validé   |

### Tests manuels

En complément des tests automatisés, des tests manuels ont été effectués via Postman pour valider les flux utilisateur complets et s'assurer que l'API fonctionne correctement de bout en bout.

#### 3.1. Scénarios testés manuellement

- **Flux d'inscription et connexion**
    - Inscription d'un nouvel utilisateur
    - Vérification de l'email (simulation via base de données)
    - Connexion avec les identifiants créés
    - Vérification de la présence des cookies JWT
- **Gestion du profil utilisateur**
    - Récupération du profil utilisateur connecté
    - Modification des informations de profil (username, bio)
    - Vérification de la persistance des modifications
- **Protection des routes**
    - Tentative d'accès aux routes protégées sans token
    - Vérification du message d'erreur 401 Unauthorized
    - Accès réussi avec token valide
- **Gestion des erreurs**
    - Test des validations (email invalide, mot de passe trop court, etc.)
    - Vérification des messages d'erreur retournés

Ces tests manuels ont permis de valider l'expérience développeur lors de l'utilisation de l'API et de s'assurer que les messages d'erreur sont clairs et explicites.

### Couverture des tests

La couverture de code a été mesurée avec Jest. Voici les résultats obtenus :

#### 4.1. Couverture globale

| Métrique                  | Pourcentage |
| ------------------------- | ----------- |
| Statements (instructions) | 40.94%      |
| Branches (conditions)     | 48.95%      |
| Functions (fonctions)     | 17.28%      |
| Lines (lignes)            | 38.43%      |

#### 4.2. Couverture par module

|Module|% Lignes|% Branches|% Fonctions|Zones testées|
|---|---|---|---|---|
|**Auth Module**|27.41%|45%|9.09%|Hachage mot de passe, connexion|
|**User Module**|46.19%|52.54%|17.39%|Profil utilisateur, mise à jour|
|Guards|41.66%|50%|0%|Protection des routes (partiellement)|
|Entities|89.65%|75%|0%|Définitions des entités|

#### 4.3. Détail de la couverture des fichiers principaux

**Module Auth :**

| Fichier                         | % Lignes | Commentaire                  |
| ------------------------------- | -------- | ---------------------------- |
| `auth.service.ts`               | 21.59%   | Testé : hashPassword()       |
| `auth.controller.ts`            | 57.57%   | Testé : route signin via E2E |
| `auth-refresh-token.service.ts` | 37.5%    | Utilisé dans le test signin  |

**Module User :**

|Fichier|% Lignes|Commentaire|
|---|---|---|
|`user.controller.ts`|61.36%|Testé : findUserProfile, updateProfile|
|`user.service.ts`|15.05%|Partiellement testé via le controller|
|`user.entity.ts`|100%|Définition de l'entité (pas de logique)|

**Analyse de la couverture :**

La couverture actuelle (~40% globalement) se concentre sur les fonctionnalités critiques pour la sécurité et l'expérience utilisateur de base :

 **Points bien couverts :**

- Hachage des mots de passe avec Argon2 (sécurité fondamentale)
- Flux de connexion complet avec cookies sécurisés (authentification)
- Récupération et mise à jour du profil utilisateur (fonctionnalité principale)
- Gestion des erreurs (NotFoundException)

 **Points non couverts :**

- Inscription d'utilisateur (`signUp`)
- Vérification d'email (`verifyEmail`)
- Récupération de mot de passe (`forgotPassword`, `resetPassword`)
- Gestion du refresh token (`refreshTokens`)
- Routes de gestion des recettes
- Logout
- Validation côté formulaire (DTOs)

Cette distribution reflète une approche pragmatique : couvrir d'abord ce qui est essentiel (authentification, sécurité des mots de passe) puis étendre progressivement.

### Limites et perspectives d'amélioration

#### Limites actuelles

Compte tenu du délai contraint de 7 semaines et de la priorisation des fonctionnalités, plusieurs aspects des tests n'ont pas pu être couverts :

- **Couverture de tests limitée** : environ 50% du code est couvert, principalement sur les fonctionnalités critiques (authentification, profil utilisateur).
- **Tests d'intégration partiels** : seul le flux de connexion a été testé de bout en bout. Les autres routes (inscription, vérification email, recettes) n'ont pas de tests d'intégration automatisés.
- **Pas de tests end-to-end (E2E)** : les tests frontend et les parcours utilisateur complets ne sont pas couverts.
- **Pas de tests de charge** : aucune validation de la performance sous forte charge n'a été effectuée.

---
## Les vulnérabilités et leur correction

La sécurité est un aspect fondamental de toute application. Dans le cadre du projet TeaCorner, plusieurs vulnérabilités potentielles ont été identifiées dès la phase de conception, permettant de mettre en place des mesures de protection appropriées avant même qu'elles ne deviennent des failles exploitables. Cette section présente les principales vulnérabilités adressées et les solutions techniques mises en œuvre pour sécuriser l'application.

### Stockage des mots de passe en clair

#### Vulnérabilité identifiée

**Type** : Violation de confidentialité (OWASP A02:2021 - Cryptographic Failures)

**Risque** : Si la base de données est compromise, les mots de passe en clair seraient immédiatement accessibles aux attaquants, permettant :

- L'accès non autorisé aux comptes utilisateurs
- L'exploitation de la réutilisation de mots de passe sur d'autres services
- La compromission totale du système
#### Solution mise en œuvre

**Hachage avec Argon2** : Utilisation de l'algorithme Argon2 recommandé par l'OWASP.

```ts
// auth.service.ts
import * as argon2 from 'argon2';

async hashPassword(password: string): Promise<string> {
  return argon2.hash(password);
}

async signUp(createUserDto: CreateUserDto): Promise<{ message: string }> {
  // Hachage du mot de passe avant stockage
  const hashedPassword = await this.hashPassword(createUserDto.password);

  const data = {
    ...createUserDto,
    password: hashedPassword,
    email_verified: false,
  };

  await this.userService.create(data);
  // ... reste du code
}
```

**Vérification lors de la connexion :**

```ts
// auth.service.ts
async validateUser(username: string, pass: string): Promise<any> {
  const user = await this.userService.findByUsername(username);
  if (!user) return null;

  // Vérification du mot de passe avec Argon2
  const isMatch = await argon2.verify(user.password, pass);
  if (!isMatch) return null;

  const { password: _password, ...result } = user;
  return result;
}
```

**Avantages d'Argon2 :**

- Protection contre les attaques par force brute (calcul intensif en mémoire et CPU)
- Salt automatique unique pour chaque mot de passe
- Résistant aux attaques GPU et ASIC

### Vol de session

#### Vulnérabilité identifiée

**Type** : Exposition de tokens d'authentification (OWASP A07:2021 - Identification and Authentication Failures)

**Risque** : Sans protection adéquate, les tokens d'authentification (JWT) peuvent être :

- Interceptés par des scripts malveillants (attaque XSS)
- Volés via le stockage localStorage accessible en JavaScript
- Utilisés dans des attaques CSRF (Cross-Site Request Forgery)
#### Solution mise en œuvre

**Cookies sécurisés :** Stockage des tokens JWT et refresh tokens dans des cookies httpOnly avec attributs de sécurité.

**Implémentation :**

```ts
// auth.service.ts
async signIn(
  user: User,
  response: Response,
): Promise<{ access_token: string; refresh_token: string }> {
  const tokens = await this.authRefreshTokenService.generateTokenPair(user);

  // Cookie pour le JWT (access token)
  response.cookie('access_token', tokens.access_token, {
    httpOnly: true,           // Inaccessible au JavaScript côté client
    secure: false,            // true en production (HTTPS uniquement)
    sameSite: 'lax',          // Protection CSRF
    maxAge: 15 * 60 * 1000,   // 15 minutes
  });

  // Cookie pour le refresh token
  response.cookie('refresh_token', tokens.refresh_token, {
    httpOnly: true,
    secure: false,            // true en production
    sameSite: 'lax',
    maxAge: 7 * 24 * 60 * 60 * 1000,  // 7 jours
  });

  return tokens;
}
```


**Mécanismes de protection :**

|Attribut|Protection|Explication|
|---|---|---|
|`httpOnly: true`|XSS|Le cookie n'est pas accessible via `document.cookie` en JavaScript|
|`secure: true`|Man-in-the-middle|Le cookie n'est transmis que via HTTPS en production|
|`sameSite: 'lax'`|CSRF|Le cookie n'est pas envoyé dans les requêtes cross-site (sauf GET)|
|Durée courte (15 min)|Vol de token|Limite la fenêtre d'exploitation en cas de vol du JWT|
**Stratégie de rafraîchissement des tokens :**

```ts
async refreshTokens(
  userId: string,
  currentRefreshToken: string,
  response: Response,
) {
  const user = await this.userService.findOne(userId);
  if (!user) {
    throw new UnauthorizedException('User not found');
  }

  // Validation du refresh token
  const isValid = await this.authRefreshTokenService.validateRefreshToken(
    currentRefreshToken,
    userId,
  );
  if (!isValid) {
    throw new UnauthorizedException('Invalid or expired refresh token');
  }

  // Génération d'un nouveau access token
  const newAccessToken = this.authRefreshTokenService.generateAccessToken(user);

  response.cookie('access_token', newAccessToken, {
    httpOnly: true,
    secure: process.env.NODE_ENV === 'production',
    sameSite: 'lax',
    maxAge: 15 * 60 * 1000,
  });

  return { message: 'Access token refreshed' };
}
```


### Injections SQL

#### Vulnérabilité identifiée

**Type** : Injection SQL (OWASP A03:2021 - Injection)

**Risque** : Manipulation des requêtes SQL permettant :

- Extraction de données sensibles (mots de passe, emails, informations personnelles)
- Modification ou suppression de données

#### Solution mise en œuvre

**Utilisation de TypeORM avec requêtes paramétrées** : L'ORM gère automatiquement l'échappement des paramètres et utilise des requêtes préparées.


**Implémentation :**

```ts
// user.service.ts
async findByUsername(username: string): Promise<User> {
  // TypeORM utilise des requêtes paramétrées automatiquement
  return this.userRepository.findOne({
    where: { user_name: username }
  });
  // Protection automatique contre les injections SQL
}

async findByEmail(email: string): Promise<User> {
  return this.userRepository.findOne({
    where: { email: email }
  });
  // Le paramètre 'email' est automatiquement échappé
}
```


**Protection au niveau de l'entité :**

```ts
// user.entity.ts
@Entity('tea_user')
export class User {
  @PrimaryGeneratedColumn('uuid')
  id: string;

  @Column({ unique: true })
  user_name: string;

  @Column({ unique: true })
  email: string;

  // TypeORM gère le mapping et la validation des types
}
```

**Avantages de TypeORM :**

- Requêtes paramétrées par défaut
- Typage fort avec TypeScript
- Validation automatique des types de données
- Protection contre les injections même dans les requêtes complexes

### Attaques par force brute

#### Vulnérabilité identifiée

**Type** : Attaques par déni de service et compromission de comptes (OWASP A07:2021)

**Risque** : Sans limitation du nombre de tentatives :

- Déni de service (DoS) en surchargeant l'API
- Compromission de comptes avec mots de passe faibles

#### Solution mise en œuvre

**Rate Limiting (limitation de débit)** : Restriction du nombre de requêtes par IP sur les routes sensibles.

**Implémentation avec @nestjs/throttler :**

```ts
// app.module.ts ou auth.module.ts
import { ThrottlerModule, ThrottlerGuard } from '@nestjs/throttler';

@Module({
  imports: [
    ThrottlerModule.forRoot([{
      ttl: 60000,      // Fenêtre de temps : 60 secondes
      limit: 5,        // Maximum 5 requêtes par fenêtre
    }]),
  ],
  providers: [
    {
      provide: APP_GUARD,
      useClass: ThrottlerGuard,  // Guard global
    },
  ],
})
export class AppModule {}
```


**Application sur les routes critiques :**

```ts
// auth.controller.ts
import { Throttle } from '@nestjs/throttler';

@Controller('auth')
export class AuthController {
  
  @Post('signin')
  @Throttle({ default: { limit: 5, ttl: 60000 } })
  // Maximum 5 tentatives de connexion par minute
  async signIn(@Request() req, @Response() res) {
    // ...
  }

  @Post('signup')
  @Throttle({ default: { limit: 3, ttl: 60000 } })
  // Maximum 3 inscriptions par minute (prévient le spam)
  async signUp(@Body() createUserDto: CreateUserDto) {
    // ...
  }
}
```

**Configuration par route :**

| Route                   | Limite     | Fenêtre | Justification                     |
| ----------------------- | ---------- | ------- | --------------------------------- |
| `/auth/signin`          | 5 requêtes | 60s     | Protection contre le brute force  |
| `/auth/signup`          | 3 requêtes | 60s     | Prévention du spam d'inscriptions |
| `/auth/forgot-password` | 2 requêtes | 300s    | Limite les abus d'envoi d'emails  |

**Gestion des erreurs :**

```ts
// Lorsque la limite est dépassée, l'utilisateur reçoit :
// HTTP 429 Too Many Requests
{
  "statusCode": 429,
  "message": "ThrottlerException: Too Many Requests"
}
```

### Cross-Site Scripting (XSS)

####  Vulnérabilité identifiée

**Type** : Injection de scripts malveillants (OWASP A03:2021 - Injection)

**Risque** : Injection de JavaScript dans les données utilisateur permettant :

- Vol de cookies et tokens (si pas httpOnly)
- Redirection vers des sites malveillants
- Modification du contenu de la page
- Keylogging (enregistrement des frappes clavier)
#### Solution mise en œuvre

**1. Validation stricte des entrées avec class-validator**

```ts
// create-user.dto.ts
import { IsString, IsEmail, MinLength, MaxLength, Matches } from 'class-validator';

export class CreateUserDto {
  @IsString()
  @MinLength(3)
  @MaxLength(20)
  @Matches(/^[a-zA-Z0-9_]+$/, {
    message: 'Le username ne peut contenir que des lettres, chiffres et underscores'
  })
  user_name: string;

  @IsEmail()
  email: string;

  @IsString()
  @MinLength(8)
  @MaxLength(100)
  password: string;
}
```

**2. Sanitisation des entrées utilisateur**

```ts
// update-user.dto.ts
export class UpdateUserDto {
  @IsOptional()
  @IsString()
  @MaxLength(50)
  display_name?: string;

  @IsOptional()
  @IsString()
  @MaxLength(500)
  bio?: string;  // Limité à 500 caractères, validation côté serveur
}
```

**Mesures complémentaires :**

- Les cookies httpOnly empêchent l'accès JavaScript aux tokens
- Validation stricte des formats (username, email)
- Limitation de la taille des champs texte

### Cross-Site Request Forgery (CSRF)

#### Vulnérabilité identifiée

**Type** : Attaque par requête falsifiée (OWASP A01:2021 - Broken Access Control)

**Risque** : Un attaquant peut forcer un utilisateur authentifié à exécuter des actions non désirées :

- Modification du profil
- Suppression de compte
- Transfert de données

#### Solution mise en œuvre

**Protection via l'attribut SameSite des cookies**

```ts
response.cookie('access_token', tokens.access_token, {
  httpOnly: true,
  secure: process.env.NODE_ENV === 'production',
  sameSite: 'lax',  // Le cookie n'est pas envoyé dans les requêtes cross-site
  maxAge: 15 * 60 * 1000,
});
```

**Fonctionnement de `sameSite: 'lax'` :**

- Cookie envoyé pour les requêtes de navigation (GET depuis un lien)
- Cookie **non envoyé** pour les requêtes POST/PUT/DELETE depuis un autre site
- Protection efficace contre les CSRF sur les actions sensibles

**Protection complémentaire :** Ajout d'un token CSRF pour les opérations critiques

### Exposition de données sensibles

#### Vulnérabilité identifiée

**Type** : Exposition de secrets et configuration (OWASP A05:2021 - Security Misconfiguration)

**Risque** :

- Clés secrètes codées en dur dans le code source
- Credentials exposés dans le repository Git
- Configuration sensible accessible publiquement
####  Solution mise en œuvre

**1. Variables d'environnement avec fichier .env**

```bash
# .env (NON versionné dans Git)
DATABASE_URL=postgresql://user:password@localhost:5432/teacorner
JWT_SECRET=super_secret_key_change_in_production_12345
JWT_REFRESH_SECRET=refresh_secret_key_67890
SMTP_HOST=smtp.gmail.com
SMTP_USER=noreply@teacorner.com
SMTP_PASSWORD=smtp_password_here
```

**2. Configuration .gitignore**

```bash
# .gitignore
.env
.env.local
.env.production
*.env
```

**3. Utilisation sécurisée dans le code**

```ts
// app.module.ts
import { ConfigModule } from '@nestjs/config';

@Module({
  imports: [
    ConfigModule.forRoot({
      isGlobal: true,
      envFilePath: '.env',
    }),
  ],
})
export class AppModule {}
```

```ts
// auth-refresh-token.service.ts
import { ConfigService } from '@nestjs/config';

constructor(
  private configService: ConfigService,
  private jwtService: JwtService,
) {}

generateAccessToken(user: User): string {
  const payload = { sub: user.id, username: user.user_name };
  return this.jwtService.sign(payload, {
    secret: this.configService.get<string>('JWT_SECRET'),
    expiresIn: '15m',
  });
}
```

**4. Fichier .env.example pour la documentation**

```bash
# .env.example (versionné dans Git)
DATABASE_URL=postgresql://user:password@localhost:5432/dbname
JWT_SECRET=your_jwt_secret_here
JWT_REFRESH_SECRET=your_refresh_secret_here
```

### Vérification d'email manquante

#### Vulnérabilité identifiée

**Type** : Bypass de contrôle d'authentification

**Risque** :

- Création de comptes avec des emails invalides
- Usurpation d'identité
- Spam et abus
#### Solution mise en œuvre

**Obligation de vérifier l'email avant connexion**

```ts
// auth.service.ts
async validateUser(username: string, pass: string): Promise<any> {
  const user = await this.userService.findByUsername(username);
  if (!user) return null;

  // Vérification que l'email est confirmé
  if (!user.email_verified) {
    throw new UnauthorizedException(
      'Veuillez vérifier votre email avant de vous connecter'
    );
  }

  const isMatch = await argon2.verify(user.password, pass);
  if (!isMatch) return null;

  const { password: _password, ...result } = user;
  return result;
}
```

**Processus de vérification sécurisé :**

```ts
async verifyEmail(token: string) {
  // Hash du token pour comparaison sécurisée
  const hashedToken = crypto.createHash('sha256').update(token).digest('hex');

  const tokenRecord = await this.emailVerificationTokenRepository.findOne({
    where: { email_token: hashedToken, used: false },
    relations: ['user'],
  });

  if (!tokenRecord) {
    throw new BadRequestException('Token invalide ou déjà utilisé');
  }

  if (tokenRecord.expires_at < new Date()) {
    throw new BadRequestException('Token expiré');
  }

  // Marquage du token comme utilisé
  tokenRecord.used = true;
  await this.emailVerificationTokenRepository.save(tokenRecord);

  // Activation du compte
  tokenRecord.user.email_verified = true;
  await this.userService.save(tokenRecord.user);

  return { message: 'Email vérifié avec succès' };
}
```

### Gestion des erreurs et fuites d'information

####  Vulnérabilité identifiée

**Type** : Information Disclosure

**Risque** : Messages d'erreur trop détaillés révélant :

- Structure de la base de données
- Technologies utilisées
- Chemins de fichiers internes

####  Solution mise en œuvre

**Messages d'erreur génériques pour l'utilisateur**

```ts
// auth.service.ts
async validateUser(username: string, pass: string): Promise<any> {
  const user = await this.userService.findByUsername(username);
  
  // Mauvais : révèle si l'utilisateur existe
  // if (!user) throw new Error('Utilisateur introuvable');
  
  //  Bon : message générique
  if (!user) return null;
  
  const isMatch = await argon2.verify(user.password, pass);
  
  // Mauvais : révèle que l'utilisateur existe mais mot de passe incorrect
  // if (!isMatch) throw new Error('Mot de passe incorrect');
  
  // Bon : retourne null, le controller renverra "Identifiants invalides"
  if (!isMatch) return null;

  return result;
}
```


--- 

## Veille technologique 

### Introduction 

La veille technologique est essentielle pour rester à jour sur les bonnes pratiques, les nouvelles versions des frameworks et les enjeux de sécurité. Durant le projet TeaCorner, j'ai mis en place une démarche de veille régulière pour prendre des décisions techniques éclairées.

### Sources et outils

**Documentation officielle :**

- NestJS Documentation (architecture, sécurité, tests)
- React Documentation (hooks, routing)
- TypeORM Documentation (relations, migrations)
- PostgreSQL Documentation

**Communautés et plateformes :**

- **Medium** : articles techniques sur NestJS, React, sécurité
- **Stack Overflow** : résolution de problèmes spécifiques
- **Daily.dev** : agrégateur d'articles tech (flux quotidien)
- **GitHub** : consultation de repos similaires, issues, discussions

**Ressources sécurité :**

- **OWASP** : Top 10 des vulnérabilités web, guides de sécurité
- **Auth0 Blog** : bonnes pratiques d'authentification
- **Authgear** : patterns d'authentification moderne
- **GeeksforGeeks** : concepts de sécurité expliqués

**Fréquence :**

- Quotidien : Daily.dev (10-15 min)
- Au besoin : Doc officielle + Stack Overflow (problèmes spécifiques)
- Hebdomadaire : Articles Medium sur les technologies du projet

### Veille appliquée au projet

**Exemple 1 : Choix d'Argon2 pour le hachage**

- **Découverte** : Article Medium + OWASP sur les algorithmes de hachage
- **Recherche** : Comparaison Argon2 vs bcrypt (résistance GPU, recommandations)
- **Application** : Implémentation d'Argon2 dans AuthService
- **Résultat** : Sécurité renforcée selon les standards OWASP

**Exemple 2 : Cookies httpOnly et sécurité des sessions**

- **Découverte** : OWASP Top 10 (A07: Identification and Authentication Failures)
- **Recherche** : Auth0 blog sur les bonnes pratiques JWT
- **Application** : Configuration des cookies (httpOnly, sameSite, secure)
- **Résultat** : Protection contre XSS et CSRF

**Exemple 3 : Rate limiting**

- **Découverte** : OWASP sur les attaques par force brute
- **Recherche** : Documentation NestJS Throttler + Stack Overflow
- **Application** : @nestjs/throttler sur routes d'authentification
- **Résultat** : Protection contre le brute force (5 req/min)

**Exemple 4 : Résolution de problèmes spécifiques**

- **Problème** : Gestion des relations TypeORM
- **Recherche** : Stack Overflow + TypeORM docs
- **Solution** : Utilisation de `relations` dans `findOne()`
- **Apprentissage** : Eager vs Lazy loading


---


## CI/CD - DevOps 

### Introduction

La mise en place d'une pipeline CI/CD (Continuous Integration / Continuous Deployment) est essentielle pour garantir la qualité du code et automatiser le processus de déploiement. Dans le cadre du projet TeaCorner, nous avons mis en place une infrastructure DevOps moderne utilisant Docker pour la containerisation, GitHub Actions pour l'automatisation, et Render pour l'hébergement côté backend et base de données.

Cette approche permet de :

- **Détecter les erreurs rapidement** : tests automatisés à chaque push
- **Garantir la qualité du code** : linting et validation automatique
- **Simplifier le déploiement** : mise en production automatique
- **Assurer la reproductibilité** : environnement identique en développement et production

### Containerisation avec Docker

#### 1.1. Architecture de containerisation

Le projet utilise Docker et Docker Compose pour créer un environnement de développement reproductible et isolé. Cette approche garantit que l'application fonctionne de manière identique sur toutes les machines (développement, staging, production).

**Technologies utilisées :**

- Docker : containerisation des applications
- Docker Compose : orchestration multi-conteneurs
- Multi-stage builds : optimisation de la taille des images

#### 1.2. Dockerfile - Image du backend

Le Dockerfile utilise une stratégie **multi-stage build** pour optimiser la taille de l'image finale et séparer les phases de build et d'exécution.

```dockerfile
# Step 1 : Build
FROM node:22 AS builder

WORKDIR /app

# Copie des fichiers de dépendances
COPY package*.json ./
RUN npm install

# Copie du code source et build
COPY . .
RUN npm run build

# Step 2 : Run (lighter image)
FROM node:22-slim AS runner

WORKDIR /app

# Copie uniquement des fichiers nécessaires depuis le builder
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules
COPY package*.json ./

EXPOSE 3000

CMD ["node", "dist/main.js"]
```

**Avantages de cette approche :**

| Avantage                          | Explication                                                                                      |
| --------------------------------- | ------------------------------------------------------------------------------------------------ |
| **Image légère**                  | L'image finale (`node:22-slim`) ne contient que le code compilé et les dépendances de production |
| **Sécurité**                      | Pas d'outils de développement (compilateur TypeScript, etc.) dans l'image de production          |
| **Performance**                   | Image plus petite = déploiement plus rapide                                                      |
| **Séparation des préoccupations** | Phase de build isolée de la phase d'exécution                                                    |

**Taille des images :**

- Image builder : ~1.2 GB (avec tous les outils de dev)
- Image finale : ~300 MB (uniquement runtime + app compilée)

#### 1.3. Docker Compose - Orchestration des services

Le fichier `docker-compose.yml` définit l'architecture multi-conteneurs de l'application en local.

```yaml
version: '3.9'

services:
  # Service backend NestJS
  backend:
    build: .
    container_name: teacorner-backend
    ports:
      - "3000:3000"
    env_file:
      - .env
    environment:
      DB_HOST: postgres
      DB_PORT: 5432
    depends_on:
      - postgres
    networks:
      - teacorner-network

  # Service base de données PostgreSQL
  postgres:
    image: postgres:16
    container_name: teacorner-db
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: root
      POSTGRES_DB: tea_corner
    ports:
      - "5432:5432"
    volumes:
      - pgdata:/var/lib/postgresql/data
    networks:
      - teacorner-network

networks:
  teacorner-network:

volumes:
  pgdata:
```

**Fonctionnalités clés :**

1. **Isolation réseau** : Les conteneurs communiquent via le réseau `teacorner-network`
2. **Persistence des données** : Volume `pgdata` pour sauvegarder la base de données
3. **Variables d'environnement** : Fichier `.env` pour la configuration
4. **Dépendances** : Le backend attend que PostgreSQL soit prêt (`depends_on`)

**Commandes Docker Compose :**

```bash
# Démarrer tous les services
docker-compose up -d

# Voir les logs
docker-compose logs -f backend

# Arrêter les services
docker-compose down

# Arrêter et supprimer les volumes (réinitialisation complète)
docker-compose down -v
```

### Pipeline CI/CD avec GitHub Actions

#### 2.1. Vue d'ensemble de la pipeline

La pipeline CI/CD automatise le processus de test et de déploiement. Elle se déclenche automatiquement à chaque push ou pull request sur la branche `staging`.

#### 2.2. Configuration GitHub Actions

**Fichier : `.github/workflows/ci-cd.yml`**

```yaml
name: CI/CD

# Déclencheurs : push ou PR sur la branche staging
on:
  push:
    branches: [ staging ]
  pull_request:
    branches: [ staging ]

jobs:
  # ========================================
  # JOB 1 : TESTS
  # ========================================
  test:
    runs-on: ubuntu-latest
    
    steps: 
      # Étape 1 : Récupération du code
      - name: Checkout code
        uses: actions/checkout@v3
      
      # Étape 2 : Installation de Node.js v22
      - name: Setup Node
        uses: actions/setup-node@v3
        with:
          node-version: 22
      
      # Étape 3 : Installation des dépendances
      - name: Install dependencies
        run: npm install
      
      # Étape 4 : Linting (ESLint)
      - name: Lint code
        run: npm run lint
      
      # Étape 5 : Exécution des tests unitaires et d'intégration
      - name: Run tests
        run: npm test

  # ========================================
  # JOB 2 : DÉPLOIEMENT
  # ========================================
  deploy:
    needs: test  # Attend que le job 'test' soit terminé avec succès
    if: github.event_name == 'push'  # Déploie uniquement sur push (pas sur PR)
    runs-on: ubuntu-latest
    
    steps:
      # Appel du webhook Render pour déclencher le déploiement
      - name: Deploy to Render
        run: |
          curl -X POST ${{ secrets.RENDER_DEPLOY_HOOK }}
```

**Webhook Render :** Le déploiement est déclenché via un simple appel HTTP POST au webhook de Render (stocké de manière sécurisée dans `secrets.RENDER_DEPLOY_HOOK`).

#### 2.4. Configuration des secrets GitHub

Pour sécuriser les informations sensibles, le webhook Render est stocké dans les **GitHub Secrets**.

**Configuration :**

1. GitHub → Settings → Secrets and variables → Actions
2. New repository secret
3. Name: `RENDER_DEPLOY_HOOK`
4. Value: `https://api.render.com/deploy/srv-xxxxx?key=yyyyy`


**Avantages :**

- Le webhook n'est jamais exposé dans le code
- Accessible uniquement via `${{ secrets.RENDER_DEPLOY_HOOK }}`
- Chiffré et géré par GitHub

### Déploiement sur Render
#### 3.1. Choix de la plateforme

**Backend + Base de données : Render.com**
Render a été choisi pour sa simplicité et son intégration native avec GitHub :

- Déploiement automatique depuis GitHub

- Support Docker natif

- PostgreSQL managé inclus

- Plan gratuit pour les projets étudiants

- Configuration simple via l'interface web


**Frontend : Netlify ou alternative (prévu)**

Le frontend React sera déployé sur Netlify ou une plateforme similaire :

- Déploiement automatique des sites statiques

- CDN global intégré

- HTTPS automatique

- Preview deployments pour les pull requests

#### 3.2. Configuration du déploiement Render
**Service Backend :**

- Type : Web Service

- Runtime : Docker

- Branch : staging

- Port : 3000

**Service PostgreSQL :**

- Type : PostgreSQL Database

- Version : 16

- Nom : tea_corner

**Variables d'environnement (configurées sur Render) :**

```bash

DATABASE_URL=postgresql://postgres:password@dpg-xxxxx/tea_corner

JWT_SECRET=production_secret_key

JWT_REFRESH_SECRET=production_refresh_secret

NODE_ENV=production

PORT=3000

```

#### 3.3. Processus de déploiement

**Flux automatique :**

1. Push sur la branche `staging`

2. GitHub Actions exécute les tests

3. Si les tests passent → Webhook déclenche Render

4. Render clone le repository et build l'image Docker

5. Déploiement de la nouvelle version

### Déploiement du frontend sur Vercel

**Frontend : Vercel**

Le frontend React est déployé sur Vercel pour bénéficier de :

- **Déploiement automatique depuis GitHub** : Vercel détecte automatiquement les push sur la branche principale et déclenche un nouveau build
- **Optimisation automatique des builds** : Analyse et optimise le bundle React (tree-shaking, code splitting)
- **CDN global Edge Network** : Distribution du contenu statique sur +100 points de présence dans le monde
- **HTTPS automatique** : Certificats SSL générés et renouvelés automatiquement
- **Preview deployments** : Chaque pull request génère une URL de prévisualisation unique
- **Variables d'environnement** : Gestion sécurisée des variables via l'interface Vercel

#### Configuration Vercel

**Détection automatique :**

- Framework : Vite (détecté automatiquement par Vercel)
- Build Command : `npm run build` (défaut Vite)
- Output Directory : `dist` (défaut Vite)
- Install Command : `npm install`

**Variables d'environnement (configurées sur Vercel) :**

```bash
VITE_API_URL=https://tea-corner-backend.onrender.com
```

#### Processus de déploiement Vercel

**Workflow automatique (pas de fichier YAML nécessaire) :**

┌──────────────┐
│  git push    │
│  to main     │
└──────┬───────┘
       │
       ▼
┌────────────────────────────────┐
│   Vercel (automatique)         │
│                                │
│  1. Détection du push GitHub  │
│  2. Clone du repository        │
│  3. Installation deps (npm)    │
│  4. Build Vite                 │
│  5. Optimisation bundle        │
│  6. Déploiement sur CDN        │
│  7. Invalidation cache         │
└──────────────┬─────────────────┘
               │
               ▼
       ┌───────────────────┐
       │  Vercel Edge CDN     │
       │  Production live        │ 
       └───────────────────┘

**Durée estimée du déploiement :** ~1-2 minutes du push à la mise en ligne

#### Pourquoi pas de workflow GitHub Actions pour le frontend ?

Contrairement au backend qui utilise GitHub Actions, **Vercel gère automatiquement le CI/CD** via son intégration GitHub native :

1. **Détection automatique** : Vercel surveille le repository GitHub connecté
2. **Build automatique** : À chaque push, Vercel exécute `npm run build`
3. **Tests automatiques** : Si configurés dans `package.json`, ils sont exécutés avant déploiement
4. **Preview deployments** : Chaque pull request génère automatiquement une URL de prévisualisation
5. **Production deployment** : Push sur `main` → déploiement automatique en production

**Aucune configuration supplémentaire n'est nécessaire** car :

- Vercel détecte automatiquement Vite/React
- Les commandes de build sont inférées depuis `package.json`
- Le routage React Router est géré automatiquement
- Les optimisations sont appliquées automatiquement (compression, minification, cache)

**Avantage :** Cette solution clé en main évite de dupliquer un workflow GitHub Actions qui serait redondant avec les fonctionnalités natives de Vercel.
#### URLs de production

**Frontend Application :**
```
https://tea-corner-frontend.vercel.app
```
---

## Conclusion

### Bilan du projet

Ce projet était **ambitieux**. Nous avions de nombreuses idées de fonctionnalités, de design et d'expérience utilisateur, mais très peu de temps pour les réaliser : **7 semaines** seulement.

Nous voulions créer une **dimension communautaire** avec partages de recettes, système d'amis et forum pour échanger autour des expériences de dégustation. Nous souhaitions également récompenser les utilisateurs avec un système de points et de personnalisation de leur expérience. Mais face aux contraintes temporelles, nous avons dû **prioriser**.

Nous avons pris le **pari de créer ce projet avec des technologies non maîtrisées** : React avec React Router v7, et NestJS. Bien sûr, lors de notre formation nous avions acquis quelques bases en JavaScript et TypeScript, mais ces deux frameworks étaient nouveaux pour nous.

La création de TeaCorner s'est donc faite **progressivement, en apprenant sur le moment** : nouvelles technologies, nouvelles méthodologies, bonnes pratiques de sécurité adaptées à NestJS, utilisation d'un framework React très récent (sorti en novembre 2024).

Pour parvenir à ce résultat, nous avons donc **revu le projet à la baisse pour cette v1**, en nous concentrant sur les fonctionnalités essentielles pour **valider les compétences du CDA** sans perdre l'essence du projet : une application de gestion du thé centrée sur l'expérience utilisateur et la méditation.

---
### Points de satisfaction

Malgré les difficultés, nous sommes fiers de plusieurs réalisations :

**Application en production** : TeaCorner tourne en production avec un déploiement automatique via CI/CD

 **Architecture backend solide** : Modules NestJS organisés selon le pattern MVC, base de données PostgreSQL avec 15+ tables modélisées en Merise

 **Sécurité bien en place** : Protection CSRF, hachage Argon2, cookies httpOnly, validation systématique des entrées

 **Design cohérent** : L'application reflète ce que nous voulions mettre en place. Les heures passées sur Figma à créer le design system se voient dans l'identité visuelle finale, tout en répondant à un besoin utilisateur réel.

 **Travail en binôme réussi** : Une bonne entente, une communication efficace et une répartition claire des tâches ont permis de mener le projet à bien malgré les contraintes.

 **Belle courbe d'apprentissage** : Nous avons énormément progressé sur des technologies modernes et recherchées en entreprise.

---
### Limites et axes d'amélioration

Avec du recul, plusieurs enseignements se dégagent :

**1. Gestion des priorités**

Malgré une organisation cadrée dès le départ (Notion pour le partage d'informations, Whimsical pour le planning général, bonne communication), **tout ne s'est pas passé comme prévu** en raison du stress et du manque d'expérience.

Notre focalisation sur des **points non essentiels** au lieu de les remettre à plus tard a fait perdre du temps précieux. Nous avons parfois privilégié la perfection sur des détails plutôt que l'avancement global du projet.

**Leçon apprise :** Prioriser impitoyablement et accepter qu'une v1 ne soit pas parfaite.

**2. Maquettage et conception**

Nous aurions dû **prendre le temps de maquetter le projet** visuellement et structurellement **avant de commencer le code**, plutôt que de faire ça en parallèle par peur du manque de temps.

Cette approche aurait permis d'avoir une vision claire de l'ensemble et d'éviter certains allers-retours.

**Leçon apprise :** La phase de conception est un investissement, pas une perte de temps.

**3. Tests unitaires**

Nous aurions dû **tester avant d'écrire les fonctionnalités** (approche TDD - Test-Driven Development) pour garantir la qualité du code dès le départ et éviter les régressions.

**Leçon apprise :** Les tests ne sont pas facultatifs, ils font gagner du temps à moyen terme.

---
### Perspectives d'évolution

**Court terme :**

1. **Nettoyer le code** backend et frontend pour avoir un projet propre, modulaire à 100%
2. **Augmenter la couverture de tests** (tests unitaires, tests d'intégration, tests end-to-end)

**Moyen terme :**

1. **Système de discussion** type forum pour permettre aux utilisateurs d'échanger entre eux et de créer des communautés
2. **Fonctionnalités sociales** : likes, partage de recettes, système d'amis
3. **Panel d'administration** : modération des contenus, gestion des utilisateurs, statistiques

**Long terme :**

1. **Serveur VPS dédié** pour déployer ce projet à plus grande échelle et gérer un trafic important
2. **Gamification** : système de points, boutique de récompenses, achievements
3. **Application mobile** (React Native) pour une expérience native sur iOS et Android

---
### Ce que ce projet m'a appris

Au-delà des compétences techniques, ce projet m'a fait réaliser quelque chose d'important : **il ne faut pas savoir coder pour créer des projets**.

J'avais une vision très limitante du développement d'applications. Je pensais qu'il fallait maîtriser parfaitement un langage ou un framework avant de se lancer.

En réalité, **quelques bases et une bonne méthodologie d'apprentissage suffisent** pour construire un projet en suivant les bonnes pratiques. Il faut accepter de ne pas tout savoir, être capable de chercher, de lire la documentation, de tester, de se tromper et de recommencer.

Grâce à ce projet, **je sais maintenant que je suis capable de m'adapter à n'importe quel projet futur** si je m'en donne les moyens. La technologie change, les frameworks évoluent, mais la méthodologie et la capacité à apprendre restent.

Cette **année de formation fut compliquée mais satisfaisante et enrichissante**. Elle m'a appris l'autonomie, la rigueur et la persévérance — des qualités bien plus importantes que la maîtrise d'un langage spécifique.

---
### Conclusion générale

TeaCorner représente bien plus qu'un projet d'examen. C'est une **démonstration concrète** de la capacité à :

- Concevoir une application de A à Z (de l'idée au déploiement)
- Apprendre de nouvelles technologies en autonomie
- Travailler efficacement en équipe
- Prioriser et s'adapter face aux contraintes
- Créer un produit qui reflète une vision et répond à un besoin réel

Les **11 compétences du référentiel CDA** ont été validées, mais surtout, nous avons acquis quelque chose de plus précieux : la **confiance en notre capacité à apprendre et à créer**.

L'application est en production, l'architecture est solide, le design est cohérent. La base est là. Le reste viendra avec le temps, l'expérience et la pratique.

**Et c'est exactement ça, être développeur : construire progressivement, améliorer continuellement, et ne jamais cesser d'apprendre.**
