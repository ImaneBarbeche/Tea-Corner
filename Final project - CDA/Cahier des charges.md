### Cahier des charges

#### Identification du problème

Ce projet est un site web qui permet aux utilisateurs de gérer leurs thés tout en étant soucieux et attentif à leur expérience de dégustation.

Actuellement il n'existe pas de plateforme en ligne de gestion de recette de thé qui combine toutes les fonctionnalités mentionnées ci-après en un seul endroit. Les plateformes qui existent permettent soit une gestion de type "journal" de ses propres recettes, où tout est créer manuellement par l'utilisateur, soit une visualisation de recettes de thés, d'accès à un minuteur et de communauté. D'autres proposent uniquement l'aspect méditatif lié à la consommation de thé. De plus, aucune plateforme web n'existe, celles mentionnées ci-dessus sont des applications mobiles. Les seules plateforme de gestion d'infusion de thé sont de simples minuteurs.

Notre application permet de réunir toutes ces fonctionnalités en un site web, tout en apportant la possibilité pour l'utilisateur de customiser son expérience.

#### Présentation Générale

##### 1. Objectif du projet

Ce document présente le cahier des charges visant à la conception et au développement d’une application web en architecture MVC, permettant aux utilisateurs :

- de voir et chercher des recettes de thés (barre de recherche et filtre)
- de créer des nouveaux thés et d'ajouter des ingrédients 
- d'ajouter des recettes à sa librairie 
- de les organiser par catégories ou tags
- de suivre sa consommation de thé
- de recevoir des suggestions en fonction de sa consommation
- d'avoir accès à un minuteur personnalisable en fonction du thé, de la quantité, et de la température
- de pouvoir créer des entrées dans son journal avec des commentaires pour chaque thé consommé

L'application est constituée d'une interface web avec un design responsive mobile first. 


##### 2. Architecture technique

- Front end développé avec React ainsi que Tailwind avec DaisyUI pour le CSS.
- Backend développé en NestJs avec une architecture MVC.
- Sécurité des données (authentification, autorisations, chiffrement, sécurité API, rôles, RGDP).
- Scalabilité et maintenabilité du code (utilisation de conteneurs).
- Base de données (PostgreSQL).
- Hébergement et déploiement (Docker-Docker Compose, CI/CD avec GitHub Actions, Vercel ou GitHub Pages).


#### Fonctionnalités

##### 1. Fonctionnalités Utilisateur

###### 1.1. Authentification / Sécurité

- Inscription avec vérification d'email.
- Connexion sécurisée (JWT et refresh token).
- Récupération / réinitialisation de mot de passe.

###### 1.2. Recettes 

A) Visualisation

- Voir des recettes existantes au niveau de la page d'accueil.
- Effectuer une recherche simple via une barre de recherche parmi des recettes proposées.
- Effectuer des recherches avancées avec un système de filtre (catégories, mots clés, saveurs, ingrédients).
- Utiliser un système de filtre pour l'affichage des recettes sur la page d'accueil.

B) Recettes de thé

- Ajouter des recettes dans sa librairie.
- Voir les détails d'une recette de thé
- Aimé une recette.
- Créer une recette : nom, type de thé (noir, vert), style de thé (matcha, earl grey), description, ingrédients, instructions (température, temps d'infusion, quantité), niveau de caffeine, source, couleur (par défaut basé sur le type de thé choisi). 
- Modifier une de ses recettes : changer le nom, les ingrédients.
- Supprimer ses recettes crées.

C) Minuteur

- Accès à un minuteur indépendamment des recettes.
- Utiliser un minuteur pour infusé son thé.
- Modifier la quantité d'eau, la température d'infusion, le temps d'infusion ainsi que le dosage (quantité de thé).
- Utiliser un minuteur en mode "focus" : minuteur qui reste actif tant que l'utilisateur reste sur la page (UI différent), citations ("prends ton temps", "prends une grande inspiration") pour l'aspect méditatif. 
- Etre notifié quand le temps d'infusion est terminé.
- Avoir la possibilité d'écrire un commentaire et d'ajouter un profil de saveur pour chaque thé consommés qui seront archiver dans une page "Brew Logs".

D) Statistiques et points

- Avoir accès à son suivi de consommation de thé dans sa page de profil.
- Avoir le nombre de thé archivé, infusé ou infusé en mode "focus".
- Avoir des suggestions basées sur sa consommation ("vous aimez le thé vert, essayez ces recettes").
- L'utilisateur gagne des points en fonction du type de minuteur utilisé, du nombre d'archivage effectué et du nombre de thé consommé.


#### Perspectives d'évolution et améliorations futures

- Partager son profil avec d'autres utilisateurs.
- Ajouter des amis.
- Partager des recettes dans la communauté.
- Noter des recettes et partager ses commentaires avec d'autres utilisateurs.
- Recommander des recettes.
- Un système de messagerie de type forum.
- Une boutique dans laquelle l'utilisateur peut échanger les points qu'il a gagné contre des objets personnalisés.


#### Organisation et méthodologie du projet

GitHub sera utilisé pour la gestion de version, tandis que Whimsical servira pour le suivi des tâches.
On utilisera Notion pour la planification et Figma pour la création de la maquette ainsi que Db Diagram pour le schéma de la base de données.
