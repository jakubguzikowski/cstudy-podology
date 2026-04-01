# Podologia Holistycznie — Client Website

> A production website built for a podology clinic in Wiry near Poznań, Poland.  
> **Live site:** [podologiaholistycznie.pl](https://podologiaholistycznie.pl)

---

## Overview

A solo freelance project — full ownership from initial client meeting through design, development, SEO configuration, and deployment. The client needed an online presence that would convert local search traffic into booked appointments.

---

## The Challenge

The client — a certified podologist running a private clinic — had no website and relied entirely on word-of-mouth referrals. Key requirements were:

- Appear in local Google search results for podology-related queries
- Make it easy for first-time visitors to book an appointment immediately
- Reflect a professional, trustworthy brand identity
- Work perfectly on mobile (the primary device of the target audience)
- Require zero technical knowledge to maintain

---

## Solution

A focused, single-page marketing site with a dedicated offer subpage. No CMS, no unnecessary complexity — just fast, accessible HTML with a clear conversion path on every section.

### Pages & Sections

| Route | Purpose |
|---|---|
| `/` | Home — hero, offer overview, services, location, social proof |
| `/oferta` | Full treatment list with descriptions |
| `/polityka-prywatnosci` | Privacy policy (GDPR compliance) |

### Conversion Design

Every section funnels toward one of three actions: **call**, **email**, or **book via Booksy**. CTAs are present in the hero and repeated in the footer — no dead ends.

### SEO & Discoverability

- `MedicalBusiness` JSON-LD structured data (name, address, opening hours, team, booking action)
- Meta tags, Open Graph and Twitter Card configured
- `sitemap.xml` and `robots.txt`
- PWA manifest for mobile installability
- `_headers` file with security and caching rules (Cloudflare/Netlify compatible)
- Polish-language content targeting local search queries

### Animations

Scroll-triggered entrance animations using a lightweight custom implementation — no animation library dependency. Elements slide in from left/right on first viewport entry via `IntersectionObserver`.

### Accessibility

- Visually hidden `<h1>` for screen readers where the logo serves as the visual heading
- Semantic HTML throughout (`<header>`, `<main>`, `<section>`, `<footer>`, `<nav>`)
- `aria-label` on all icon-only and context-dependent links
- Proper heading hierarchy across all pages

---

## Tech Stack

| Layer | Choice | Why |
|---|---|---|
| Framework | Next.js 15 (App Router) | SSG output, image optimization, font optimization |
| Language | TypeScript | Type-safe content layer and component props |
| Styling | SCSS Modules | Scoped styles, no runtime overhead, full control |
| Font | Gantari (Google Fonts via `next/font`) | Zero layout shift, self-hosted automatically |
| Icons | HugeIcons | Consistent icon set |
| Deployment | Static export | Hosted on edge CDN, sub-second load times |

---

## Architecture Decisions

**Content as a typed module** — all copy, labels, hrefs, and metadata live in `/src/content/` as TypeScript objects exported through a single `content` barrel. No CMS needed; copy changes are a single-file diff.

```
src/content/
├── index.ts          ← single export point
├── metadata.ts       ← site info, address, structured data input
├── headings.ts
├── labels.ts
├── services.ts
├── offer.ts
└── ...
```

**Section-based page composition** — the homepage is assembled from isolated section components (`Header`, `Offer`, `Service`, `Location`, `Proof`), each owning its own styles and markup. Easy to reorder or extend.

**SCSS design tokens** — colors, spacing, radius and breakpoints defined once in `_variables.scss` and `_mixins.scss`. All layout patterns (section padding, two-column wrapper, content stack) are reusable mixins.

---

## Results

- ✅ Live and indexed by Google
- ✅ Passes Core Web Vitals (LCP, CLS, FID)
- ✅ Booking link active via Booksy integration
- ✅ Client can share the URL and immediately send patients to a professional online presence

---

## Note on Source Code

This is a client project — the full source code is not publicly available. This repository serves as a case study. If you'd like to discuss the implementation in more detail, feel free to reach out.

---

## Contact

Interested in working together or want to see more?  
Check out my other projects or get in touch.

jakubguzikowski.dev
contact@jakubguzikowski.dev
linkedin.com/in/jakubguzikowski
