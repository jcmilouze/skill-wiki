---
tags: [skill]
updated: 2026-05-23
---

# Skill : wiki-lint

## Objectif
Auditer la santé du wiki : cohérence, couverture, liens, contradictions.

## Déclenchement
- Après 5+ ingestions consécutives
- Demande explicite de l'utilisateur
- Contradictions non résolues dans log.md

## Procédure

```
1. LIRE index.md (vue complète du wiki)
2. LIRE log.md (identifier les contradictions signalées non résolues)
3. GREP ⚠️ CONTRADICTION dans tous les fichiers wiki/
4. VÉRIFIER chaque axe :

   A. CONTRADICTIONS
      - Page concernée, nature du conflit, date, statut (résolu / non résolu)

   B. ORPHELINS
      - Pages dans index.md sans liens entrants depuis d'autres pages
      - Fichiers sur disque absents de index.md

   C. DOUBLONS
      - Concepts couverts sur plusieurs pages — proposer fusion

   D. LACUNES
      - Termes mentionnés sans page dédiée
      - Pages < 5 lignes utiles

   E. LIENS MANQUANTS
      - Références textuelles non converties en [[liens]]

5. PRODUIRE un rapport de lint (ne pas corriger automatiquement)
6. APPENDER dans log.md :
   ## [YYYY-MM-DD] lint | Audit complet
   - Contradictions : N
   - Orphelins : N / Doublons : N / Lacunes : N
   - Actions prioritaires : [[p1]], [[p2]]
```

## Règles
- Proposer les corrections, ne pas les appliquer sans validation utilisateur
- Prioriser : contradictions > orphelins > lacunes > liens manquants

## Format du rapport

```markdown
## Rapport de lint — [YYYY-MM-DD]

### Contradictions non résolues (N)
| Page | Conflit | Date |

### Pages orphelines (N)
### Doublons potentiels (N)
### Lacunes (N)
### Actions prioritaires
1. [action — priorité]
```

## Liens
- [[workflows/lint-wiki]]
- [[skills/wiki-router]]
