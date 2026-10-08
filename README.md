# Creasphere — Frontend

## Objectif

Site vitrine de Creasphere, artisane graveuse sur verre.
Il présente son savoir-faire, la galerie de ses créations, son parcours, et permet aux visiteurs de la contacter. Les données (créations, techniques, messages) proviennent de l'API [creasphere-backend](https://github.com/gmeline/creasphere-backend).

## Stack technique

- **Node.js** ≥ 18
- **React** + **Vite** (build et serveur de développement)
- **TailwindCSS** (styles)
- **React Router** (navigation)
- **Axios** (appels à l'API)

## Installation

1. Cloner le repo :
   ```bash
   git clone https://github.com/gmeline/creasphere-frontend.git
   cd creasphere-frontend
   ```
2. Installer les dépendances :
   ```bash
   npm install
   ```
3. Copier `.env.example` en `.env` et renseigner les valeurs :
   ```bash
   cp .env.example .env
   ```
   `VITE_API_URL` doit pointer vers l'API backend (ex : `http://localhost:5000/api`).
4. Lancer le serveur de développement :
   ```bash
   npm run dev
   ```
   Le site est accessible sur `http://localhost:5173`.

## Scripts disponibles

| Script | Description |
|---|---|
| `npm run dev` | Lance le serveur de développement Vite avec rechargement à chaud |
| `npm run build` | Génère la version de production dans `dist/` |
| `npm run preview` | Sert localement le build de production pour le vérifier |

## Librairies utilisées

| Librairie | À quoi elle sert |
|---|---|
| *(complété au fil des installations)* | |

## Structure du projet

```
creasphere-frontend/
├── src/
│   ├── api/            # Client API et appels par ressource
│   ├── assets/         # Images, polices, icônes
│   ├── components/
│   │   ├── layout/     # Header, Footer, menus, Layout
│   │   ├── ui/         # Composants réutilisables (cards, modal…)
│   │   └── sections/   # Sections de pages (Hero, Techniques…)
│   ├── hooks/          # Hooks personnalisés
│   ├── pages/          # Une page par route
│   ├── router.jsx      # Déclaration des routes
│   ├── App.jsx
│   └── main.jsx
├── .env.example
├── CONTRIBUTING.md
└── README.md
```

## Conventions de nommage

- **PascalCase** pour les composants et leurs fichiers : `CreationCard.jsx`
- **camelCase** pour les fonctions et les hooks : `useCreations.js`, `getAllCreations()`

## Contribuer

Les conventions de branches, de commits et de Pull Requests sont décrites dans [CONTRIBUTING.md](./CONTRIBUTING.md).
