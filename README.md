# Fitness Challenge - Frontend

Ce projet contient le frontend de l'application Fitness Challenge. Il est conçu pour être déployé séparément et se connecter à une API backend existante.

## Configuration

L'URL du backend est configurable via la variable d'environnement `VITE_API_URL`.

- **Backend par défaut** : `http://localhost:5000/api`
- **Backend actuel (Hébergé)** : `https://fitness-challenge-api.pulseverse.shop/api`

### Configuration en local

Pour configurer l'URL de l'API en local, créez ou modifiez le fichier `.env.local` à la racine :

```env
VITE_API_URL=https://fitness-challenge-api.pulseverse.shop/api
```

## Installation et Lancement (Développement)

1.  Installez les dépendances :
    ```bash
    npm install
    ```

2.  Lancez le serveur de développement :
    ```bash
    npm run dev
    ```

    Le frontend sera accessible sur `http://localhost:5173` (ou le port indiqué).

## Déploiement

Le frontend peut être déployé sur n'importe quel hébergeur de fichiers statiques ou conteneurs.

### Option 1 : Docker

Pour construire et exécuter le frontend via Docker en pointant vers le backend hébergé :

```bash
docker build -t fitness-frontend --build-arg VITE_API_URL=https://fitness-challenge-api.pulseverse.shop/api .
docker run -p 3000:80 fitness-frontend
```

(Note : Assurez-vous d'être dans le dossier contenant le Dockerfile)

### Option 2 : Vercel / Netlify / Static Hosting

1.  Connectez votre dépôt Git à la plateforme.
2.  Configurez le dossier racine si nécessaire (ici `.`).
3.  Définissez la variable d'environnement `VITE_API_URL` avec la valeur de votre backend (ex: `https://fitness-challenge-api.pulseverse.shop/api`).
4.  Commandes de build :
    - **Build Command** : `npm run build`
    - **Output Directory** : `dist`

## Structure du Projet

- `src/lib/api.ts` : Contient la configuration de l'API et les appels fetch.
- `src/pages` : Les pages de l'application (Dashboard, Login, Register, etc.).
- `vite.config.ts` : Configuration de Vite.
