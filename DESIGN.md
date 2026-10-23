# Design System: Agostina Castello Portfolio

## 1. Visual Theme & Atmosphere

A gallery-airy, centered composition with clinical precision and a warm editorial undercurrent. The atmosphere is confident without being aggressive — like a well-lit studio portfolio where the work speaks loudly and the chrome disappears. White space is load-bearing. Typography carries the hierarchy; components stay out of the way.

- **Density:** 3/10 — Art Gallery Airy. Generous negative space, few elements per viewport
- **Variance:** 5/10 — Offset Symmetric. Centered hero, asymmetric card grid, deliberate imbalance in supporting sections
- **Motion:** 5/10 — Fluid CSS. Spring-physics reveals, perpetual typewriter loop, subtle fade-ups. No cinematic drama

The palette pairs a single saturated coral-orange accent with a deep violet for interactive chrome, anchored to pure white surfaces and near-black ink. No gradients, no blur backdrops, no glassmorphism.

---

## 2. Color Palette & Roles

| Name | Hex | Role |
|---|---|---|
| **Pure Canvas** | `#FFFFFF` | Primary background — hero, cards, nav |
| **Lavender Field** | `#E8EDFF` | Accent surfaces — metrics strip, footer, about section |
| **Lavender Mid** | `#D4DCFF` | Borders on lavender surfaces, photo ring |
| **Charcoal Ink** | `#0C0B1D` | Primary text — headings, body |
| **Slate Stone** | `#4D4B63` | Secondary text — descriptions, captions |
| **Muted Dusk** | `#5C5978` | Tertiary text — metadata, tags |
| **Whisper Border** | `#CDD2F0` | 1px structural lines, card edges |
| **Electric Violet** | `#5B2FE8` | Primary interactive — CTA button, active links, typewriter cursor |
| **Violet Hover** | `#4520C4` | CTA hover state |
| **Violet Wash** | `#EDE8FD` | Pill backgrounds, light tag fills |
| **Coral Fire** | `#FF5523` | Accent — name headline, dot decorators, highlights |
| **Coral Blush** | `#FFF0EC` | Soft coral surface for cards or callouts |
| **Sage Mist** | `#DDF4EC` | Card tint — case study #1 |
| **Peach Sand** | `#FFE8DC` | Card tint — case study #2 |
| **Lilac Smoke** | `#EEE0FF` | Card tint — case study #3 |

**Dark mode shifts:** All surfaces invert to deep violet-blacks (`#0A0915`, `#141228`). Coral lightens to `#FF7050`. Violet brightens to `#8F6FFF`. Borders tighten to `#2A2748`.

**Banned:** Pure black `#000000`. Neon glow shadows. Oversaturated gradients. Any second accent color.

---

## 3. Typography Rules

- **Display / Headlines:** `Syne` — geometric, condensed character. Track-tight (`letter-spacing: -0.03em` to `-0.04em`). Weight 700–800. Used for name, role title, section headings, card titles. Never screaming — hierarchy through size contrast, not maximalism
- **Body / UI:** `Plus Jakarta Sans` — humanist sans. Relaxed leading (`line-height: 1.6–1.7`). Weight 300–600. Max line length 65 characters (`max-width: 560px` at body size). Used for descriptions, nav links, metadata, tags
- **Mono:** None currently — if added, use `JetBrains Mono` for timestamps or code snippets only
- **Scale (rem):** `0.75 / 1 / 1.125 / 1.375 / 1.875 / 2.75 / 4 / 5.5`
- **Hero role title:** `clamp(2.4rem, 5.5vw, 5.5rem)` — typewriter target, never wraps on desktop
- **Hero name line:** `2.75rem`, Coral Fire, weight 700
- **Intro line:** `1.125rem`, Charcoal Ink, weight 500

**Banned:** `Inter`. `Georgia`, `Times New Roman`, `Garamond` — any generic serif. Font-size below `0.75rem` for any visible label.

---

## 4. Hero Section

**Structure (centered, full-width text block):**

```
Hi 👋! I'm                          ← Plus Jakarta Sans, 1.125rem, Charcoal Ink
Agostina Castello                   ← Syne, 2.75rem, Coral Fire #FF5523, weight 700
Product Designer|                   ← Syne, clamp(2.4rem–5.5rem), Charcoal Ink, typewriter loop
UX Enterprise & Accessibility Spec  ← Plus Jakarta Sans, 1.125rem, Slate Stone, static
```

**Typewriter loop:** cycles `Product Designer → UX/UI Designer → Design Systems Lead → Enterprise UX Designer → B2B SaaS Designer`. Cursor `|` in Electric Violet, `step-end` blink at 0.75s. Type speed 70ms/char, delete 40ms/char, pause at end 1800ms, pause at start 400ms.

**CTA row:** `E-mail ↗` and `LinkedIn ↗` as text links in Electric Violet with a single 1px underline. No buttons in the hero body. The nav carries the primary CTA.

**Banned in hero:** Scroll arrows. Bouncing chevrons. "Scroll to explore." Secondary CTA buttons. Background imagery. Gradient overlays. Asymmetric layouts for this centered composition.

---

## 5. Component Stylings

**Navigation**
- Fixed top, `60px` height, Pure Canvas background
- Logo: `AC` monogram in Electric Violet, Syne 700
- Links: Plus Jakarta Sans, weight 500, Charcoal Ink. Hover: Electric Violet
- CTA: Electric Violet filled pill, `5px 20px` padding, `100px` border-radius. Hover: Violet Hover. Active: `-1px` translate Y, tactile push
- No outer glow. No blur backdrop. Border-bottom `1px` Whisper Border on scroll

**Cards (Work Grid)**
- Generous rounding: `20px` border-radius
- Tinted backgrounds (Sage Mist, Peach Sand, Lilac Smoke) — no white cards on white canvas
- No box-shadow by default. Hover: `translateY(-4px)` with `0 12px 32px rgba(12,11,29,0.08)` — shadow tinted to Charcoal Ink, never pure black
- Featured card spans full 12-column grid. Supporting cards: asymmetric 5/7 or 6/6 splits — never 3 equal columns
- Card arrow: Electric Violet icon in Lavender Field circle. Hover rotates `45deg`

**Tags / Pills**
- Small: `0.75rem`, Plus Jakarta Sans 600, uppercase or mixed case
- Background: Lavender Field or Violet Wash for skill tags; Coral Blush for coral variants
- `100px` border-radius, `4px 10px` padding
- No border. No shadow

**Metrics Strip**
- Lavender Field background
- Large number in Syne 700, Electric Violet
- Label in Plus Jakarta Sans, Slate Stone
- 3-column grid — exception allowed for metrics-only rows (not feature cards)

**Inputs / Contact**
- Not currently present. If added: label above, Plus Jakarta Sans, Slate Stone. Focus ring Electric Violet `2px`. Error text below in coral. No floating labels

**Loaders**
- Skeletal shimmer in Lavender Field matching layout dimensions. Never circular spinners

---

## 6. Layout Principles

- **Max-width:** `1160px`, centered, `padding: 0 clamp(1rem, 4vw, 2rem)`
- **Hero:** Full viewport height feel, `padding-top: calc(60px + 5rem)`, centered single column
- **Work grid:** CSS Grid 12-column. Featured card: `12 cols`. Pairs: `5 + 7` or `6 + 6` asymmetric. Never 3 equal horizontal cards
- **About section:** `1fr 340px` split with generous `4rem` gap
- **Spacing scale (rem):** `0.5 / 0.75 / 1 / 1.25 / 1.5 / 2 / 2.5 / 3 / 4 / 5`
- **Section vertical rhythm:** `clamp(3rem, 8vw, 5rem)` between sections
- No `calc()` percentage hacks. No absolute positioning for layout. Every element in its own clean spatial zone — no overlapping

---

## 7. Responsive Rules

- **< 768px:** All multi-column grids collapse to single column. Work cards full-width. About grid stacks (photo order `-1`)
- **Typography:** Headlines via `clamp()`. Body minimum `1rem`. No text below `0.75rem`
- **Touch targets:** All interactive elements minimum `44px` tap height
- **Nav:** Hamburger toggle replaces horizontal links. Mobile menu drops below nav in Pure Canvas, border-bottom Whisper Border
- **Full-height sections:** `min-height: 100dvh` — never `100vh` (iOS Safari jump)
- **Horizontal overflow:** Zero tolerance — critical failure

---

## 8. Motion & Interaction

- **Reveal:** `fade-up` — `translateY(20px) opacity(0)` → `translateY(0) opacity(1)`. Easing: `cubic-bezier(0.22, 0, 0.1, 1)`. Duration `160ms` for micro, `600–700ms` for section reveals. Staggered cascade: `0.05s / 0.1s / 0.15s / 0.2s / 0.25s / 0.35s` offsets
- **Typewriter:** Perpetual loop on hero role. `step-end` cursor blink. Spring-paced character timing
- **Pulse dot:** `pulse-dot` — scale `1 → 1.3 → 1` over `2s`, `ease-in-out infinite`. Used on status decorators
- **Card hover:** `translateY(-4px)` + shadow reveal, `160ms` ease. Arrow rotates `45deg`
- **CTA active:** `translateY(-1px)` tactile push on `:active`
- **Hardware-accelerated only:** `transform` and `opacity`. Never animate `top`, `left`, `width`, `height`
- **No scroll-triggered parallax.** No heavy GSAP choreography. No page transitions

---

## 9. Anti-Patterns (Banned)

- No `Inter` font — use `Syne` + `Plus Jakarta Sans`
- No generic serifs (`Georgia`, `Times New Roman`, `Garamond`)
- No pure black `#000000` — use Charcoal Ink `#0C0B1D`
- No neon outer glow shadows — shadows tinted to Charcoal Ink only
- No oversaturated gradients or gradient text on large headings
- No glassmorphism or blur backdrops
- No custom mouse cursors
- No overlapping elements — strict spatial separation
- No 3-column equal feature card grids — asymmetric layouts only
- No placeholder names ("John Doe", "Acme Corp")
- No fake round numbers (`99.9%`, `100%`) in metrics
- No AI copywriting clichés: "Elevate", "Seamless", "Unleash", "Next-Gen", "Transform"
- No filler UI: "Scroll to explore", scroll arrows, bouncing chevrons
- No broken image links — use real assets or structured SVG placeholders
- No second accent color — Coral is a name accent only; Electric Violet is the sole interactive accent
- No emojis in body copy or UI labels — hero intro `👋` is the single permitted exception
