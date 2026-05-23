---
tags: [skill]
updated: 2026-05-23
---

# Skill : wiki-query

## Objectif
Répondre à une question en s'appuyant sur le wiki, avec citations des pages utilisées.

## Déclenchement
- Question explicite de l'utilisateur
- Demande de synthèse, comparaison ou explication

## Procédure

```
1. LIRE index.md pour identifier les pages pertinentes
2. LIRE les pages pertinentes (max 7 pour rester dans le budget de contexte)
3. SYNTHÉTISER une réponse :
   - Citer chaque page utilisée : "Selon [[page]], ..."
   - Signaler les lacunes : "Le wiki ne couvre pas encore X"
   - Signaler les contradictions trouvées en cours de lecture
4. PROPOSER l'intégration si la réponse a de la valeur :
   "Cette réponse mérite-t-elle d'être sauvegardée dans le wiki ?"
   → Si oui : créer la page dans le dossier approprié
5. APPENDER dans log.md :
   ## [YYYY-MM-DD] query | [question résumée]
   - Pages lues : [[p1]], [[p2]]
   - Réponse intégrée : oui → [[page]] / non
```

## Format de réponse recommandé

```markdown
## Réponse
[Réponse directe]

## Sources wiki utilisées
- [[page1]] — ...
- [[page2]] — ...

## Lacunes
- Le wiki ne couvre pas encore : X

## Pages liées
[[page3]], [[page4]]
```

## Liens
- [[workflows/answer-question]]
- [[skills/wiki-router]]
