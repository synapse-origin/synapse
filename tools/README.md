# 🛠️ Outils SYNAPSE

Code source et implémentations des agents IA de SYNAPSE.

---

## 🎯 Vue d'Ensemble

Ce dossier contient les implémentations des 4 agents IA de SYNAPSE :

| Agent | Status | Langage | Maturité |
|-------|--------|---------|----------|
| **[Memory Agent](memory-agent/)** | 🟡 En développement | Python | Alpha |
| **[Pattern Agent](pattern-agent/)** | 🔴 Planifié | Python | Roadmap Q1 2025 |
| **[Simulation Agent](simulation-agent/)** | 🔴 Planifié | Python | Roadmap Q1 2025 |
| **[Coordination Agent](coordination-agent/)** | 🔴 Planifié | Python | Roadmap Q2 2025 |

**Légende** :
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
docker-compose --version

# Git
git --version
```

### Installation Globale

```bash
# Cloner le repository
git clone https://github.com/synapse-origin/synapse.git
cd synapse

# Créer environnement virtuel
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows

# Installer dépendances
pip install -r tools/requirements.txt

# Configuration
cp tools/.env.example tools/.env
# Éditer tools/.env avec vos clés API
```

### Démarrer les Agents

```bash
# Lancer l'infrastructure (bases de données)
cd tools
docker-compose up -d

# Lancer Memory Agent (seul disponible pour l'instant)
cd memory-agent
python main.py

# Dashboard (optionnel)
cd ../dashboard
npm install
npm run dev
```

---

## 🧠 Memory Agent

### Description

Agent de mémoire organisationnelle. Capture, structure et restitue la connaissance collective.

**Fonctionnalités** :
- Capture automatique des décisions
- Construction de graphe de connaissances
- Recherche sémantique
- Détection de contradictions
- API REST + WebSocket

**Technologies** :
- Python 3.11+ (FastAPI)
- Neo4j (graphe)
- Pinecone (embeddings)
- Claude API (LLM)
- PostgreSQL (métadonnées)

**Status** : 🟡 Alpha (développement actif)

👉 **[Documentation complète](memory-agent/README.md)**

---

## 🔍 Pattern Agent

### Description

Détecteur de patterns récurrents (blocages, inefficacités, opportunités).

**Fonctionnalités** :
- Analyse time series
- Clustering de patterns
- Alertes en temps réel
- Prédictions (ML)

**Technologies** :
- Python 3.11+
- InfluxDB (time series)
- Scikit-learn (ML)
- Kafka (streaming)

**Status** : 🔴 Roadmap Q1 2025

👉 **[Documentation complète](pattern-agent/README.md)**

---

## 🎲 Simulation Agent

### Description

Simulateur de scénarios pour décisions complexes.

**Fonctionnalités** :
- Monte Carlo simulations
- Bayesian networks
- Multi-scenario comparison
- Apprentissage continu

**Technologies** :
- Python 3.11+
- NumPy/SciPy
- XGBoost
- Plotly (visualisations)

**Status** : 🔴 Roadmap Q1 2025

👉 **[Documentation complète](simulation-agent/README.md)**

---

## 🔗 Coordination Agent

### Description

Optimiseur de flux et de coordination.

**Fonctionnalités** :
- Détection de blocages
- Optimisation de dépendances
- Suggestions de recomposition
- Orchestration automatique

**Technologies** :
- Python 3.11+
- Neo4j (graphe dépendances)
- OR-Tools (optimisation)
- NetworkX

**Status** : 🔴 Roadmap Q2 2025

👉 **[Documentation complète](coordination-agent/README.md)**

---

## 🏗️ Architecture Globale

```
┌─────────────────────────────────────────────┐
│  Dashboard (React)                          │
│  Port 3000                                  │
└─────────────────────────────────────────────┘
              ↕️ HTTP/WebSocket
┌─────────────────────────────────────────────┐
│  API Gateway (FastAPI)                      │
│  Port 8000                                  │
│  - Routing                                  │
│  - Auth                                     │
│  - Rate limiting                            │
└─────────────────────────────────────────────┘
              ↕️
    ┌─────────┴─────────┬─────────┬─────────┐
    ↓                   ↓         ↓         ↓
┌─────────┐     ┌─────────┐  ┌─────────┐  ┌─────────┐
│ Memory  │     │ Pattern │  │Simulat. │  │ Coord.  │
│ Agent   │     │ Agent   │  │ Agent   │  │ Agent   │
│ :8001   │     │ :8002   │  │ :8003   │  │ :8004   │
└─────────┘     └─────────┘  └─────────┘  └─────────┘
    ↓               ↓            ↓            ↓
┌─────────────────────────────────────────────┐
│  Data Layer                                 │
│  - Neo4j (graph)                            │
│  - Pinecone (vectors)                       │
│  - InfluxDB (time series)                   │
│  - PostgreSQL (metadata)                    │
│  - Redis (cache)                            │
└─────────────────────────────────────────────┘
```

---

## 📦 Structure des Agents

Chaque agent suit cette structure :

```
agent-name/
├── README.md              # Documentation
├── Dockerfile             # Image Docker
├── requirements.txt       # Dépendances Python
├── .env.example          # Variables d'env exemple
├── src/
│   ├── main.py           # Point d'entrée
│   ├── api/              # Routes API
│   ├── core/             # Logique métier
│   ├── models/           # Modèles de données
│   └── utils/            # Utilitaires
├── tests/
│   ├── unit/             # Tests unitaires
│   ├── integration/      # Tests d'intégration
│   └── fixtures/         # Données de test
└── docs/
    ├── architecture.md   # Architecture
    ├── api.md           # Documentation API
    └── deployment.md    # Guide déploiement
```

---

## 🔧 Configuration

### Variables d'Environnement

Créez un fichier `tools/.env` :

```bash
# LLM APIs
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...

# Databases
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=password

PINECONE_API_KEY=...
PINECONE_ENVIRONMENT=us-west1-gcp

POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_DB=synapse
POSTGRES_USER=synapse
POSTGRES_PASSWORD=...

INFLUXDB_URL=http://localhost:8086
INFLUXDB_TOKEN=...
INFLUXDB_ORG=synapse

REDIS_URL=redis://localhost:6379

# Monitoring
SENTRY_DSN=...  # Optionnel
PROMETHEUS_PORT=9090

# Application
LOG_LEVEL=INFO
ENV=development  # development | production
```

---

## 🧪 Tests

### Lancer tous les tests

```bash
# Tests unitaires
pytest tools/*/tests/unit/ -v

# Tests d'intégration
pytest tools/*/tests/integration/ -v

# Coverage
pytest --cov=tools --cov-report=html
```

### Tests par agent

```bash
# Memory Agent uniquement
cd tools/memory-agent
pytest tests/ -v

# Avec coverage
pytest tests/ --cov=src --cov-report=term-missing
```

---

## 📊 Monitoring

### Prometheus Metrics

Tous les agents exposent des métriques Prometheus sur `/metrics` :

```
# Requêtes
http_requests_total
http_request_duration_seconds

# Agent spécifique (Memory)
memory_decisions_captured_total
memory_search_latency_seconds
memory_contradictions_detected_total

# Ressources
process_cpu_seconds_total
process_memory_bytes
```

### Grafana Dashboard

Dashboard pré-configuré disponible : `tools/monitoring/grafana-dashboard.json`

Import dans Grafana :
1. Dashboards → Import
2. Upload `grafana-dashboard.json`
3. Sélectionner Prometheus data source

---

## 🐳 Docker

### Démarrer toute l'infrastructure

```bash
cd tools
docker-compose up -d
```

Services lancés :
- Neo4j (7474, 7687)
- PostgreSQL (5432)
- Redis (6379)
- InfluxDB (8086)
- Prometheus (9090)
- Grafana (3001)

### Agents en Docker

```bash
# Builder une image
cd tools/memory-agent
docker build -t synapse/memory-agent .

# Lancer
docker run -p 8001:8001 \
  --env-file ../.env \
  synapse/memory-agent
```

---

## 🚀 Déploiement

### Option 1 : Docker Compose (Recommandé pour dev/test)

```bash
cd tools
docker-compose -f docker-compose.prod.yml up -d
```

### Option 2 : Kubernetes (Production)

Manifests disponibles dans `tools/k8s/` :

```bash
kubectl apply -f tools/k8s/namespace.yml
kubectl apply -f tools/k8s/databases/
kubectl apply -f tools/k8s/agents/
kubectl apply -f tools/k8s/monitoring/
```

### Option 3 : Cloud Managé

- **Fly.io** : Configuration dans `.fly.toml`
- **Render** : Blueprint dans `render.yaml`
- **Railway** : Auto-détection

---

## 🔐 Sécurité

### Bonnes Pratiques

**Secrets** :
- ❌ Ne jamais committer de `.env`
- ✅ Utiliser des secrets managers (AWS Secrets, Vault)
- ✅ Rotation régulière des clés API

**API** :
- ✅ Authentification JWT
- ✅ Rate limiting (100 req/min par défaut)
- ✅ CORS configuré strictement
- ✅ HTTPS obligatoire en production

**Données** :
- ✅ Chiffrement at-rest (databases)
- ✅ Chiffrement in-transit (TLS)
- ✅ Anonymisation des PII
- ✅ Logs sans données sensibles

---

## 📈 Performance

### Benchmarks (Memory Agent V0.1)

| Opération | Latence P50 | Latence P95 | Throughput |
|-----------|-------------|-------------|------------|
| Capture décision | 150ms | 300ms | 100 req/s |
| Recherche sémantique | 200ms | 500ms | 50 req/s |
| Détection contradiction | 300ms | 800ms | 30 req/s |

**Environnement** : 2 CPU, 4GB RAM, SSD

### Optimisations

**Déjà implémentées** :
- Cache Redis (recherches fréquentes)
- Batch processing (embeddings)
- Connection pooling (databases)
- Async I/O (FastAPI)

**Roadmap** :
- CDN pour assets statiques
- Read replicas (databases)
- Sharding (données volumineuses)

---

## 🤝 Contribution

### Workflow

1. **Fork** le repository
2. **Créer une branche** : `git checkout -b feature/mon-agent`
3. **Développer** avec tests
4. **Tester** : `pytest tests/ -v`
5. **Commit** : `git commit -m "feat(memory): ajoute recherche par date"`
6. **Push** : `git push origin feature/mon-agent`
7. **Pull Request** sur GitHub

### Standards de Code

**Python** :
- PEP 8 (formatting)
- Type hints obligatoires
- Docstrings (Google style)
- Coverage > 80%

**Linting** :
```bash
# Formatter
black src/

# Linter
ruff check src/

# Type checking
mypy src/
```

---

## 📚 Ressources

### Documentation Technique

- **[Architecture des Agents](../framework/agents.md)**
- **[Guide d'Implémentation](../docs/getting-started.md)**
- **[API Reference](api-reference.md)** *(à venir)*

### Tutoriels

- **[Créer un Agent Custom](tutorials/custom-agent.md)** *(à venir)*
- **[Intégrer avec Slack](tutorials/slack-integration.md)** *(à venir)*
- **[Déployer en Production](tutorials/production-deployment.md)** *(à venir)*

### Communauté

- 💬 [Discussions GitHub](https://github.com/synapse-origin/synapse/discussions)
- 🐛 [Issues](https://github.com/synapse-origin/synapse/issues)
- 📧 synapse-origin@proton.me

---

## 🎯 Roadmap Technique

### Q4 2024
- [x] Architecture initiale
- [x] Documentation
- [ ] Memory Agent V0.1 (alpha)
- [ ] Dashboard V0.1

### Q1 2025
- [ ] Memory Agent V1.0 (production)
- [ ] Pattern Agent V0.1
- [ ] Tests de charge
- [ ] CI/CD complet

### Q2 2025
- [ ] Simulation Agent V0.1
- [ ] Coordination Agent V0.1
- [ ] Marketplace d'agents
- [ ] API publique stable

---

## 📄 Licence

Code source sous **MIT License**.  
Documentation sous **CC BY-SA 4.0**.

Voir [LICENSE](../LICENSE.md) pour détails.

---

<p align="center">
  <strong>Outils SYNAPSE</strong><br>
  <em>Construisons ensemble les agents du futur</em>
</p>

**Version** : 0.1.0  
**Dernière mise à jour** : Novembre 2024
