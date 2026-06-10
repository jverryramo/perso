# Tableau de bord — administratif & gestion de la maison

Application web autonome (un seul fichier `index.html`) pour suivre les tâches
administratives et d'entretien de la maison sur un **horizon glissant de 18 mois**.

Aucune installation, aucun serveur : tout fonctionne dans le navigateur.

## Fonctionnalités

- **Vue 18 mois** à partir du mois courant, regroupée par mois (avec l'année).
- **Récurrences** : annuelle, semestrielle, trimestrielle, mensuelle ou sans date.
  Une tâche récurrente apparaît automatiquement dans chaque mois concerné, avec
  sa propre case à cocher.
- **Section « À surveiller »** qui calcule ce qui est en retard ou bientôt dû,
  selon un délai de rappel défini par tâche.
- **Catégories gérables** : renommer, recolorer, ajouter, supprimer.
  La catégorie « Autre » est protégée (filet de sécurité).
- **Suivi de l'avancement** sur la période.
- Pré-rempli avec les échéances courantes au Québec (impôts, REER, SAAQ,
  assurances, pneus, entretien maison, etc.) — toutes modifiables.

## Données

Les tâches et catégories sont enregistrées **localement dans le navigateur**
(`localStorage`), sous les clés `admin-tasks-v1` et `admin-cats-v1`.

- Aucune donnée personnelle n'est dans le code : le dépôt peut rester public.
- Les données ne se synchronisent pas entre appareils (un navigateur = un jeu
  de données).
- Vider les données du navigateur efface le suivi.

## Mise en ligne (GitHub Pages)

1. `index.html` doit être à la racine du dépôt.
2. Settings → Pages → « Deploy from a branch » → branche `main`, dossier `/ (root)`.
3. L'application est ensuite accessible à :
   **https://jverryramo.github.io/perso/**

## Mise à jour

Remplacer `index.html` (commit + push). Les données enregistrées dans le
navigateur ne sont pas touchées : une migration automatique gère les anciens
formats au chargement.

## Technique

Fichier unique HTML, React 18 + Babel standalone via CDN, Tailwind via CDN,
icônes SVG en ligne. Rien à compiler.
