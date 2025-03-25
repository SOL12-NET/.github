# 🧠 Crypto Chronicle Harvester

**Crypto Chronicle Harvester** est une suite d'outils destinée à collecter, transformer, analyser et historiser l'ensemble des données relatives aux cryptomonnaies.  
Elle repose sur une architecture modulaire, évolutive et optimisée pour le stockage temporel, l'analyse et la scalabilité.

## 🧩 Structure de l'organisation

Ce projet est découpé en plusieurs **repos spécialisés** au sein de l'organisation GitHub :

| Repository | Description |
|------------|-------------|
| [`rss-harvester`](https://github.com/SOL12-NET/rss-harvester) | Extraction et analyse de flux RSS crypto (CoinDesk, CryptoPotato, etc.) avec analyse de sentiment |
| [`crypto-chronicle-harvester`](https://github.com/SOL12-NET/crypto-chronicle-harvester) | Scraping Selenium d'Investing.com pour récupérer les données de prix depuis la date de genèse jusqu'à aujourd'hui |
| `futures-data` *(à venir)* | Module de récupération des données de contrats futures sur les principales plateformes |
| `market-intelligence` *(à venir)* | Aggrégation des données sociales, signaux, alertes on-chain |
| `dashboard` *(à venir)* | Interface web de visualisation (dashboards, tendances, backtest) |

> 💡 Chaque module fonctionne indépendamment, mais tous se connectent à la **même base TimescaleDB** pour centraliser les données.

---

## 🔍 Objectifs

- Récupérer **les données les plus complètes possibles** sur le marché des cryptomonnaies (prix, événements, news, indicateurs, futures…)
- Calculer des **indicateurs clés** (variations, corrélations, sentiment, anomalies)
- Fournir une **base TimescaleDB optimisée** pour des requêtes rapides par crypto et timestamp
- Permettre une **visualisation temps réel ou historique**
- Préparer le terrain pour des **analyses prédictives ou des alertes automatisées**

---

## 🛠️ Stack Technique

- **Python 3.x** (pandas, SQLAlchemy, Selenium, TextBlob, feedparser…)
- **PostgreSQL + TimescaleDB** (historisation & performance)
- **Docker / Docker Compose** (containerisation)
- **Selenium headless** (scraping)
- **PgAdmin** (gestion BDD)
- À venir : **FastAPI / Streamlit / Grafana** (visualisation), **Airflow** (orchestration)

---

## 🗃️ Schéma de base de données

| Table              | Description |
|--------------------|-------------|
| `crypto_prices`    | Données OHLCV par jour avec variations J-1 / J-7 / J-30 |
| `crypto_news`      | Données d’actualités avec polarité et source |
| `crypto_events`    | (optionnel) Données d’événements fondamentaux ou contextuels |
| `cryptocurrency`   | Métadonnées sur les cryptos (nom, symbole, date de genèse) |

---

## 🚀 Lancer le projet

Chaque repo inclut un `README.md` détaillé avec :
- Installation des dépendances
- Fichier `.env` à adapter
- Lancement avec Docker (`docker-compose.yml` fourni)
- Mode headless (scraper)
- Instructions pour l’initialisation de la base

---

## 🧑‍💻 Contribuer

Ce projet est amené à évoluer fortement.  
Si tu veux contribuer (parseurs, indicateurs, visualisation, optimisations DBA…), tu es le bienvenu !

---

## 🪪 Auteur

**Mathis Martini**  
🔒 DevSecOps | 🧠 Data + Cybersecurity | 🎯 Performance Oriented

