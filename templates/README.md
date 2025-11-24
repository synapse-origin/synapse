# 📝 Templates SYNAPSE

Templates prêts à l'emploi pour documenter et structurer votre implémentation SYNAPSE.

---

## 🎯 Templates Disponibles

### Essentiels

1. **[Intent Statement](intent-statement.md)** 🎯
   - **Quoi :** Déclaration d'intention stratégique
   - **Quand :** Jour 1 de SYNAPSE
   - **Qui :** Intent Architect + équipe
   - **Fréquence :** Créé au début, révisé trimestriellement

2. **[Decision Record](decision-record.md)** 📋
   - **Quoi :** Enregistrement formalisé d'une décision
   - **Quand :** Pour toute décision importante
   - **Qui :** Le décideur (Maker) + Memory Agent
   - **Fréquence :** À chaque décision majeure

### Complémentaires

3. **[Pattern Report](pattern-report.md)** 🔍 *(À venir)*
   - **Quoi :** Rapport de pattern détecté
   - **Quand :** Pattern significatif détecté
   - **Qui :** System Orchestrator + Pattern Agent
   - **Fréquence :** Hebdomadaire ou à la demande

4. **[Ethics Audit](ethics-audit.md)** ⚖️ *(À venir)*
   - **Quoi :** Audit éthique périodique
   - **Quand :** Trimestriel ou après incident
   - **Qui :** Ethical Guardian + Comité éthique
   - **Fréquence :** Trimestrielle

---

## 📖 Comment Utiliser

### Intent Statement

**Étapes :**
1. **Préparation** (1-2h) : Intent Architect fait draft
2. **Atelier** (2-3h) : Discussion collective
3. **Formalisation** (1h) : Mise au propre
4. **Signature** : Les 4 rôles valident

**Conseils :**
- Concis : 2 pages max
- Mesurable : Critères quantifiés
- Accessible : Éviter jargon
- Honnête : Admettre contraintes

👉 [Template Intent Statement](intent-statement.md)

---

### Decision Record

**Étapes :**
1. **Contexte** (10 min) : Pourquoi décider ?
2. **Options** (30 min) : 3-5 options
3. **Simulation** (optionnel, 1-2h) : Demander Simulation Agent
4. **Décision** (30 min) : Choisir + justifier
5. **Documentation** (15 min) : Remplir template

**Conseils :**
- Pas 3h pour décision mineure
- Toujours documenter le "pourquoi"
- Définir métriques de succès

👉 [Template Decision Record](decision-record.md)

---

## 🔄 Workflow de Documentation

### Nouvelle Décision Majeure

```
1. Identifier besoin
   ↓
2. Remplir Decision Record (options)
   ↓
3. Demander simulation si complexe
   ↓
4. Decision Moment (réunion)
   ↓
5. Compléter Decision Record (choix)
   ↓
6. Enregistrer dans Memory Agent
   ↓
7. Suivre implémentation
```

### Pattern Détecté

```
1. Pattern Agent alerte
   ↓
2. System Orchestrator crée Pattern Report
   ↓
3. Pattern Review (réunion)
   ↓
4. Si action → Decision Record
   ↓
5. Suivi impact
```

---

## 💡 Bonnes Pratiques

### DO ✅

- Documenter décisions importantes
- Être concis mais complet
- Langage clair
- Mettre à jour si contexte change

### DON'T ❌

- Documenter chaque micro-décision
- 10 pages pour décision simple
- Jargon incompréhensible
- Laisser documents obsolètes

---

## 📊 Fréquence Recommandée

| Template | Fréquence |
|----------|-----------|
| Intent Statement | Créé au début, révisé Q3-6 mois |
| Decision Record | 2-5 par semaine |
| Pattern Report | Hebdomadaire ou à la demande |
| Ethics Audit | Trimestriel |

---

## 💾 Stockage

### Option 1 : Memory Agent (Recommandé)
- **Avantage :** Indexation auto, recherche sémantique
- **Inconvénient :** Nécessite agent opérationnel

### Option 2 : Git Repository
- **Avantage :** Versionné, accessible
- **Inconvénient :** Pas de recherche sémantique

### Option 3 : Hybride (Idéal)
- **Source :** Git (markdown files)
- **Index :** Memory Agent (recherche)

**Structure Git :**
```
docs/
├── intent/
│   └── intent-statement-v1.md
├── decisions/
│   ├── 2024-11/
│   │   ├── dec-001-migration-db.md
│   │   └── dec-002-nouveau-produit.md
│   └── 2024-12/
├── patterns/
│   └── 2024-11/
└── audits/
    └── 2024-Q4-ethics-audit.md
```

---

## 🎨 Personnalisation

Vous pouvez adapter les templates à votre contexte :

**Startup :**
- Intent Statement simplifié (1 page)
- Decision Record allégé
- Moins de formalisme

**Grande entreprise :**
- Intent Statement détaillé (conformité)
- Decision Record avec validation légale
- Audit éthique mensuel

**Conseils :**
1. Gardez structure de base
2. Ajoutez sections si nécessaire
3. Documentez vos changements
4. Partagez avec communauté

---

## 📚 Ressources

**Exemples :**
- [Études de cas](../case-studies/) - Intent Statements réels

**Guides :**
- [Guide d'implémentation](../docs/getting-started.md)
- [Quick Start](../framework/quick-start.md)

**Support :**
- 💬 [Discussions](https://github.com/synapse-origin/synapse/discussions)
- 📧 synapse-origin@proton.me

---

## 🚀 Templates à Venir

**Q1 2025 :**
- [ ] Pattern Report Template
- [ ] Ethics Audit Template
- [ ] Onboarding Checklist
- [ ] Team Configuration Template

**Contribuez !** Partagez vos templates :
1. Fork le repository
2. Ajoutez template dans `templates/`
3. Ouvrez Pull Request

---

*Templates maintenus par la communauté SYNAPSE*  
*Dernière mise à jour : Novembre 2024*
