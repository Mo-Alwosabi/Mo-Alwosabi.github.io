# CODEBASE_MAP.md — Living Architecture & Knowledge Graph

> **Agent Invariant**: Consult this map before modifying or writing code. Update it incrementally whenever files/routes/models are added or changed.

## 1. System Overview
- **Stack**: Astro 5.7.13 (Static SSG), Preact 10.27.2 (`@astrojs/preact` compat), Tailwind CSS 3.4.17, GSAP 3.13.0, AOS 2.3.4, Lucide Astro
- **Architecture**: Framework-native Astro multilingual static site (`en` default without prefix, `ar` under `/ar/` with RTL support)

## 2. Entry Points
- `astro.config.mjs` — Astro config, i18n (`en`, `ar`), Tailwind, Preact, Sitemap, Compress
- `src/pages/index.astro` — Root English landing page
- `src/pages/ar/index.astro` — Arabic RTL landing page

## 3. Registered Routes & Endpoints
| Route / URL | Handler File | Method | Description |
|---|---|---|---|
| `/` | `src/pages/index.astro` | GET | English portfolio home |
| `/ar/` | `src/pages/ar/index.astro` | GET | Arabic RTL portfolio home |
| `/en/` | `src/pages/en/index.astro` | GET | English portfolio home |
| `/ar/imprint/` | `src/pages/ar/imprint.astro` | GET | Arabic imprint |
| `/ar/privacy-policy/` | `src/pages/ar/privacy-policy.astro` | GET | Arabic privacy policy |
| `/en/imprint/` | `src/pages/en/imprint.astro` | GET | English imprint |
| `/en/privacy-policy/` | `src/pages/en/privacy-policy.astro` | GET | English privacy policy |

## 4. Key Customized Files
- `src/utils/me.ts` — Personal profile & Base64-obfuscated contact info (`Mohammed Ameen Al-Wosabi`)
- `src/utils/i18n.ts` — Translation helper (`en`, `ar`)
- `src/i18n/en.json` & `src/i18n/ar.json` — Full bilingual content (Hero, About Me, 9 Skill Clusters, 4 Timeline Milestones, Contact)
- `src/assets/profile.jpg` — Personal portrait photo
- `src/layouts/Layout.astro` — Dynamic `lang` and `dir="rtl"` / `dir="ltr"` + `Cairo` Arabic font
