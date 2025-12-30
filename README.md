## 🏰 Chasse aux Sorcières — Infrastructure (Docker)

Ce dépôt contient la **configuration globale de l’infrastructure** du projet via **Docker Compose**.
Il orchestre l’ensemble des services nécessaires au bon fonctionnement de l’écosystème.

---

### 🏗️ Architecture

* **Reverse Proxy :** Traefik

  * SSL automatique via Let’s Encrypt
* **Base de données :** MySQL 8.0
* **Services applicatifs :**

  * API Symfony
  * Site Angular
  * Bot Discord

---

### 🚀 Déploiement

Le dépôt est relié à une **CI/CD GitHub Actions**.
Chaque push sur la branche `main` :

* met à jour les images Docker
* redéploie automatiquement les services sur le VPS

---

### ▶️ Lancement en local

```bash
git clone git@github.com:Miles280/chasse-aux-sorcieres-docker.git .
git clone git@github.com:Miles280/chasse-aux-sorcieres-api.git api
git clone git@github.com:Miles280/chasse-aux-sorcieres-bot.git bot
git clone git@github.com:Miles280/chasse-aux-sorcieres-site.git site

docker compose up -d
```

---

### 🔒 Sécurité

* Les données sensibles sont stockées dans des fichiers `.env` (non versionnés)
* La base de données n’est **pas exposée publiquement**
* Accès possible uniquement via **tunnel SSH**
* Le port `3306` reste fermé à l’extérieur
