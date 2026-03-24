# TP 0 — Développement Web avec Jakarta EE, Hibernate et DAO Générique

## 📚 Cours
Développement JakartaEE : Architecture N-Tiers et Persistance

---

## Contexte

#### Ce TP constitue une mise en pratique fondamentale des technologies Jakarta EE modernes. L'objectif est de construire une application de gestion d'inventaire robuste en utilisant le pattern DAO Générique, permettant ainsi une séparation claire entre la logique métier et l'accès aux données.

#### Le projet met l'accent sur l'utilisation de Hibernate 6 pour le mapping objet-relationnel (ORM) et sur la transition vers l'espace de nom jakarta.*.

---

## Objectifs

#### - Configurer un environnement Jakarta EE 9+ avec Tomcat 10
#### - Maîtriser le mapping JPA/Hibernate avec plusieurs entités (User et Product)
#### - Implémenter un DAO Générique pour factoriser le code CRUD
#### - Développer des Servlets pour orchestrer les requêtes HTTP
#### - Créer des interfaces dynamiques avec JSP et JSTL
#### - Gérer la persistance dans une base de données MySQL

---

## Technologies utilisées

- **Java 11+**
- **Jakarta EE 9** (Servlet 5.0, JSP 3.0)
- **Hibernate 6.0.0.Final** (JPA Provider)
- **Maven** (Gestionnaire de dépendances)
- **MySQL 8.0**


---

##  Structure du projet


<img width="1276" height="875" alt="image" src="https://github.com/user-attachments/assets/0df2a5d9-a035-4525-9e37-4123c85025a7" />

<img width="1266" height="858" alt="image" src="https://github.com/user-attachments/assets/22912ebc-5abe-4cc9-9117-a14f33e8073b" />



## Installation et lancement
#### 1. Préparation de la base de données :
Créer la base de données dans MySQL :
CREATE DATABASE IF NOT EXISTS inventorymanagement;
#### 2. Configuration :
Modifier le fichier src/main/resources/hibernate.cfg.xml avec vos identifiants MySQL (User/Password).

#### 3. Compilation :
mvn clean install
#### 4. Déploiement :
Configurer un serveur Tomcat 10.x dans IntelliJ.

Ajouter l'artifact inventory-management:war exploded.

Définir le context path sur /tp0_spring.

Lancer le serveur.

#### - L'application est accessible sur : http://localhost:8081/tp0_spring/
## Composants clés
### GenericDAO.java & GenericDAOImpl.java
#### Interface et implémentation abstraite regroupant les méthodes save, update, delete et findAll. Utilise les types génériques <T, ID>.
### UserDAO.java & ProductDAO.java
#### Classes spécifiques héritant du DAO générique et ajoutant des méthodes métier (ex: findByEmail, findBySku).
### HibernateUtil.java
#### Singleton gérant la SessionFactory pour assurer une gestion efficace des sessions Hibernate.
### UserListServlet.js & ProductListServlet.js
#### Contrôleurs récupérant les données via les DAOs et les transmettant aux pages JSP via request.setAttribute.
## Aperçu des fonctionnalités

![WhatsApp Image 2026-03-24 at 15 09 25](https://github.com/user-attachments/assets/910bf125-82f5-42fa-8dd8-7d5333d06f69)

![WhatsApp Image 2026-03-24 at 15 14 10](https://github.com/user-attachments/assets/c80363f4-8220-4cda-a783-ff55f8e8239e)


#### - Tableau de bord : Accueil avec accès rapide aux modules.
#### - Gestion des Utilisateurs : CRUD complet (Création, Affichage, Modification, Suppression).
#### - Gestion des Produits :
#### - Enregistrement avec validation du SKU unique.
#### - Suivi des stocks (Badge de couleur selon la quantité).
#### - Recherche filtrée par mot-clé.
## Conclusion
#### Ce TP m'a permis de maîtriser l'intégration d'un framework ORM (Hibernate) dans une application Web Jakarta EE :
 - Utilisation du DAO Générique pour réduire drastiquement la duplication de code.
 - Compréhension du cycle de vie des entités (Transient, Persistent, Detached).
 - Manipulation des Servlets pour le routage et des JSP pour le rendu.
- Configuration avancée d'un serveur d'application moderne (Tomcat 10).
