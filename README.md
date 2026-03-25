# 📊 Retail ETL Pipeline : dbt & Google Cloud Platform

Ce projet implémente une architecture de données moderne (Modern Data Stack) pour transformer des données brutes en tables analytiques prêtes pour le BI dans **BigQuery**. Il utilise **dbt** pour la logique de transformation, **Docker** pour la conteneurisation, et **Terraform** pour déployer l'infrastructure sur **Google Cloud Run Jobs**.

## 🏗️ Architecture Technique

L'ensemble de l'infrastructure est géré via l'Approche "Infrastructure as Code" (IaC) :

* **Data Warehouse** : Google BigQuery (Stockage et calcul).
* **Transformation** : dbt (Data Build Tool) version 1.9.0.
* **Conteneurisation** : Docker (Image basée sur `dbt-bigquery`).
* **Orchestration** : Google Cloud Run Jobs (Exécution scalable).
* **Infrastructure** : Terraform (Provisioning automatique des ressources GCP).
* **CI/CD** : Google Cloud Build pour l'intégration continue.

---

## 📂 Structure du Répertoire

```text
.
├── infra/                # Fichiers de configuration Terraform (IaC)
├── models/               # Modèles SQL dbt (staging & transform)
│   ├── staging/          # Nettoyage et typage initial
│   └── transform/        # Agrégations et logique métier
├── tests/                # Tests de qualité de données (non-null, unique, etc.)
├── .gitignore            # Fichiers exclus de Git (clés JSON, target/, logs/)
├── dbt_project.yml       # Configuration principale du projet dbt
├── packages.yml          # Dépendances dbt (dbt_utils, etc.)
├── Dockerfile            # Instructions de build de l'image de production
└── README.md             # Documentation du projet