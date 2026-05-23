---
updated: 2026-05-23
maintainer: jcmilouze
---

# Index du Wiki Antigravity

Catalogue de toutes les pages. Une information = une page. Pas de duplication.
Lire ce fichier en premier à chaque session.

---

## Skills Antigravity (customs)

Pipeline obligatoire : `/brainstorm-spec → /write-plan → /execute-plan → /review-hardening → /ship-proof`

| Page | Résumé |
|------|--------|
| [skills/antigravity/agent](skills/antigravity/agent.md) | Founding Tech Lead & AI Delivery Governor — orchestre tout |
| [skills/antigravity/brainstorm-spec](skills/antigravity/brainstorm-spec.md) | Clarifier avant d'implémenter |
| [skills/antigravity/write-plan](skills/antigravity/write-plan.md) | Plan d'exécution atomique séquencé |
| [skills/antigravity/execute-plan](skills/antigravity/execute-plan.md) | Exécution stricte étape par étape |
| [skills/antigravity/review-hardening](skills/antigravity/review-hardening.md) | Audit qualité 8 axes avant livraison |
| [skills/antigravity/ship-proof](skills/antigravity/ship-proof.md) | Checklist livraison production-ready |
| [skills/antigravity/debug-root-cause](skills/antigravity/debug-root-cause.md) | Diagnostic méthodique des bugs |
| [skills/antigravity/ollama-dispatch](skills/antigravity/ollama-dispatch.md) | Délégation local-first vers Ollama |

## Skills Claude Code (natifs)

| Page | Résumé |
|------|--------|
| [skills/claude/init](skills/claude/init.md) | Initialiser CLAUDE.md sur un projet |
| [skills/claude/review](skills/claude/review.md) | Review d'une Pull Request |
| [skills/claude/security-review](skills/claude/security-review.md) | Audit sécurité de la branche courante |
| [skills/claude/update-config](skills/claude/update-config.md) | Configurer le harness (settings.json, hooks, permissions) |
| [skills/claude/keybindings-help](skills/claude/keybindings-help.md) | Personnaliser les raccourcis clavier |
| [skills/claude/simplify](skills/claude/simplify.md) | Revue et simplification du code modifié |
| [skills/claude/fewer-permission-prompts](skills/claude/fewer-permission-prompts.md) | Réduire les prompts de permission |
| [skills/claude/loop](skills/claude/loop.md) | Exécution récurrente d'un prompt |
| [skills/claude/schedule](skills/claude/schedule.md) | Agents planifiés (routines cron) |
| [skills/claude/claude-api](skills/claude/claude-api.md) | Build avec l'API Anthropic / Claude SDK |

## Skills Wiki (meta)

| Page | Résumé |
|------|--------|
| [[skills/wiki-router]] | Skill de routage — identifie l'intention et charge la skill adaptée |
| [[skills/wiki-ingest]] | Skill d'ingestion — traite une source et met à jour le wiki |
| [[skills/wiki-query]] | Skill de requête — répond à une question depuis le wiki |
| [[skills/wiki-lint]] | Skill de lint — détecte les problèmes de cohérence du wiki |

## Workflows

| Page | Résumé |
|------|--------|
| [workflows/ingest-source](workflows/ingest-source.md) | Procédure complète pour ingérer une nouvelle source |
| [workflows/answer-question](workflows/answer-question.md) | Procédure pour répondre à une question depuis le wiki |
| [workflows/lint-wiki](workflows/lint-wiki.md) | Procédure de santé du wiki — contradictions, orphelins, lacunes |

## MCP

| Page | Résumé |
|------|--------|
| [[mcp/mcp-overview]] | Vue d'ensemble des connecteurs MCP disponibles |

## Sources

| Page | Résumé |
|------|--------|
| [[sources/sources-index]] | Registre de toutes les sources brutes ingérées |

## Décisions

| Page | Résumé |
|------|--------|
| [[decisions/decisions-log]] | Arbitrages d'architecture et choix structurants |

---

## Modèles Ollama (référence)

| Modèle | Spécialité |
|--------|-----------|
| `qwen3.5:35b` | Code, refactor, tests, SQL, endpoints, UI |
| `gemma4:31b` | Planification, architecture, analyse, vision, docs |

Endpoint local : `http://localhost:11434`

---

## Règles de gouvernance

- Lire `index.md` en premier à chaque session
- Une information = une page (pas de duplication)
- `log.md` est append-only
- Signaler les contradictions avec ⚠️ CONTRADICTION
- Max 10 fichiers lus par session

*Dernière mise à jour : 2026-05-23*
