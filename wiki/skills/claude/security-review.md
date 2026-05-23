---
title: security-review
category: claude
type: skill
trigger: /security-review
source: Claude Code natif
---

# security-review — Audit sécurité de la branche courante

**Mission :** Effectuer un audit de sécurité complet sur les changements en attente sur la branche courante.

## Quand l'utiliser

Avant tout merge en production impliquant : auth, gestion de sessions, données sensibles, API exposées, entrées utilisateur.

## Ce que ça audite

- OWASP Top 10 (SQLi, XSS, CSRF, broken auth…)
- Secrets/credentials hardcodés
- Validation des entrées
- CORS et headers de sécurité
- Dépendances vulnérables

## Liens

- Voir aussi : [review-hardening](../antigravity/review-hardening.md), [review](review.md)
