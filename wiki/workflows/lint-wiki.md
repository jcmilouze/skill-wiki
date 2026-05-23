---
tags: [workflow]
updated: 2026-05-23
---

# Workflow : Lint Wiki

## Quand l'utiliser
- Après 5+ ingestions consécutives
- Contradictions signalées et non résolues dans log.md
- Périodiquement (tous les 10 ingests ou 1 fois par semaine)

## Étapes

### 1 — Inventaire
```bash
find /Users/jc/Documents/Obsidian/Skill/wiki -name "*.md" | sort
```
- Comparer avec index.md
- Lister les fichiers présents mais absents de l'index

### 2 — Détection des contradictions
```bash
grep -r "⚠️ CONTRADICTION" /Users/jc/Documents/Obsidian/Skill/wiki/ --include="*.md" -l
```
Pour chaque occurrence : page, nature, date, statut (résolu / non résolu)

### 3 — Détection des orphelins
```
- Pages dans index.md sans [[lien entrant]] dans d'autres pages
- Vérifier manuellement ou via grep inversé
```

### 4 — Détection des doublons
```
- Chercher les titres similaires dans index.md
- Chercher les sections répétées dans plusieurs pages
- Proposer des fusions si pertinent
```

### 5 — Détection des lacunes
```
- Termes mentionnés fréquemment sans page dédiée
- Pages < 5 lignes utiles à développer
- Catégories vides ou sous-représentées dans index.md
```

### 6 — Rapport

```markdown
## Rapport de lint — [YYYY-MM-DD]

### Contradictions non résolues (N)
| Page | Conflit | Date |
|------|---------|------|

### Pages orphelines (N)
- [[page]] — aucun lien entrant

### Doublons potentiels (N)
- [[pageA]] et [[pageB]] — chevauchement sur : X

### Lacunes (N)
- Terme "X" mentionné N fois, pas de page dédiée

### Actions prioritaires
1. [action — niveau d'urgence]
2. ...
```

### 7 — Log
```
## [YYYY-MM-DD] lint | Audit complet
- Contradictions : N / Orphelins : N / Doublons : N / Lacunes : N
- Actions prioritaires : ...
```

## Règles
- Proposer, ne pas corriger automatiquement
- Prioriser : contradictions > orphelins > lacunes > liens manquants

## Liens
- [[skills/wiki-lint]]
