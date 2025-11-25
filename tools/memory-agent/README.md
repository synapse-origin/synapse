# 🧠 Memory Agent

**Status** : 🟡 Alpha  
**Version** : 0.1.0  
**Langage** : Python 3.11+

---

## 🎯 Fonction

Capture, structure et restitue la mémoire organisationnelle de SYNAPSE.

**Ce qu'il fait** :
- Capture décisions, communications, code
- Construit graphe de connaissances
- Détecte contradictions
- Fournit contexte pertinent

👉 **[Spécifications complètes](../../framework/agents.md#memory-agent)**

---

## 🚀 Installation

### Prérequis
```bash
Python 3.11+
Docker & Docker Compose
```

### Setup
```bash
# Clone
git clone https://github.com/synapse-origin/synapse.git
cd synapse/tools/memory-agent

# Environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou venv\Scripts\activate  # Windows

# Dépendances
pip install -r requirements.txt

# Configuration
cp .env.example .env
# Éditer .env avec vos clés API
```

### Configuration .env
```bash
# LLM
ANTHROPIC_API_KEY=your_key_here
# ou
OPENAI_API_KEY=your_key_here

# Databases
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=your_password

PINECONE_API_KEY=your_key_here
PINECONE_ENVIRONMENT=us-east-1

# Redis
REDIS_URL=redis://localhost:6379
```

---

## 🏃 Démarrage

### Lancer Infrastructure
```bash
# Bases de données
docker-compose up -d

# Vérifier
docker ps
# Doit montrer : neo4j, redis
```

### Lancer Memory Agent
```bash
# Development
python main.py

# Production
gunicorn main:app --workers 4 --bind 0.0.0.0:8001
```

**API disponible sur** : `http://localhost:8001`

---

## 📡 API Endpoints

### POST /decisions
Enregistrer une décision
```bash
curl -X POST http://localhost:8001/decisions \
  -H "Content-Type: application/json" \
  -d '{
    "id": "dec-001",
    "content": "Migrer vers PostgreSQL",
    "maker": "alice",
    "date": "2025-11-24",
    "context": "Besoin scalabilité"
  }'
```

### GET /search
Rechercher dans la mémoire
```bash
curl "http://localhost:8001/search?q=migration+database"
```

### GET /context
Obtenir contexte pour situation
```bash
curl "http://localhost:8001/context?situation=choix+database"
```

👉 **[Documentation API complète](API.md)** *(à venir)*

---

## 🧪 Tests
```bash
# Unit tests
pytest tests/ -v

# Coverage
pytest --cov=memory_agent tests/

# Integration tests
pytest tests/integration/ -v
```

---

## 📊 Stack Technique

**LLM** : Anthropic Claude / OpenAI GPT-4  
**Vector DB** : Pinecone (ou Weaviate, Qdrant)  
**Graph DB** : Neo4j  
**Cache** : Redis  
**API** : FastAPI  

---

## 🎯 Roadmap

**V0.1 (Actuel - Alpha)**
- [x] Capture décisions manuelles
- [x] Graphe de connaissances basique
- [x] Recherche sémantique
- [ ] Détection contradictions

**V0.2 (Q1 2026)**
- [ ] Webhooks Git/Slack automatiques
- [ ] Détection contradictions avancée
- [ ] Dashboard visualisation graphe

**V1.0 (Q2 2026)**
- [ ] ML patterns dans historique
- [ ] Suggestions proactives
- [ ] API complète documentée

---

## 🤝 Contribuer

Voir [CONTRIBUTING.md](../../CONTRIBUTING.md)

**Besoin actuel** :
- Améliorer extraction entités (LLM prompts)
- Tests coverage > 80%
- Documentation API

---

## 📞 Support

💬 [GitHub Discussions](https://github.com/synapse-origin/synapse/discussions)  
🐛 [Issues](https://github.com/synapse-origin/synapse/issues)  
📧 synapse-origin@proton.me

---

*Memory Agent - SYNAPSE V0.1*  
*Dernière mise à jour : Novembre 2025*
