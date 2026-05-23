---
title: ship-proof
category: antigravity
type: skill
trigger: /ship-proof
priority: critical
depends_on: [review-hardening]
models: []
---

# ship-proof — Livraison production-ready

**Mission :** Finaliser une livraison 100% production-ready. Ne jamais shipper sans `/review-hardening` APPROVED.

## Quand l'utiliser

**OBLIGATOIRE** après `/review-hardening` APPROVED, ou quand l'utilisateur dit "ship it", "déploie", "livre".

## Checklist 7 points

1. **BUILD FINAL** → compile sans erreur, tous environnements
2. **SMOKE TESTS** → flux critiques testés
3. **CHANGELOG** → résumé des changements (format conventionnel)
4. **COMMIT PROPRE** → conventional commits (`feat:`, `fix:`, `refactor:`, `chore:`)
5. **DOCUMENTATION** → README / API docs mis à jour si nécessaire
6. **CHECKLIST DEPLOY** → variables d'env, migrations, rollback plan
7. **SIGN-OFF** → validation finale prêt pour prod

## Format de sortie

```
🚀 SHIP-PROOF : [Nom feature/bugfix]
📊 Statut global (Build / Tests / Review / Couverture)
🔨 1. Build & Tests
📋 2. Changelog (## [version] - YYYY-MM-DD)
💬 3. Commit message (conventional)
📚 4. Documentation
🚀 5. Checklist déploiement
✅ SIGN-OFF : READY FOR PROD
Risque résiduel : [faible | moyen | élevé]
```

## Checklist Coolify (si VPS impliqué)

- [ ] Variables `VITE_*` à jour dans Coolify UI → redéploiement déclenché
- [ ] Volumes persistants vérifiés
- [ ] Alias réseau Coolify corrects (inter-services via alias, pas localhost)
- [ ] Rollback : Coolify → service → deploy history → version précédente

## Contraintes absolues

- Ne jamais shipper si build ou tests échouent
- Ne jamais shipper si BLOCKERS de review-hardening sont ouverts
- Toujours inclure un plan de rollback (`git revert HEAD`)
- Couverture > 90% sur les nouvelles modifications

## Liens

- Précédent : [review-hardening](review-hardening.md)
- Pipeline complet : [agent](agent.md)
