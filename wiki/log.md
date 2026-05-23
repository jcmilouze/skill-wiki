# Log du Wiki

Journal append-only. Ne jamais modifier les entrées existantes. Ajouter uniquement à la fin.

Format : `## [YYYY-MM-DD] type | titre`
Types : `ingest` | `query` | `lint` | `update` | `decision`

---

## [2026-05-23] decision | Initialisation du wiki

- Création de la structure initiale du wiki Claude Code / Antigravity
- Basé sur le pattern LLM Wiki
- Pages créées : index, agents, skills wiki-meta, workflows, mcp-overview, sources-index, decisions-log
- Contradictions : aucune

## [2026-05-23] ingest | Skills Antigravity + Claude Code

- Source : `/Users/jc/.claude/skills/` (8 SKILL.md) + skills natifs Claude Code (10)
- Pages créées :
  - `skills/antigravity/` : agent, brainstorm-spec, write-plan, execute-plan, review-hardening, ship-proof, debug-root-cause, ollama-dispatch (8 pages)
  - `skills/claude/` : init, review, security-review, update-config, keybindings-help, simplify, fewer-permission-prompts, loop, schedule, claude-api (10 pages)
- Index mis à jour avec les deux catégories de skills
- Contradictions : aucune
- Auteur : Claude Sonnet 4.6 (assistant wiki)
