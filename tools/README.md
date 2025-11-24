# 🛠️ Outils SYNAPSE

Code source et implémentations des agents IA de SYNAPSE.

---

## 🎯 Vue d'Ensemble

| Agent | Status | Langage | Maturité |
|-------|--------|---------|----------|
| **[Memory Agent](memory-agent/)** | 🟡 En développement | Python | Alpha |
| **[Pattern Agent](pattern-agent/)** | 🔴 Planifié | Python | Q1 2025 |
| **[Simulation Agent](simulation-agent/)** | 🔴 Planifié | Python | Q1 2025 |
| **[Coordination Agent](coordination-agent/)** | 🔴 Planifié | Python | Q2 2025 |

**Légende :**
- 🟢 Production-ready
- 🟡 En développement
- 🔴 Planifié

---

## 🚀 Démarrage Rapide

### Prérequis

```bash
# Python 3.11+
python --version

# Docker & Docker Compose
docker --version

# Git
git --version
```

### Installation

```bash
# Cloner
git clone https://github.com/synapse-origin/synapse.git
cd synapse

# Environnement virtuel
python -m venv venv
source venv/bin/activate  # Linux/Mac

# Dépendances
pip install -r tools/requirements.txt

# Configuration
cp tools/.env.example tools/.env
# Éditer tools/.env avec vos clés API
```

### Démarrer

```bash
# Infrastructure (bases de données)
cd tools
docker-compose up -d

# Memory Agent (seul disponible)
cd memory-agent
python main.py

# Dashboard (optionnel)
cd ../dashboard
npm install && npm run dev
```

---

## 🧠 Memory Agent

**Fonction :** Mémoire organisationnelle

**Capacités :**
- Capture automatique décisions
- Construction graphe de connaissances
- Recherche sémantique
- Détection contradictions

**Stack :**
- Python 3.11+ (FastAPI)
- Neo4j (graphe)
- Pinecone (embeddings)
- Claude API (LLM)

**Status :** 🟡 Alpha

👉 **[Documentation complète](memory-agent/README.md)**  
👉 **[Spécifications](../framework/agents.md#memory-agent)**

---

## 🔍 Pattern Agent

**Fonction :** Détecteur de patterns

**Capacités :**
- Analyse time series
- Clustering patterns
- Alertes temps réel
- Prédictions ML

**Stack :**
- Python 3.11+
- InfluxDB (time series)
- Scikit-learn (ML)

**Status :** 🔴 Q1 2025

👉 **[Spécifications](../framework/agents.md#pattern-agent)**

---

## 🎲 Simulation Agent

**Fonction :** Simulateur de scénarios

**Capacités :**
- Monte Carlo simulations
- Bayesian networks
- Comparaison multi-scénarios
- Apprentissage continu

**Stack :**
- Python 3.11+
- NumPy/SciPy
- XGBoost

**Status :** 🔴 Q1 2025

👉 **[Spécifications](../framework/agents.md#simulation-agent)**

---

## 🔗 Coordination Agent

**Fonction :** Optimiseur de flux

**Capacités :**
- Détection blocages
- Optimisation dépendances
- Suggestions recomposition
- Orchestration auto

**Stack :**
- Python 3.11+
- Neo4j (graphe)
- OR-Tools (optimisation)

**Status :** 🔴 Q2 2025

👉 **[Spécifications](../framework/agents.md#coordination-agent)**

---

## 🏗️ Architecture Globale

```
┌─────────────────────────────────┐
│  Dashboard (React)              │
│  Port 3000                      │
└─────────────────────────────────┘
           ↕️ HTTP/WebSocket
┌─────────────────────────────────┐
│  API Gateway (FastAPI)          │
│  Port 8000                      │
└─────────────────────────────────┘
           ↕️
    ┌──────┴──────┬──────┬──────┐
    ↓             ↓      ↓      ↓
┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐
│Memory  │  │Pattern │  │Simul.  │  │Coord.  │
│:8001   │  │:8002   │  │:8003   │  │:8004   │
└────────┘  └────────┘  └────────┘  └────────┘
    ↓           ↓          ↓          ↓
┌──────────────────────────────────────┐
│  Data Layer                          │
│  - Neo4j, Pinecone, InfluxDB,       │
│  - PostgreSQL, Redis                │
└──────────────────────────────────────┘
```

---

## 🔧 Configuration

### Variables d'Environnement

```bash
# tools/.env

# LLM APIs
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...

# Databases
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=password

PINECONE_API_KEY=...
POSTGRES_HOST=localhost
REDIS_URL=redis://localhost:6379

# Application
LOG_LEVEL=INFO
ENV=development
```

---

## 🧪 Tests

```bash
# Tous les tests
pytest tools/*/tests/ -v

# Tests par agent
cd tools/memory-agent
pytest tests/ -v --cov=src
```

---

## 📊 Monitoring

**Métriques Prometheus :** `/metrics` sur chaque agent

```
# Exemples
http_requests_total
memory_decisions_captured_total
memory_search_latency_seconds
```

**Dashboard Grafana :** `tools/monitoring/grafana-dashboard.json`

---

## 🐳 Docker

```bash
# Toute l'infrastructure
cd tools
docker-compose up -d

# Services : Neo4j, PostgreSQL, Redis, InfluxDB, 
#            Prometheus, Grafana
```

---

## 🚀 Déploiement

**Docker Compose (Dev/Test) :**
```bash
docker-compose -f docker-compose.prod.yml up -d
```

**Kubernetes (Production) :**
```bash
kubectl apply -f tools/k8s/
```

**Cloud :**
- Fly.io : `.fly.toml`
- Render : `render.yaml`
- Railway : Auto-détection

---

## 🤝 Contribution

1. Fork le repository
2. Créer branche feature
3. Développer avec tests
4. Pull Request

**Standards :**
- PEP 8 (black)
- Type hints
- Coverage > 80%

👉 **[Guide de contribution](../CONTRIBUTING.md)**

---

## 📚 Ressources

**Documentation :**
- [Architecture des Agents](../framework/agents.md)
- [Guide d'Implémentation](../docs/getting-started.md)

**Communauté :**
- 💬 [Discussions](https://github.com/synapse-origin/synapse/discussions)
- 🐛 [Issues](https://github.com/synapse-origin/synapse/issues)

---

## 🎯 Roadmap Technique

**Q4 2024 :**
- [ ] Memory Agent V0.1 (alpha)
- [ ] Dashboard V0.1

**Q1 2025 :**
- [ ] Memory Agent V1.0 (production)
- [ ] Pattern Agent V0.1

**Q2 2025 :**
- [ ] Simulation + Coordination V0.1
- [ ] API publique stable

---

*Outils SYNAPSE - Construisons ensemble*  
*Dernière mise à jour : Novembre 2024*
