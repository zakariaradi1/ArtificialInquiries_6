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
La restauration complète d'Omeka S reste à vérifier.
