---
title: review
category: claude
type: skill
trigger: /review
source: Claude Code natif
---

# review — Review d'une Pull Request

**Mission :** Analyser et commenter une pull request GitHub en profondeur.

## Quand l'utiliser

Quand on veut un review structuré d'une PR (changements, qualité, risques, suggestions).

## Utilisation

```
/review          → review de la branche courante
/review <PR#>   → review d'une PR GitHub spécifique
```

## Ce que ça fait

- Lit les diffs de la PR
- Identifie les risques, la dette technique, les edge cases
- Commente par fichier et par bloc de changements
- Donne un verdict global (APPROVED / CHANGES REQUESTED)

## Liens

- Voir aussi : [security-review](security-review.md), [review-hardening](../antigravity/review-hardening.md)
