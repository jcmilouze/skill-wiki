# Schéma du Wiki — Règles de gouvernance pour Claude Code

## Rôle de ce fichier
Ce fichier est le contrat entre toi (Claude Code) et ce wiki.
Il définit les conventions, les workflows obligatoires et les règles de maintenance.
Tu dois le lire en premier à chaque session impliquant le wiki.

## Structure du wiki

```
wiki/
├── CLAUDE.md         ← ce fichier (schéma, règles)
├── index.md          ← catalogue de toutes les pages
├── log.md            ← journal append-only
├── agents/           ← rôle de chaque agent
├── skills/           ← procédures des skills Antigravity
├── workflows/        ← procédures détaillées par opération
├── mcp/              ← connecteurs et outils externes
├── sources/          ← sources brutes ingérées
└── decisions/        ← arbitrages d'architecture
```

## Règles absolues

1. **Une seule source de vérité.** Une information n'existe qu'à un seul endroit. Les autres pages y font référence via un lien `[[page]]`.
2. **index.md est toujours mis à jour.** Après chaque création ou modification majeure de page, mettre à jour l'entrée correspondante dans `index.md`.
3. **log.md est append-only.** Ne jamais modifier ou supprimer une entrée existante. Ajouter uniquement à la fin.
4. **Pas de duplication.** Avant de créer une page, vérifier dans `index.md` qu'elle n'existe pas déjà.
5. **Signaler les contradictions.** Si une nouvelle information contredit une page existante, ajouter `> ⚠️ CONTRADICTION` dans la page concernée et l'enregistrer dans log.md.
6. **Frontmatter YAML minimal.** Ajouter uniquement `tags`, `updated` et `sources` quand utile.

## Convention de nommage

- Fichiers : `kebab-case.md`
- Titres H1 : lisible, identique au nom de fichier
- Tags : `agent` | `skill` | `workflow` | `mcp` | `decision` | `source`

## Format d'entrée de log

```
## [YYYY-MM-DD] type | titre
- Action effectuée
- Pages touchées : [[page1]], [[page2]]
- Contradictions : aucune / voir [[page]]
```

Types : `ingest` | `query` | `lint` | `update` | `decision`

## Workflow par défaut (nouvelle session)

1. Lire `index.md` pour connaître l'état du wiki
2. Lire les 5 dernières entrées de `log.md` pour savoir ce qui a été fait récemment
3. Identifier l'intention : ingest / query / lint / update
4. Charger la skill ou le workflow correspondant
5. Exécuter, puis mettre à jour `index.md` et `log.md`

## Quand déclencher un lint

- Après 5+ ingestions consécutives
- Si l'utilisateur le demande
- Si des contradictions ont été signalées et non résolues

## Limites de contexte

- Lire au maximum 10 fichiers complets par session
- Approche chirurgicale : lire `index.md` d'abord, puis seulement les pages nécessaires
- Si le wiki dépasse ~200 pages : signaler le besoin d'un outil de recherche (ex: qmd)
- Après ~2h de session : recommander un reset de contexte
