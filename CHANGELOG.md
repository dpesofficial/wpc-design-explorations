# WP Creative Design Explorations — Changelog

All major changes across design versions and the showcase index.

---

## [Unreleased] — Nav & Logo Polish (v4)

- Logo scaled 50% larger in nav (`22px → 33px`)
- Nav liquid glass: solid `#09102e` on load, frosted glass on scroll (no more jitter)
- Jitter fix: full-width fixed wrapper (`nav-wrap`) animates only `padding` — no `left/transform/width` layout thrash
- Background `#000000 → #09102e` deep navy
- Accent `--plum: #8052ff → #F7991C` WP Creative orange throughout
- All hardcoded `rgba(128,82,255,...)` values updated to `rgba(247,153,28,...)`
- Over-use of plum pulled back: kickers, eyebrows, stat suffixes, marquee highlights, footer badge, cursor dot, progress bar all set to white/ash — plum reserved for CTA buttons and headline emphasis only
- WP Creative logo SVG (nav + footer) replaced hex/text placeholder — brand colours restored

---

## [2.0.0] — v4 Dala Void Design + Index Bento Grid

_Commit: `e4028fb`_

### v4.html — New Design (Dala Design System)

- Dark void canvas: `#000000` background, `#8052ff` Plum Voltage sole accent, Inter weight 200
- Hero: split grid `1fr 1fr` — left text block, right `<canvas id="constellation">` particle field
- Particle constellation: 1,800 micro-shapes (circles, triangles, diamonds, squares), polar clustering, mouse repel physics (90px radius, force 2.4)
- Floating pill nav: `border-radius: 24px`, backdrop blur, SVG hexagon logo mark
- Water ripple: violet `rgb(128,82,255)`, screen blend mode, gate 48px, mousemove force 180, click force 500, alpha `Math.min(42, spec*0.48)`
- Sections: stats row, feature grid, testimonials, services list, CTA band, footer
- ACF-ready field structure matching wpc-botanical theme
- Scroll reveal (`rv` class), magnetic buttons, custom cursor ring

### index.html — Showcase Bento Grid Redesign

- 4-card 2×2 bento grid replacing previous single-column list
- Per-site gradient backgrounds: v1 warm terracotta, v2 sage green, v3 soft lavender, v4 deep void navy
- Fake browser chrome bar per card (3 dots + URL bar)
- `.bc__preview` height `557px` — full hero visible
- Real hero screenshots as card banners (`preview-v1/v2/v3/v4.png`)
- Pills, "Explore →" CTA foot per card
- Dead mini-cosmos JS block removed (canvas replaced by static `<img>`)

### preview-v1/v2/v3/v4.png

- Headless Chrome screenshots at `1440×900` via `--headless=new --screenshot`
- Python HTTP server (`python -m http.server 8765`) for local file serving
- v1: Darkroom Gallery darkroom cityscape hero
- v2: Botanical parchment hero
- v3: Iridescent sphere hero
- v4: Void cosmos particle field hero

### v1/v2/v3.html — Ripple Boost

- Gate `72px → 48px` (fires more readily)
- Mousemove force `110 → 180`
- Click force `280–320 → 500`
- Ripple radius `4px → 5px` (mousemove), `10px → 14px` (click)
- Alpha `Math.min(16, spec*0.19) → Math.min(42, spec*0.48)` — ~2.5× more visible

### v1.html — Card Hover Smoothing

- `.fc` transition `0.35s → 0.55s`, easing `cubic-bezier(.22,1,.36,1) → (.16,1,.3,1)`, lift `-6px → -5px`
- `.why-card` transition `0.3s → 0.5s`, slide `6px → 5px`
- `.tcard` transition `0.3s → 0.5s`, lift `-4px → -3px`

---

## [1.0.0] — Initial Commit

_Commit: `a43d0e6`_

### v1.html — Darkroom Gallery (Aker-inspired)

- Dark cinematic theme, full-bleed photography hero
- Custom cursor (ember dot + ring), progress bar, scroll reveal
- Water ripple on hero canvas — teal `rgb(15, 54, 57)`, multiply blend
- Counter animation (cubic ease), magnetic buttons, hero entrance animation
- Sections: hero, stats, features, results, services, testimonials, clients, CTA, footer

### v2.html — Perplexity Botanical (Parchment)

- Warm parchment palette, botanical SVG background
- Same interaction layer as v1 (ripple, cursor, scroll reveal)
- Botanical parallax background element on hero
- Adapted colour tokens: ink `#2c1f14`, paper `#faf6ef`, ember `#c85a1e`

### v3.html — OFF+BRAND Iridescent

- Iridescent sphere hero element, parchment base
- Layered CSS sphere with conic-gradient shimmer animation
- Same ripple and cursor system
- Richer hero composition with sphere parallax

### index.html — Monopo Saigon-style Showcase

- Original design: grid of version cards with site names and tags
- Water ripple on index hero banner
- Navigation to all 3 live design explorations

### wpc-botanical WordPress Theme

- Underscores-based theme for Laragon/local WP
- `front-page.php` + template parts: `hero.php`, `stats.php`, `features.php`, `results.php`, `services.php`, `diff.php`, `testimonials.php`, `clients.php`, `founders.php`, `process.php`, `cta.php`
- ACF Pro local JSON sync (`acf-json/group_wpc_homepage.json`) — auto-imports on activation
- `wpc_field()` helper with graceful fallbacks for all fields
- Full CSS from v2.html ported to `assets/css/style.css`
- `assets/js/main.js` — cursor, ripple, parallax, scroll reveal, counter, magnetic buttons
- Zip structure fix: `System.IO.Compression.ZipFile` with `"wpc-botanical/$relative"` entry paths (Compress-Archive baked absolute Windows paths — broke WP upload)

---

## Design Token Reference

| Token | v1 | v2 | v3 | v4 |
|---|---|---|---|---|
| Background | `#0a0a0a` | `#faf6ef` | `#faf6ef` | `#09102e` |
| Accent | `#b75928` ember | `#c85a1e` ember | `#c85a1e` ember | `#F7991C` orange |
| Text | `#e8e4df` | `#2c1f14` | `#2c1f14` | `#ffffff` |
| Ripple colour | `rgb(15,54,57)` teal | `rgb(15,54,57)` teal | `rgb(15,54,57)` teal | `rgb(247,153,28)` orange |
| Ripple blend | multiply | multiply | multiply | screen |
