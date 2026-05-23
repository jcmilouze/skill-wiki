---
tags: [skill]
updated: 2026-05-23
---

# Skill : wiki-router

## Objectif
Identifier l'intention de l'utilisateur et charger la skill adaptée sans mélanger les opérations.

## Déclenchement
Invoquer en début de session ou quand l'intention n'est pas claire.

## Procédure

```
1. LIRE wiki/index.md (toujours en premier)
2. LIRE wiki/log.md (5 dernières entrées)
3. ANALYSER l'intention :
   - "source", "fichier", "ajoute", "traite", "lis", "intègre"  → INGEST
   - "question", "explique", "synthèse", "compare", "cherche"   → QUERY
   - "audit", "vérifie", "problème", "contradiction", "orphelin" → LINT
   - Ambigu → DEMANDER : "Est-ce une ingestion, une requête ou un audit ?"
4. CHARGER la skill correspondante :
   - INGEST → [[skills/wiki-ingest]]
   - QUERY  → [[skills/wiki-query]]
   - LINT   → [[skills/wiki-lint]]
5. PASSER le contexte : intention qualifiée + pages pertinentes identifiées
```

## Règles
- Une seule opération à la fois
- Ne jamais exécuter directement : toujours déléguer à la skill
- Si l'utilisateur donne plusieurs intentions : prioriser INGEST > LINT > QUERY

## Liens
- [[agents/agent-router]]
- [[skills/wiki-ingest]], [[skills/wiki-query]], [[skills/wiki-lint]]
