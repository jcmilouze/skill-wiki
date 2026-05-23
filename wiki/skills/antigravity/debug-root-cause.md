---
title: debug-root-cause
category: antigravity
type: skill
trigger: /debug-root-cause
priority: critical
depends_on: []
models: [gemma4:31b, qwen3.5:35b]
---

# debug-root-cause — Diagnostic méthodique des bugs

**Mission :** Identifier et corriger la cause racine d'un bug avec méthode scientifique. Jamais par essai-erreur.

## Quand l'utiliser

**OBLIGATOIRE** pour tout bug : "ne marche pas", "erreur", comportement inattendu, test qui échoue.

## Méthode scientifique (5 étapes strictes)

1. **REPRODUIRE** → Steps précises + environnement + logs/screenshots
2. **HYPOTHÈSES** → 3 causes possibles max, classées par probabilité
3. **INSTRUMENTER** → Logs ciblés, breakpoints conditionnels (pas de spray console.log)
4. **VALIDER** → Tester hypothèse #1 → confirmée ou infirmée
5. **CORRIGER** → Patch minimal à la cause + test de non-régression

## Format de sortie

```
🐛 BUG ANALYSIS : [Titre court]
🔄 1. Reproduction fiable (étapes, environnement, logs)
💭 2. Hypothèses (#1 haute, #2 moyenne, #3 faible)
🛠️ 3. Instrumentation proposée
✅ 4. Validation (hypothèse testée → CONFIRMÉE | INFIRMÉE)
🩹 5. Correctif (diff minimal)
🧪 Test de protection
```

## Taxonomie des bug patterns (par fréquence)

| Catégorie | Patterns fréquents |
|-----------|-------------------|
| **Null/Undefined** | Property access sur null, return manquant, destructuring sans default |
| **Off-by-One/Boundary** | Bounds de boucle, fence-post, collection vide supposée non-vide |
| **Async/Timing** | await manquant, race condition, closure stale, timers non nettoyés |
| **State** | Mutation in-place, UI désync, double source de vérité |
| **Import/Module** | Dépendance circulaire, mismatch export format, case-sensitivity |
| **Type/Coercion** | String vs number, loose equality, floating-point, falsy-but-valid (0, '') |
| **Env/Config** | Env var absente, path hardcodé, conflit de port |
| **API Contract** | Format réponse changé, champ requis manquant, encoding |
| **Scope/Closure** | Variable shadowing, `this` perdu, hoisting var |
| **Error Handling** | Exception swallée, promise rejection non gérée |

## Modèles recommandés

- Logique/flux → `gemma4:31b`
- SQL/performance → `qwen3.5:35b`
- UI visuel → `gemma4:31b` (vision)

## Contraintes absolues

- Ne jamais patcher sans identifier la cause racine
- Max 3 hypothèses — si plus, la tâche est mal ciblée
- Toujours commencer par la reproduction
- Toujours ajouter au moins 1 test de protection
- Patch minimal : ne corriger que la cause, pas refactorer autour
