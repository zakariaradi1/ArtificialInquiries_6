# Artificial Inquiries — Exercice 6

## Design Your AI Test

### Objectif

L’objectif de cet exercice est de sélectionner des tâches professionnelles représentatives afin de construire un test permettant d’évaluer les capacités et les limites des agents/LLM.

## Ex6a — Classification des tâches

Les tâches identifiées sont classées selon trois catégories :

- **Business** : tâches principalement professionnelles.
- **Pleasure** : tâches réalisées avec intérêt ou plaisir.
- **Business + Pleasure** : tâches appartenant aux deux catégories.

Cette classification permet d'identifier les tâches les plus pertinentes pour la suite de l'exercice.

## Ex6b — Choosing Your Core Four

Quatre tâches principales (**Core Four**) sont sélectionnées parmi les tâches précédentes.

La sélection prend en compte :

- l’importance professionnelle de la tâche ;
- sa diversité ;
- la possibilité de la déléguer à un LLM ;
- le niveau de confiance envers l’IA ;
- l’hésitation éventuelle à déléguer la tâche.

Les quatre tâches doivent permettre de réaliser un test représentatif des capacités d’un LLM.

## Ex6c — What's on the Line?

Pour chaque Core Task, l’exercice consiste à définir :

- le **Task Fit** ;
- la **Professional Relevance** ;
- le **Personal Outcome** ;
- les critères permettant de distinguer un **Failure**, un résultat **Good Enough** et un **Success** ;
- les attentes vis-à-vis du résultat : **Terrible**, **Pretty Bad**, **Good Enough** ou **Excellent**.

Ces éléments serviront ensuite à évaluer les résultats produits par les différents modèles d’IA.

## Diagramme de classes

Le diagramme de classes est réalisé avec **Mermaid**.

Il représente :

- les tâches ;
- les catégories Business / Pleasure ;
- les quatre Core Tasks ;
- l’évaluation des tâches ;
- les critères de résultat ;
- les niveaux d’attente.

Le diagramme est **interactif et cliquable** afin de faciliter la navigation entre les différentes parties du modèle.

Fichier :

`diagram_class.md`

## Technologies

- Markdown
- Mermaid
- Git
- GitHub

## Structure du dépôt

```text
ArtificialInquiries_numEx/
├── README.md
└── diagram_class.md


## Modélisation avec Omeka S

Le projet utilise Omeka S pour représenter les classes,
les propriétés et les relations entre les ressources.

- Vocabulaire RDF personnalisé au format Turtle
- 7 Resource Templates exportés en JSON
- 12 items de test avec des relations RDF
- Export SQL anonymisé

## Technologies utilisées

| Technologie | Utilisation |
|---|---|
| Omeka S | Gestion des ressources sémantiques |
| RDF / Turtle | Vocabulaire et propriétés |
| Mermaid | Diagramme de classes |
| JSON | Export des modèles de ressources |
| MySQL | Base de données |
| MAMP | Serveur local |
| Markdown | Documentation |
| Git / GitHub | Versionnement et publication |

## Fichiers du projet

- `diagram_class.md` : diagramme de classes
- `artificial_inquiries.ttl` : vocabulaire RDF
- `resource-template/` : 7 modèles JSON
- `omk.sql` : export SQL anonymisé

## Résultat

Le projet relie la modélisation conceptuelle à une
implémentation sémantique dans Omeka S.

L'import SQL a été testé avec succès dans MySQL.
La restauration d'Omeka S sur l'hébergement Cloud a été réalisée ; 12 ressources sont visibles dans le tableau de bord.


## Ex6d — Application web Omeka S

**Thème :** Les outils de coordination et d’orchestration d’agents IA.

### Démonstration en ligne

- [Interface web Ex6](https://artificialinquiries.42web.io/omeka-s-cloud/response.html)
- [Omeka S (administration)](https://artificialinquiries.42web.io/omeka-s-cloud/admin)

L’application repose sur **Omeka S 4.2.1**, un vocabulaire RDF personnalisé, **7 modèles de ressources** et **12 ressources de démonstration**. Les relations relient notamment les tâches, catégories, évaluations, critères et niveaux d’attente.

### Fonctionnalités

- Inscription autonome et authentification locale par session PHP.
- Trois rôles : utilisateur, administrateur et propriétaire (super-administrateur).
- Le propriétaire seul peut attribuer ou retirer le rôle administrateur.
- Consultation des ressources après connexion.
- Les demandes de création, modification et suppression soumises par les utilisateurs sont placées **en attente** jusqu’à acceptation ou refus par un administrateur.
- Interface de consultation avec recherche et filtrage par classe RDF.

### Architecture

```text
Navigateur (response.html)
    │
    ▼
Backend PHP (server/api.php) — sessions, rôles, demandes et validation
    │
    ├── MySQL — utilisateurs et demandes
    │
    └── API Omeka S — ressources et relations RDF
```

### Déploiement et confidentialité

Le backend PHP et Omeka S sont hébergés sur InfinityFree. Les identifiants MySQL, clés API, mots de passe et fichiers de configuration privés **ne doivent jamais être publiés sur GitHub ou GitHub Pages**. L’interface statique seule ne remplace pas l’authentification côté serveur. Les ressources Omeka non publiques ne doivent être servies qu’après contrôle de session et de droits.

### État de la démonstration

Le tableau de bord Omeka S et les 12 ressources ont été observés sur l’instance Cloud ; une session administrateur et une demande refusée ont été observées dans l’interface. Le fonctionnement complet des opérations approuvées et les éventuelles connexions CAS, GitHub ou Google doivent être validés séparément avant de les déclarer opérationnels.


## Utilisation et déploiement de la démonstration

L'application est accessible ici : https://artificialinquiries.42web.io/omeka-s-cloud/response.html

**Fonctionnement :** le visiteur crée un compte et se connecte. Il peut consulter les ressources RDF et soumettre une demande de création, modification ou suppression. La demande reste en attente jusqu'à validation ou refus par un administrateur. Le propriétaire peut aussi gérer les rôles administrateurs.

**Architecture :** `response.html` (interface) → `server/api.php` (authentification, sessions, autorisations et modération) → MySQL (utilisateurs et demandes) et API Omeka S (ressources sémantiques).

**Installation :** Omeka S et le backend nécessitent un hébergement PHP/MySQL, ici InfinityFree. Déposer l'interface et le backend sur le serveur et renseigner la configuration privée du serveur. Ne jamais publier `server/config.php`, les identifiants MySQL, les clés API ou les mots de passe sur GitHub. GitHub Pages seul ne peut pas exécuter PHP.

**Démonstration :** https://artificialinquiries.42web.io/omeka-s-cloud/response.html
