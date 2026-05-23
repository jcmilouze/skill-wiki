---
title: execute-plan
category: antigravity
type: skill
trigger: /execute-plan
priority: high
depends_on: [write-plan]
models: [qwen3.5:35b, gemma4:31b]
---

# execute-plan — Exécution stricte du plan

**Mission :** Exécuter fidèlement un plan validé, étape par étape, sans élargir le périmètre.

## Règles d'or

- **1 étape = 1 réponse**
- **Vérifier avant de passer à la suivante**
- **Déléguer le code à Ollama local**
- **Ne jamais dériver du plan**

## Processus par étape

1. **CONFIRMER** → Afficher l'étape courante et son critère de succès
2. **DÉLÉGUER** → Appeler Ollama avec le bon modèle
3. **EXÉCUTER** → Appliquer le code généré (review rapide sécurité)
4. **VÉRIFIER** → Tester selon le critère de succès
5. **RAPPORTER** → Résultat + statut
6. **DEMANDER** → Validation utilisateur avant étape suivante

## Checkpoint taxonomy (GSD)

| Type | Fréquence | Usage |
|------|-----------|-------|
| `human-verify` | 90% | Claude a fini, l'humain confirme |
| `decision` | 9% | L'humain choisit une direction |
| `human-action` | 1% | Aucune alternative CLI/API |

**Règle :** si Claude peut l'exécuter via CLI/API, Claude l'exécute.

## Dégradation contextuelle

| Tier | Utilisation | Comportement |
|------|------------|--------------|
| PEAK | 0–30% | Opérations complètes |
| GOOD | 30–50% | Préférer résumés, déléguer agressivement |
| DEGRADING | 50–70% | Frontmatter uniquement, avertir |
| POOR | 70%+ | Mode checkpoint d'urgence — `/reset-context` |

## Format de sortie par étape

```
📍 ÉTAPE [X]/[TOTAL] : [Titre]
[LOCAL] qwen3.5:35b — <description courte>

📂 Fichiers modifiés
🧪 Vérification (critères cochés)
📊 Statut : ✅ OK | ⚠️ ATTENTION | ❌ ÉCHEC
Lignes : +X -Y

🚀 Prochaine étape : Étape [X+1]
💬 Envoie "OK" pour continuer ou "fix" pour corriger
```

## Commandes utilisateur

- `OK` / `OK étape X` → passe à l'étape suivante
- `fix` / `fix étape X` → corrige l'étape courante
- `plan changé` → arrête et relance `/write-plan`

## Contraintes absolues

- Ne jamais coder une autre étape en avance
- Ne jamais élargir le périmètre du plan
- Ne jamais passer à la suivante sans validation
- Si blockers sécu détectés → stopper et signaler

## Liens

- Précédent : [write-plan](write-plan.md)
- Suivant : [review-hardening](review-hardening.md)
