# 📝 Templates SYNAPSE

Templates prêts à l'emploi pour documenter et structurer votre implémentation SYNAPSE.

---

## 🎯 Templates Disponibles

### Essentiels (Utilisez-les dès le début)

1. **[Intent Statement](intent-statement.md)** 🎯
   - Déclaration d'intention stratégique
   - Quand l'utiliser : Jour 1 de SYNAPSE
   - Qui le remplit : Intent Architect + équipe
   - Fréquence : Créé au début, révisé trimestriellement

2. **[Decision Record](decision-record.md)** 📋
   - Enregistrement formalisé d'une décision
   - Quand l'utiliser : Pour toute décision importante
   - Qui le remplit : Le décideur (Maker) + Memory Agent
   - Fréquence : À chaque décision majeure (stratégique, tactique)

### Complémentaires (À utiliser selon besoins)

3. **[Pattern Report](pattern-report.md)** 🔍 *(À venir)*
   - Rapport de pattern détecté par Pattern Agent
   - Quand l'utiliser : Quand un pattern significatif est détecté
   - Qui le remplit : System Orchestrator + Pattern Agent
   - Fréquence : Hebdomadaire ou à la demande

4. **[Ethics Audit](ethics-audit.md)** ⚖️ *(À venir)*
   - Audit éthique périodique du système
   - Quand l'utiliser : Trimestriel ou après incident
   - Qui le remplit : Ethical Guardian + Comité éthique
   - Fréquence : Trimestrielle

---

## 📖 Comment Utiliser Ces Templates

### 1. Intent Statement

**Étape par étape** :

1. **Préparation** (1-2h)
   - Intent Architect prépare un draft seul
   - Réfléchit : Pourquoi existe-t-on ? Où va-t-on ?

2. **Atelier collectif** (2-3h)
   - Tous les rôles SYNAPSE + stakeholders clés
   - Discussion : objectifs, contraintes, hors scope
   - Consensus sur les priorités

3. **Formalisation** (1h)
   - Intent Architect met au propre
   - Utilise le template
   - Partage pour validation finale

4. **Signature & Publication**
   - Les 4 rôles signent
   - Document publié et accessible à tous
   - Communiqué à l'organisation

**Conseils** :
- Soyez concis : 2 pages max
- Évitez le jargon : accessible à tous
- Soyez mesurable : critères de succès quantifiés
- Soyez honnête : admettez les contraintes

**Exemple de contenu** :
```markdown
Objectif Principal :
"Créer la meilleure plateforme de gestion de projets 
pour équipes distribuées."

Objectif Stratégique #1 :
- Description : Atteindre 100 clients payants
- Mesure : ARR de 500k€
- Horizon : 31/12/2025

Contrainte Éthique :
- Aucune surveillance invasive des utilisateurs
- Transparence totale sur l'utilisation des données
```

---

### 2. Decision Record

**Étape par étape** :

1. **Contexte** (10 min)
   - Pourquoi cette décision maintenant ?
   - Quel problème / quelle opportunité ?

2. **Options** (30 min)
   - Brainstormer 3-5 options
   - Pour chaque option : avantages, risques, coûts

3. **Simulation** (optionnel, 1-2h)
   - Demander au Simulation Agent
   - Analyser les scénarios proposés

4. **Décision** (30 min)
   - Choisir l'option
   - Justifier le choix
   - Définir plan d'action

5. **Documentation** (15 min)
   - Remplir le template
   - Enregistrer dans Memory Agent
   - Partager aux concernés

**Qui participe ?** :
- Décideur principal (Maker)
- Rôles impactés
- Experts si nécessaire

**Conseils** :
- Ne pas passer 3h sur une décision mineure
- Pour décisions mineures : version simplifiée
- Toujours documenter le "pourquoi"
- Définir comment mesurer le succès

**Exemple de décision** :
```markdown
# Decision Record #042

Décision : Migrer vers PostgreSQL

Contexte :
Notre base MongoDB atteint ses limites de scalabilité.
Transactions ACID nécessaires pour paiements.

Options considérées :
A. PostgreSQL (relationnel, ACID)
B. Optimiser MongoDB (actuel)
C. Hybrid (MongoDB + PostgreSQL)

Simulation Agent recommande : Option A (confiance 85%)

Choix : Option A - PostgreSQL
Raison : ACID critique pour conformité financière

Actions :
- [ ] POC migration (2 semaines) - Alice
- [ ] Formation équipe PostgreSQL - Bob
- [ ] Migration progressive (3 mois) - Équipe
```

---

## 🔄 Workflow de Documentation

### Scénario 1 : Nouvelle Décision Majeure

```
1. Identifier besoin de décision
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
7. Suivre l'implémentation
   ↓
8. Révision à M+X (résultats vs prédictions)
```

### Scénario 2 : Pattern Détecté

```
1. Pattern Agent alerte
   ↓
2. System Orchestrator crée Pattern Report
   ↓
3. Pattern Review (réunion)
   ↓
4. Si action → Decision Record
   ↓
5. Suivi de l'impact
```

### Scénario 3 : Audit Éthique

```
1. Date d'audit (trimestriel)
   ↓
2. Ethical Guardian prépare Ethics Audit
   ↓
3. Analyse des décisions IA
   ↓
4. Comité d'éthique se réunit
   ↓
5. Rapport publié
   ↓
6. Actions correctives si nécessaire
```

---

## 💡 Bonnes Pratiques

### Documentation

**DO** ✅ :
- Documenter les décisions importantes (stratégiques, avec impact)
- Être concis mais complet
- Utiliser un langage clair
- Mettre à jour quand le contexte change

**DON'T** ❌ :
- Documenter chaque micro-décision
- Écrire 10 pages pour une décision simple
- Utiliser du jargon incompréhensible
- Laisser les documents obsolètes sans mise à jour

### Fréquence

| Template | Fréquence Recommandée |
|----------|----------------------|
| Intent Statement | Créé au début, révisé tous les 3-6 mois |
| Decision Record | À chaque décision majeure (2-5/semaine) |
| Pattern Report | Hebdomadaire ou quand pattern significatif |
| Ethics Audit | Trimestriel ou après incident |

### Stockage

**Où stocker les documents ?**

**Option 1 : Memory Agent** (Recommandé)
- Avantage : Indexation automatique, recherche sémantique
- Inconvénient : Nécessite Memory Agent opérationnel

**Option 2 : Git Repository**
- Avantage : Versionné, accessible sans infrastructure
- Inconvénient : Pas de recherche sémantique

**Option 3 : Hybride**
- Source de vérité : Git (markdown files)
- Indexé dans : Memory Agent (pour recherche)
- Best of both worlds

**Structure Git recommandée** :
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

## 🎨 Personnalisation des Templates

### Vous pouvez adapter les templates à votre contexte

**Exemples d'adaptations** :

**Startup early-stage** :
- Intent Statement simplifié (1 page)
- Decision Record allégé (pas de simulation systématique)
- Moins de formalisme, plus de vitesse

**Grande entreprise réglementée** :
- Intent Statement détaillé (conformité, risques)
- Decision Record avec sections validation légale/sécurité
- Audit éthique plus fréquent (mensuel)

**Équipe technique pure** :
- Ajouter sections techniques aux Decision Records
- Templates en markdown (intégration Git)
- Liens vers code, PRs, issues

**Conseils pour personnaliser** :
1. Gardez la structure de base
2. Ajoutez des sections si nécessaire (ne retirez pas)
3. Documentez vos changements
4. Partagez vos versions avec la communauté

---

## 📚 Ressources Complémentaires

### Exemples Réels

Voir [case-studies/](../case-studies/) pour des exemples d'Intent Statements et Decision Records d'organisations pilotes.

### Formation

Pour apprendre à utiliser ces templates efficacement :
- [Guide d'implémentation](../docs/getting-started.md)
- [Quick Start](../framework/quick-start.md)

### Support

Questions sur l'utilisation des templates ?
- 💬 [GitHub Discussions](https://github.com/synapse-origin/synapse/discussions)
- 📧 synapse-origin@proton.me

---

## 🚀 Templates à Venir

**Roadmap Q1 2025** :
- [ ] Pattern Report Template
- [ ] Ethics Audit Template
- [ ] Onboarding Checklist Template
- [ ] Team Configuration Template
- [ ] Simulation Request Template

**Contribuez !**

Vous avez créé un template utile ? Partagez-le avec la communauté :
1. Fork le repository
2. Ajoutez votre template dans `templates/`
3. Ouvrez une Pull Request
4. Expliquez le cas d'usage

---

## 📄 Licence

Ces templates sont sous licence **CC BY-SA 4.0**.

Vous pouvez :
- Les utiliser librement
- Les adapter à vos besoins
- Les partager

À condition de :
- Créditer SYNAPSE
- Partager vos versions adaptées sous même licence

---

*Templates maintenus par la communauté SYNAPSE.*

**Version** : 1.0  
**Dernière mise à jour** : Novembre 2024
