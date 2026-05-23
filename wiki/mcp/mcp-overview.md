---
tags: [mcp]
updated: 2026-05-23
---

# MCP — Vue d'ensemble des connecteurs

## Qu'est-ce qu'un MCP
Model Context Protocol — interface standardisée permettant à Claude Code d'appeler des outils externes (APIs, services) comme des tools natifs, sans passer par du code d'intégration custom.

## Connecteurs actifs

### Google Drive
- Préfixe : `mcp__claude_ai_Google_Drive__`
- Opérations disponibles : `read_file_content`, `create_file`, `copy_file`, `download_file_content`, `search_files`, `list_recent_files`, `get_file_metadata`, `get_file_permissions`
- Usage wiki : ingérer des documents Drive comme sources, exporter des pages wiki vers Drive

### Web Search / Web Fetch
- Outils : `WebSearch`, `WebFetch`
- Usage wiki : enrichir une ingestion avec des sources web, vérifier des faits, récupérer une URL

## Connecteurs à documenter (si activés)
- [ ] Slack — threads et canaux
- [ ] GitHub — issues, PRs, code
- [ ] Base de données locale

## Conventions d'usage
- Ne pas appeler un MCP sans intention claire
- Enregistrer dans log.md si la donnée récupérée est intégrée au wiki
- Préférer les sources locales aux appels réseau quand c'est possible

## Liens
- [[agents/agent-claude-code]]
- [[workflows/ingest-source]]
