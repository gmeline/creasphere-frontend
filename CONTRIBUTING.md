# Contribuer à Creasphere (frontend)

Ce document définit les règles de nommage des branches, des commits et des Pull Requests (PR) pour garder un historique Git lisible et cohérent.

---

## 1. Branches

La branche `main` est la branche stable : on n'y pousse **jamais** directement. Tout passe par une branche dédiée puis une PR.

| Préfixe | Usage | Exemple |
|---|---|---|
| `feature/<nom-court>` | Nouvelle fonctionnalité | `feature/header` |
| `fix/<nom-court>` | Correction d'un bug | `fix/mobile-menu-scroll` |
| `chore/<nom-court>` | Configuration, dépendances, outillage | `chore/install-tailwind` |
| `docs/<nom-court>` | Documentation uniquement | `docs/readme` |

Règles :
- Nom en minuscules, mots séparés par des tirets (`kebab-case`).
- Une branche = une issue (une US).
- Toujours partir d'un `main` à jour :
```bash
  git checkout main
  git pull
  git checkout -b feature/<nom-court>
```

---

## 2. Commits (Conventional Commits)

Format : `<type>: <description courte à l'impératif, en minuscules>` (pas d'espace avant les deux-points).

| Type | Usage | Exemple |
|---|---|---|
| `feat:` | Nouvelle fonctionnalité | `feat: add Hero section` |
| `fix:` | Correction de bug | `fix: close mobile menu on link click` |
| `chore:` | Config, dépendances, outillage | `chore: install react-router-dom` |
| `docs:` | Documentation | `docs: add installation steps to README` |
| `refactor:` | Réécriture sans changement de comportement | `refactor: extract CreationCard component` |
| `test:` | Ajout ou modification de tests | `test: add ContactForm validation tests` |

Règles :
- Un commit = un changement logique (éviter les commits fourre-tout).
- Pas de point final dans la description.
- Description de 72 caractères maximum.

---

## 3. Pull Requests

- **Titre** au format : `[Phase X] Titre`
  Exemple : `[Phase 5] Composant Header`
- **Description obligatoire**, contenant au minimum :
  - Ce que fait la PR (2-3 lignes).
  - Comment la tester.
  - `Closes #<numéro de l'issue GitHub>` pour fermer automatiquement l'issue au merge.

> ⚠️ Le numéro à mettre après `Closes #` est le **numéro GitHub de l'issue** (affiché à côté de son titre), pas le numéro CREA.

Modèle de description :

```markdown
## Ce que fait cette PR
...

## Comment tester
1. ...
2. ...

Closes #<numéro>
```

---

## 4. Review

- Au moins **1 approbation** est requise avant tout merge sur `main`.
- Si le projet n'a qu'un seul développeur, une **auto-review documentée** est acceptée : relire le diff dans l'onglet "Files changed" et laisser un commentaire de validation (ex : "Auto-review : diff relu, testé en local avec `npm run dev`").

---

## 5. Merge

- Stratégie par défaut : **Squash and merge** (un seul commit propre par PR sur `main`).
- Le message du commit squashé reprend le titre de la PR au format Conventional Commits.
- Supprimer la branche après le merge.
