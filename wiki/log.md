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

## [2026-05-23] ingest | Projets locaux — 26 projets ingérés

- Source : `/Users/jc/.gemini/antigravity/scratch/` (scan complet)
- Pages créées :
  - `projects/index.md` : catalogue général 26 projets, 6 catégories
  - `projects/canal-top14.md` : React 19 + Tailwind v4 + Framer Motion
  - `projects/velotrack.md` : MapLibre, BRouter, Zustand (4 variantes)
  - `projects/ucl-bets.md` : Next.js + Drizzle + LibSQL + Ollama
  - `projects/autocorrect.md` : Next.js + Clerk + Prisma + Google APIs
  - `projects/ollama-brain-watch.md` : Recharts + Tailwind v4, monitoring Ollama
  - `projects/postgres-connector.md` : MCP SDK + pg + Zod
- Index mis à jour avec section Projets
- Contradictions : aucune

## [2026-05-23] update | allowed-tools ajoutés sur 4 skills

- Pages mises à jour : write-plan, review-hardening, ship-proof, debug-root-cause
- Changement : ajout frontmatter `allowed-tools` (find/grep/ls/cat selon le skill)
- Source : sync depuis `/Users/jc/.claude/skills/*/SKILL.md`
- Contradictions : aucune
