---
tags: [source]
updated: 2026-05-23
---

# Sources — Registre

Registre de toutes les sources brutes ingérées. Mise à jour après chaque ingest.

---

## Format d'entrée

`| Date | Slug | Titre | Type | Pages touchées |`

---

## Sources ingérées

| Date | Slug | Titre | Type | Pages touchées |
|------|------|-------|------|----------------|
| 2026-05-23 | llm-wiki-pattern | LLM Wiki — A pattern for building personal knowledge bases | article | [[agents/agent-router]], [[skills/wiki-ingest]], [[skills/wiki-query]], [[skills/wiki-lint]], [[decisions/decisions-log]] |

---

## Types de sources

| Type | Description |
|------|-------------|
| `article` | Article web ou blog |
| `doc` | Documentation technique |
| `transcript` | Transcript audio/vidéo |
| `note` | Note personnelle |
| `pdf` | Document PDF |
| `code` | Fichier ou repo de code |
| `conversation` | Extrait de conversation avec un LLM |

## Liens
- [[workflows/ingest-source]]
- [[index]]
