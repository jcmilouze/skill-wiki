---
tags: project
updated: 2026-05-23
sources: /Users/jc/.gemini/antigravity/scratch/canal-top14/
---

# canal-top14

Landing page interactive Canal+ / Top 14, design "Stadium Dark".

## Stack

| Couche | Tech |
|--------|------|
| Framework | React 19 + TypeScript + Vite |
| Style | Tailwind v4 (OKLCH tokens) |
| Animation | Framer Motion |
| Icons | Lucide React |
| Router | React Router DOM |

## Design tokens OKLCH

```css
--color-gold: oklch(0.85 0.15 85)
--color-stadium-black: oklch(0.12 0 0)
--color-stadium-surface: oklch(0.18 0 0)
```

## Classes utilitaires

- `.glass-card` — glassmorphisme avec backdrop-blur
- `.shine-border` — animation conic-gradient sur le border
- `.shiny-text` — sweep lumineux sur le texte

## Pages

| Route | Fichier | Contenu |
|-------|---------|---------|
| `/` | `src/pages/Home.tsx` | Hero parallaxe, offre card, grille matchs |
| `/subscribe` | `src/pages/Subscribe.tsx` | Plans tarifaires, modal abonnement, trust badges, FAQ |

## Hero parallaxe

```tsx
const { scrollY } = useScroll()
const heroY = useTransform(scrollY, [0, 600], [0, 180])
const heroScale = useTransform(scrollY, [0, 600], [1, 1.15])
// motion.img avec style={{ y: heroY, scale: heroScale }} dans un div overflow-hidden
```

## Données matchs (Phases Finales 2026)

- Demi-finale 1 : Stade Toulousain vs Clermont — SAM. 30 MAI • 16H00 — CANAL+
- Demi-finale 2 : La Rochelle vs Racing 92 — DIM. 31 MAI • 15H30 — CANAL+ SPORT
- Grande Finale : Stade de France — SAM. 20 JUIN • 21H05 — CANAL+

## Dev server

```bash
cd /Users/jc/.gemini/antigravity/scratch/canal-top14
npm run dev  # http://localhost:5173
```
