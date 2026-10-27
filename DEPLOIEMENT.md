# Déploiement Ex6

Application en ligne : https://artificialinquiries.42web.io/omeka-s-cloud/response.html

## Architecture

- `response.html` : interface de consultation, inscription, connexion et demandes CRUD.
- `server/api.php` : backend PHP, sessions, rôles et modération.
- `server/config.php` : configuration privée du serveur **jamais publiée**.
- Omeka S / MySQL : stockage des ressources RDF, des utilisateurs et des demandes.

## Rôles

- Utilisateur : consultation après connexion, soumission de demandes de création, modification et suppression.
- Admin : exécution CRUD et acceptation/refus des demandes.
- Propriétaire : mêmes droits que l'admin, plus attribution et retrait des rôles administrateur.

## Installation

1. Héberger Omeka S sur un serveur PHP/MySQL.
2. Déposer `response.html` et `server/api.php` dans le répertoire de l'instance.
3. Configurer **sur le serveur uniquement** `server/config.php` avec les identifiants MySQL, clés API Omeka et compte propriétaire.
4. Protéger `server/config.php` contre l'accès HTTP.
5. Tester l'inscription, les droits d'accès, la modération et les opérations CRUD.

**Attention :** GitHub Pages ne peut pas exécuter PHP ; l'application complète fonctionne sur l'hébergement PHP. Ne jamais publier de secrets ni d'export SQL contenant des données sensibles.
