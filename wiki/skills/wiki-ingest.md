---
tags: [skill]
updated: 2026-05-23
---

# Skill : wiki-ingest

## Objectif
Traiter une nouvelle source (ou une mise à jour) et l'intégrer dans le wiki de façon cohérente.

## Déclenchement
- Nouvelle source à traiter (article, doc, note, conversation)
- Mise à jour d'une information existante
- Correction d'une page

## Procédure

```
1. LIRE la source brute (fichier, URL, texte collé)
2. EXTRAIRE :
   - Concepts clés
   - Entités (agents, skills, outils, projets)
   - Décisions ou arbitrages
   - Contradictions potentielles avec le wiki existant
3. VÉRIFIER dans index.md si des pages concernées existent déjà
4. POUR CHAQUE page concernée :
   a. Existe → lire et mettre à jour, dater la mise à jour
   b. N'existe pas → créer avec frontmatter minimal dans le bon dossier
5. CRÉER une page source dans sources/ si la source mérite archivage
6. SIGNALER les contradictions :
   - Ajouter dans la page : > ⚠️ CONTRADICTION [date] : [explication courte]
   - Ne pas supprimer l'ancienne version — laisser les deux jusqu'à résolution
7. METTRE À JOUR index.md (nouvelles pages + résumés mis à jour)
8. APPENDER dans log.md :
   ## [YYYY-MM-DD] ingest | [titre source]
   - Pages créées : [[...]]
   - Pages mises à jour : [[...]]
   - Contradictions : aucune / voir [[...]]
```

## Règles
- Ne pas dupliquer : une info = une page
- Créer des pages granulaires (un concept / un agent / une skill par page)
- Garder les pages courtes : max ~60 lignes pour skills et agents
- Lier abondamment avec `[[page]]`

## Liens
- [[workflows/ingest-source]]
- [[sources/sources-index]]
- [[skills/wiki-router]]
