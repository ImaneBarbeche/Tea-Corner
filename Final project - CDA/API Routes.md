## Authentication

- Register (POST/auth/register)
- Login (POST/auth/login)
- Email verification (POST/auth/verify-email)
- Logout (POST/auth/logout)
- Refresh token (POST/auth/refresh)
- Forgotten password (POST/auth/forgot-password)
- Password reset (PATCH/auth/reset-password)

## Admin (future implementation)

Get ALL users
Find one by username
Voir le profile des utilisateurs pour l'admin avec toutes les infos (sauf password?)

## User Management 

- Update profile (PATCH/users/profile) - check that the person is the user logged in
- Update password (PATCH/users/password)
- Delete account (DELETE/users/account)
- View profile (GET/users/profile)
- View stats (GET/users/stats)

- Mes favoris (GET/users/favorites)
- Modifier mes favoris (POST/users/favorites/:teaId)
- Supprimer mes favoris (DELETE/users/favorites/:teaId)

- Mes collections (GET/collections)
- Créer une collection (POST/collections)
- Modifier une collection (PATCH/collections/:id)
- Supprimer une collection (DELETE/collections/:id)
- Ajouter un thé à une collection (POST/collections/:id/teas/:teaId)
- Supprimer un thé d'une collection (DELETE/collections/:id/teas/:teaId)

## Tea

- Liste des thés (avec filtres, recherche, pagination) (GET/teas)
- Détails d'un thé (GET/teas/:id)
- Créer une recette (authentifié user ou admin) (POST/teas)
- Modifier sa recette (PATCH/teas/:id)
- Supprimer sa recette (DELETE/teas/:id)
- Mes recettes créées (GET/teas/my-teas)
- Accord avec autres thés (GET/teas/:id/pairings)
### Brew Logs

- Historique des préparations (GET/brew-logs)
- Détails d'une préparation (GET/brew-logs/:id)
- Enregistrer une préparation (POST/brew-logs)
- Modifier une note de préparation (PATCH/brew-logs/:id)
- Supprimer un log (DELETE/brew-logs/:id)

- Dernières préparations (GET/brew-logs/recent)
- Statistiques (GET/brew-logs/stats)

### Categories already in app

- Catégories du système (GET/categories)

### Ingredients

- Liste des ingrédients (avec filtres par type) (GET/ingredients)
- Créer un ingrédient (POST/ingredients)
- Modifier son ingrédient (PATCH/ingredients/:id)
- Supprimer son ingrédient (DELETE/ingredients/:id)

### Points

- Historique de points (GET/points)
- Total de points (GET/points/total)

### Tea Style

- Liste des styles (matcha) (GET/tea-styles)
- Filtre par style ou type de thé (GET/tea-styles)

### Flavour profiles

- Liste des profils de saveurs (GET/flavour-profiles)



## **Ordre d'implémentation recommandé**

### **Sprint 1 - Core Features**

1. Auth (register, login, logout)
2. Users (profile CRUD)
3. Teas (CRUD basique)
4. Ingredients (GET, liste)

### **Sprint 2 - Collections & Favorites**

5. Categories (GET)
6. Tea-styles, Flavor-profiles (GET)
7. Favorites
8. Collections personnelles

### **Sprint 3 - Tracking & Stats**

9. Brew logs (CRUD)
10. Brew logs stats
11. Points system

### **Sprint 4 - Advanced Features**

12. Tea pairings
13. Adjust portions
14. Advanced filters & search
15. Email verification, password reset