---
tags: [decision]
updated: 2026-05-23
---

# Décisions d'architecture

Journal des arbitrages structurants. Append-only comme log.md, mais centré sur les choix qui façonnent le système plutôt que sur les opérations quotidiennes.

## Format

```
## [YYYY-MM-DD] [Titre de la décision]
**Contexte :** pourquoi cette décision s'imposait
**Décision :** ce qui a été choisi
**Alternatives rejetées :** ce qui a été écarté et pourquoi
**Impact :** pages ou comportements affectés
```

---

## [2026-05-23] Structure initiale basée sur le pattern LLM Wiki

**Contexte :** Besoin d'organiser les skills Claude Code / Antigravity de façon persistante et maintenable. Le RAG classique repart de zéro à chaque session — rien ne s'accumule.

**Décision :** Adopter le pattern LLM Wiki — wiki markdown persistent maintenu par Claude Code, avec trois couches : sources brutes / wiki généré / schéma de gouvernance (CLAUDE.md). Stocker dans l'Obsidian vault existant `/Users/jc/Documents/Obsidian/Skill/`.

**Alternatives rejetées :**
- RAG + embeddings : infrastructure lourde, inutile à cette échelle
- Mémoire Claude Code seule : non structurée, non navigable dans Obsidian
- Notion / Confluence : hors Obsidian, non contrôlable par le LLM

**Impact :** Toute la structure `wiki/`, conventions de nommage, workflows ingest/query/lint, CLAUDE.md comme contrat de gouvernance.

---

## [2026-05-23] Local-first — Ollama pour la génération de code

**Contexte :** Coût et confidentialité des données pour les tâches de génération répétitives.

**Décision :** Déléguer la génération de code à `qwen3.5:35b` via Ollama local. Claude Code garde : orchestration, architecture, sécurité, review, maintenance wiki.

**Alternatives rejetées :**
- Claude seul pour tout : coût élevé pour les tâches mécaniques
- GPT-4o : données sortantes, coût cloud

**Impact :** [[agents/agent-antigravity]] — configuration et commande de délégation standard.
