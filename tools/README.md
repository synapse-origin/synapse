# 🛠️ Outils SYNAPSE

Code source des agents IA.

---

## 🎯 Agents

| Agent | Status | Langage |
|-------|--------|---------|
| [Memory](memory-agent/) | 🟡 Alpha | Python |
| [Pattern](pattern-agent/) | 🔴 Q1 2025 | Python |
| [Simulation](simulation-agent/) | 🔴 Q1 2025 | Python |
| [Coordination](coordination-agent/) | 🔴 Q2 2025 | Python |

👉 **[Spécifications détaillées](../framework/agents.md)**

---

## 🚀 Démarrage

### Installation

```bash
git clone https://github.com/synapse-origin/synapse.git
cd synapse/tools

# Env + dépendances
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Configuration
cp .env.example .env
# Éditer .env (clés API)
```

### Lancer

```bash
# Infrastructure
docker-compose up -d

# Memory Agent
cd memory-agent
python main.py
```

---

## 🏗️ Architecture

```
Dashboard (React :3000)
    ↕️
API Gateway (FastAPI :8000)
    ↕️
Memory :8001 | Pattern :8002 | Simul :8003 | Coord :8004
    ↕️
Neo4j | Pinecone | InfluxDB | PostgreSQL | Redis
```

---

## 🔧 Stack

**APIs :**
- Anthropic Claude / OpenAI

**Databases :**
- Neo4j (graphe)
- Pinecone (embeddings)
- InfluxDB (time series)
- PostgreSQL (données)
- Redis (cache)

**Monitoring :**
- Prometheus
- Grafana

**Coût :** 200-500€/mois (pilote)

---

## 🧪 Tests

```bash
pytest tools/*/tests/ -v
```

---

## 🐳 Docker

```bash
docker-compose up -d
```

**Services :** Neo4j, PostgreSQL, Redis, InfluxDB, Prometheus, Grafana

---

## 🚀 Déploiement

**Cloud :**
- Fly.io (`.fly.toml`)
- Render (`render.yaml`)
- Kubernetes (`k8s/`)

---

## 🤝 Contribution

1. Fork
2. Branch feature
3. Tests
4. Pull Request

**Standards :** PEP 8, Type hints, Coverage >80%

👉 [Guide contribution](../CONTRIBUTING.md)

---

## 📚 Ressources

[Agents (specs)](../framework/agents.md)  
[Guide implémentation](../docs/getting-started.md)  
[Discussions](https://github.com/synapse-origin/synapse/discussions)

---

## 🎯 Roadmap

**Q4 2024 :** Memory V0.1  
**Q1 2025 :** Memory V1.0, Pattern V0.1  
**Q2 2025 :** Simulation, Coordination V0.1

---

*Outils SYNAPSE*  
*Dernière mise à jour : Novembre 2024*
