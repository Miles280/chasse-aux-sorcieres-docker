# 🏰 Chasse aux Sorcières - Infrastructure (Docker)

Ce dépôt contient la configuration globale de l'infrastructure du projet via Docker Compose.

## 🏗️ Architecture
- **Reverse Proxy :** Traefik (avec SSL Let's Encrypt automatique)
- **Base de données :** MySQL 8.0
- **Services :** API (Symfony), Site (Angular), Bot Discord (Node.js)

## 🚀 Déploiement
Le projet utilise une **CI/CD via GitHub Actions**. Tout push sur la branche `main` déclenche un déploiement automatique sur le VPS.

### Lancer en local
```bash
git clone git@github.com:Miles280/chasse-aux-sorcieres-docker.git .
git clone git@github.com:Miles280/chasse-aux-sorcieres-api.git api
git clone git@github.com:Miles280/chasse-aux-sorcieres-bot.git bot
git clone git@github.com:Miles280/chasse-aux-sorcieres-site.git site

docker compose up -d
```

## 🔒 Sécurité
- Les données sensibles sont gérées via des fichiers `.env` (non versionnés).
- Accès DB via tunnel SSH uniquement (Port 3306 non exposé publiquement).


