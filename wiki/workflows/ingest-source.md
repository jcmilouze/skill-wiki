---
tags: [workflow]
updated: 2026-05-23
---

# Workflow : Ingest Source

## Quand l'utiliser
Nouvelle source à intégrer : fichier local, article, note, transcript, documentation, conversation.

## Étapes

### 1 — Préparation
```
- Lire index.md
- Lire log.md (5 dernières entrées)
- Identifier les pages existantes potentiellement concernées
- Nommer la source : [YYYY-MM-DD]-[slug-court]
```

### 2 — Lecture et extraction
```
- Lire la source complète
- Extraire :
  □ Titre et date
  □ Concepts clés (3-7)
  □ Entités nommées (agents, outils, skills, personnes)
  □ Décisions ou opinions fortes
  □ Données factuelles
  □ Contradictions potentielles avec le wiki
```

### 3 — Page source (si archivage utile)

```markdown
---
tags: [source]
date: YYYY-MM-DD
origin: [url ou chemin]
---
# [Titre]
## Résumé
## Concepts extraits
## Entités mentionnées
## Décisions / opinions
## Contradictions signalées
```

Sauvegarder dans `sources/[YYYY-MM-DD]-[slug].md`

### 4 — Mise à jour des pages wiki

Pour chaque concept/entité identifié :
1. Vérifier dans index.md si la page existe
2. Existe → lire, intégrer, mettre à jour la date `updated:`
3. N'existe pas → créer dans le bon dossier avec frontmatter minimal
4. Lier vers la source : "Voir aussi : [[sources/[slug]]]"

### 5 — Signalement des contradictions

Si contradiction :
1. Ajouter dans la page concernée :
   > ⚠️ CONTRADICTION [YYYY-MM-DD] : [explication courte]
   > Source : [[sources/[slug]]]
2. Garder les deux versions jusqu'à résolution explicite

### 6 — Mise à jour index.md et log.md
```
- Ajouter la page source dans sources/ de index.md
- Mettre à jour les résumés des pages modifiées dans index.md
- Appender dans log.md :
  ## [YYYY-MM-DD] ingest | [Titre source]
  - Pages créées : [[...]]
  - Pages mises à jour : [[...]]
  - Contradictions : aucune / voir [[...]]
```

## Règles

- ⚠️ CONTRADICTION si une info contredit une page existante → signaler, ne pas écraser silencieusement
- Une page = une entité atomique
- Pas de duplication inter-pages

## Liens
- [[skills/wiki-ingest]]
- [[sources/sources-index]]
