# 🎶 Emusic – Application Web de Gestion d'École de Musique

Emusic est une application web développée avec le framework **Symfony**. Elle permet aux écoles de musique de gérer l'ensemble de leur activité : instruments, cours, élèves, professeurs, inscriptions, paiements, etc.

## 🚀 Fonctionnalités principales

- 🧑‍🏫 Gestion des **professeurs** et de leurs spécialités
- 🎻 Gestion du **parc instrumental**, des accessoires, des prêts et de la maintenance
- 📅 **Planification des cours** et emploi du temps par salle et professeur
- 👨‍👩‍👧‍👦 Gestion des **élèves** et **inscriptions**
- 💰 Calcul automatique des **tarifs** selon quotient familial
- 🔐 **Authentification** et gestion des rôles : administrateur, professeur, élève/parent
- 📊 Tableau de bord personnalisé selon le rôle de l'utilisateur

## 🛠️ Stack technique

| Élément         | Technologie              |
|----------------|--------------------------|
| Frontend       | HTML / CSS / JS (Twig)   |
| Backend        | PHP (Symfony 6.4)        |
| Base de données| MySQL                    |
| Sécurité       | Symfony Security Bundle, CSRF Protection |
| ORM            | Doctrine ORM             |

## 📸 Aperçus

- Tableau de bord
- Interface de gestion des instruments
- Planning hebdomadaire des cours
- Gestion des inscriptions et paiements
- Administration des comptes utilisateurs

## 🧩 Architecture

L’application suit l’architecture MVC (Modèle-Vue-Contrôleur) de Symfony avec :
- Des entités Doctrine fortement liées (élève ↔ professeur ↔ cours ↔ instrument)
- Un routage RESTful pour une navigation claire
- Une gestion des rôles centralisée via le Security Bundle

## ⚙️ Installation

### Prérequis

- PHP ≥ 8.1
- Composer
- MySQL
- Symfony CLI (optionnel mais recommandé)

### Étapes

- git clone https://github.com/BocquetMa/emusic.git
- cd emusic
- composer install
- cp .env .env.local

# Modifier .env.local avec vos informations MySQL
- php bin/console doctrine:database:create
- php bin/console doctrine:migrations:migrate
- symfony serve

Accédez à l’application sur : http://127.0.0.1:8000

✅ Compte démo
Rôle	Identifiants
Admin	admin@emusic.fr / admin123
Professeur	prof@emusic.fr / prof123
Élève/Parent	eleve@emusic.fr / eleve123

Les comptes sont préremplis avec des données fictives pour test.

🧠 Défis rencontrés
Modélisation des entités relationnelles : gestion des dépendances complexes entre cours, instruments, professeurs et élèves → utilisation optimale de Doctrine

Tarification variable : calculs dynamiques selon le quotient familial et le type de cours → système flexible configurable par les admins

Gestion multi-rôles : affichage conditionnel des interfaces et sécurisation des accès selon les permissions
