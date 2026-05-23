---
tags: [workflow]
updated: 2026-05-23
---

# Workflow : Answer Question

## Quand l'utiliser
L'utilisateur pose une question sur le domaine couvert par le wiki.

## Étapes

### 1 — Navigation dans l'index
```
- Lire index.md
- Identifier les 3-7 pages les plus pertinentes
- Si aucune page pertinente → signaler la lacune, ne pas inventer
```

### 2 — Lecture des pages pertinentes
```
- Lire chaque page identifiée
- Prendre note des marqueurs ⚠️ CONTRADICTION
- Budget : max 7 pages par query
```

### 3 — Synthèse

Utiliser ce format :

```markdown
## Réponse
[Réponse directe, 1-3 paragraphes]

## Sources wiki utilisées
- [[page1]] — raison de la sélection
- [[page2]] — raison de la sélection

## Limites / Lacunes
- Le wiki ne couvre pas encore : X
- Contradiction non résolue : voir [[page]]

## Pages liées
[[page3]], [[page4]]
```

### 4 — Proposition d'intégration
```
Si la synthèse produit une valeur nouvelle (analyse, comparaison, conclusion) :
→ Proposer : "Cette réponse mérite-t-elle une page wiki ?"
→ Si oui : créer la page dans le dossier approprié, mettre à jour index.md
```

### 5 — Log
```
## [YYYY-MM-DD] query | [question résumée en 5 mots]
- Pages lues : [[p1]], [[p2]]
- Lacunes identifiées : X
- Réponse intégrée : oui → [[page]] / non
```

## Liens
- [[skills/wiki-query]]
