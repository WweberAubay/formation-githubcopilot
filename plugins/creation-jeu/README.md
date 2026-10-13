# creation-jeu

Demandez « fais-moi un casse-briques » : l'agent crée un mini-jeu jouable dans le navigateur, avec une structure de code, des contrôles, des effets et un tableau des meilleurs scores décidés d'avance.

## Contenu

| Composant | Emplacement | Rôle |
| --- | --- | --- |
| Skill `creer-jeu` | `skills/creer-jeu/` | Procédure : repérer le projet (TypeScript ou JavaScript), classe `Game` qui porte le canvas, l'état et la boucle, contrôles clavier, souris et tactile, difficulté croissante, rendu arcade (néon, particules, tremblement), bruitages Web Audio, scores enregistrés dans `localStorage`, partie complète jouée pour vérifier. |

Le plugin suit le format Agent Plugins 1.0 : la skill est portable et ne contient aucun script.

## Utilisation

- `/creation-jeu:creer-jeu un casse-briques` dans le chat, ou simplement « fais-moi un snake » : la skill se charge d'après sa description.
- Quand la demande est vague, l'agent choisit des valeurs raisonnables (taille de la zone, vitesse, nombre de vies) et les indique dans son résumé final plutôt que de poser des questions.
- Le jeu est créé dans `src/games/<nom-du-jeu>/`, avec un lien depuis le menu du projet s'il en a un, sinon sur une page autonome.

## Prérequis

Un navigateur pour jouer ; un projet web (Vite, par exemple) pour le lancer. Aucune dépendance n'est imposée.

## Sécurité et confidentialité

La skill n'exécute rien par elle-même et n'envoie rien hors de la machine : elle guide l'agent, qui écrit des fichiers dans votre projet. Les scores restent dans le `localStorage` du navigateur.
