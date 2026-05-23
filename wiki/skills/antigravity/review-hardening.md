---
title: review-hardening
category: antigravity
type: skill
trigger: /review-hardening
priority: critical
depends_on: [execute-plan]
models: [gemma4:31b, qwen3.5:35b]
---

# review-hardening — Audit qualité avant livraison

**Mission :** Garantir un code de qualité production avant toute livraison ou merge. Bloque si des seuils critiques ne sont pas atteints.

## Quand l'utiliser

**OBLIGATOIRE** après `/execute-plan` (> 2 étapes), modification sécurité/auth/DB, refactor multi-fichiers.

## Vérification 4 niveaux (GSD)

| Niveau | Question | Méthode |
|--------|----------|---------|
| **Exists** | Le fichier/fonction est-il présent ? | `ls`, `grep` |
| **Substantive** | Vraie implémentation (pas un stub) ? | Chercher : `TODO`, `FIXME`, `placeholder`, `[]`, `{}` |
| **Wired** | Connecté au système ? | Tracer imports, handlers, routes |
| **Functional** | Fonctionne-t-il réellement ? | Test manuel / CI |

Niveaux 1–3 = vérifiables automatiquement. Niveau 4 = checkpoint humain.

## 8 Checkpoints obligatoires

1. **SÉCURITÉ** : SQLi, XSS, secrets hardcodés, CORS unrestricted, auth
2. **DETTE TECHNIQUE** : duplication, complexité cyclomatique > 10, magic numbers
3. **TESTS** : couverture > 80% nouveaux changements, edge cases
4. **LISIBILITÉ** : noms explicites, commentaires utiles (pas de bruit)
5. **EDGE CASES** : null/undefined, timeouts, erreurs réseau
6. **PERFORMANCE** : N+1 queries, boucles O(n²), bundle size
7. **MAINTENANCE** : backward compat, gestion d'erreurs, évolutivité
8. **DOCUMENTATION** : README et API docs à jour si changement d'interface

## Format de sortie

```
🔍 REVIEW HARDENING : [Tâche/Feature]
📊 Verdict global : APPROVED ✅ | WARNINGS ⚠️ | BLOCKED 🛑
| # | Checkpoint | Statut | Détail | Action requise |
🛑 BLOCKERS (à corriger avant de continuer)
⚠️ WARNINGS (améliorations recommandées)
🚀 Recommandation : APPROVED → /ship-proof | FIX → corriger | BLOCKED → stop
```

## Seuils bloquants (BLOCKED automatique)

- Vulnérabilités OWASP Top 10
- Secrets hardcodés dans le code
- SQL non paramétrisé
- Tests < 80% sur les nouvelles modifications
- Fonctions > 50 lignes sans justification
- CORS unrestricted en prod

## Modèles recommandés

- Review standard → `gemma4:31b`
- Code complexe → `qwen3.5:35b`
- Sécurité critique → audit manuel

## Liens

- Précédent : [execute-plan](execute-plan.md)
- Suivant : [ship-proof](ship-proof.md)
