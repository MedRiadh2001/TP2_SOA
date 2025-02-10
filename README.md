# TP2 : Création d’une API Restful avec Express JS

Ce document présente le compte rendu du **Travail Pratique 2 (TP2)** du cours **SOA et Microservices**. L'objectif de ce TP est de concevoir et implémenter une API RESTful avec **Express.js** et **SQLite3**, en intégrant **Keycloak** pour la gestion de l'authentification et de l'autorisation.

---

## Objectifs

- Développer une API REST avec Express.js.
- Gérer les données avec SQLite3.
- Implémenter une authentification et une autorisation sécurisées avec Keycloak.
- Tester l'API avec Postman.

---

## Technologies utilisées

- **Node.js** : Environnement d'exécution JavaScript.
- **Express.js** : Framework pour la création d'API REST.
- **SQLite3** : Base de données légère et embarquée.
- **Postman** : Outil pour tester et déboguer les requêtes API.
- **Keycloak** : Solution de gestion des identités et des accès.

---

## Structure du projet

- **`database.js`** : Configuration et initialisation de la base de données SQLite3.
- **`index.js`** : Point d'entrée de l'API, incluant la gestion des routes et l'intégration de Keycloak.
- **`keycloak-config.json`** : Fichier de configuration pour Keycloak.

---

## Instructions d'exécution

1. Clonez ce dépôt sur votre machine locale :

```bash
git clone https://github.com/ton-repo/TP2_SOA.git
```
 2. Installez les dépendances nécessaires :

 ```bash
 npm install
 ```
 3. Démarrez le serveur Node.js :

 ```bash
 node index.js
 ```
 4. Assurez-vous que Keycloak est en cours d'exécution sur `http://localhost:8080/auth`.
 
 5. Accédez à l'API via :
 
 ```
 http://localhost:3030
 ```
 
 ---
 
 ## Routes de l'API
 
 ### 1. Obtenir la liste des personnes
 - **Méthode** : `GET`
 - **URL** : `/personnes`
 - **Description** : Retourne la liste de toutes les personnes dans la base de données.
 - **Exemple de réponse** :
 ```json
{ 
  "message": "success", 
  "data": [ 
    { "id": 1, "nom": "Bob", "adresse": "Paris" }, 
    { "id": 2, "nom": "Alice", "adresse": "Lyon" },
    { "id": 3, "nom": "Charlie", "adresse": "Marseille" }
  ] 
}
 ```
 ### 2. Obtenir une personne par son ID
 - **Méthode** : `GET`
 - **URL** : `/personnes/:id`
 - **Description** : Renvoie les détails d'une personne spécifique.
 
 ### 3. Créer une nouvelle personne
 - **Méthode** : `POST`
 - **URL** : `/personnes`
 - **Description** : Enregistre une nouvelle personne dans la base de données.
 - **Exemple de la requête** :
 ```json
{ 
  "nom": "Charlie", 
  "adresse": "Marseille" 
}
 ```
 - **Exemple de réponse** :
 ```json
{ 
  "message": "success", 
  "data": { "id": 3 } 
}
 ```
 ### 4. Mettre à jour une personne
 - **Méthode** : `PUT`
 - **URL** : `/personnes/:id`
 - **Description** : Met à jour les informations d'une personne existante.
 - **Exemple de la requête** :
 ```json
{ 
  "nom": "Charlie Brown", 
  "adresse": "Nice" 
}
 ```
 - **Exemple de réponse** :
 ```json
{ 
  "message": "success" 
}
 ```
 ### 5. Supprimer une personne
 - **Méthode** : `DELETE`
 - **URL** : `/personnes/:id`
 - **Description** : Supprime une personne de la base de données.
 - **Exemple de réponse** :
 ```json
{ 
  "message": "success" 
}
 ```
 ### 6. Accéder à une route sécurisée
 - **Méthode** : `GET`
 - **URL** : `/secure`
 - **Description** : Accessible uniquement aux utilisateurs authentifiés via Keycloak.  
 ---

 
 ## Auteur
 
 - **Mohamed Riadh Essridi**
 - Classe : 4GL1
