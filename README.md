# Projet Strapi + Flutter Web : Guide de démarrage rapide

### 1. Création et configuration du CMS Strapi

#### Installation et création du projet Strapi

 - npx create-strapi-app@latest nom-cms --quickstart
 - Lors de la création, tu peux ignorer la connexion Strapi Cloud (option « Skip »)
    .Strapi s’installe avec SQLite par défaut, parfait pour du dev local.
    .À la fin, démarre Strapi avec :
    .cd mon-cms
    .npm run develop
 - Ouvre l’interface d’administration dans le navigateur à l’adresse :
    . http://localhost:1337/admin
    . Crée ton compte administrateur

#### Création des contenus
Dans le menu « Générateur de types de contenu », crée un type de collection Produit avec les champs souhaités : 
 - NomDuProduit (texte)
 - descriptionCompleteDuProduit (texte long)
 - lePrix (nombre)
Sauvegarde, puis publie quelques produits via l’interface.

#### Test de l’API REST
Strapi expose automatiquement une API REST pour ton contenu.
 - Par exemple, tu peux récupérer les produits avec :
   . GET http://localhost:1337/api/produits
 - Pour tester, utilise Postman ou simplement ton navigateur.

### 2. Création d’une app Flutter Web consommant l’API Strapi

#### Configuration initiale

 - Crée ton projet Flutter :
    . flutter create mon_app_strapi
    . cd mon_app_strapi

#### Ajout des dépendances HTTP
  . Dans pubspec.yaml, ajoute :
     dependencies:
     flutter:
     sdk: flutter
     http: ^0.13.
  . Puis :
     flutter pub get
  
#### Exemple simple de requête GET et affichage

#### Remarques / Conseils

 - Pour la prod, configure une base de données externe (PostgreSQL, MySQL, etc.).
 - Pense à sécuriser l’API avec authentification JWT si besoin.
 - Sur Flutter, envisage un package comme flutter_bloc ou provider pour gérer l’état.
 - Utilise flutter_dotenv pour gérer les URLs API selon l’environnement.