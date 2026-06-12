# CI/CD TP – Nginx Docker GitHub Actions

## Présentation

Ce projet a été réalisé dans le cadre du TP CI/CD.

L'objectif est de mettre en place une pipeline GitHub Actions permettant de vérifier automatiquement une application Nginx conteneurisée avant son déploiement.

## Architecture du projet

```text
ci-cd-tp/
│
├── Dockerfile
├── README.md
│
├── nginx/
│   ├── index.html
│   └── nginx.conf
│
└── .github/
    └── workflows/
        └── pipeline.yml
```

## Description des composants

### Dockerfile

Construit une image Docker basée sur Nginx.

### index.html

Page web servie par le serveur Nginx.

### nginx.conf

Configuration personnalisée du serveur Nginx.

### pipeline.yml

Pipeline GitHub Actions exécutée automatiquement lors d'un push ou d'une Pull Request.

## Fonctionnement du pipeline

Le pipeline effectue les opérations suivantes :

1. Récupération du code source
2. Vérification des fichiers obligatoires
3. Construction de l'image Docker
4. Vérification de la configuration Nginx
5. Démarrage du conteneur
6. Test HTTP
7. Vérification de l'endpoint `/health`

## Schéma de fonctionnement

```text
Push Git
   │
   ▼
GitHub Actions
   │
   ▼
Vérification des fichiers
   │
   ▼
Build Docker
   │
   ▼
Test Nginx
   │
   ▼
Test HTTP
   │
   ▼
Test /health
   │
   ▼
Succès ou Échec
```

omar diallo
