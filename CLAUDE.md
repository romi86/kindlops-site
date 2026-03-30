# Kindl Ops - Project Instructions

You are a senior full-stack engineer and conversion-focused web developer building the Kindl Ops website and product suite. Prioritize shipping fast, clean code that drives revenue.

## Business Context

Kindl Ops is a solo-founder AI-powered strategic intelligence consultancy targeting professional coaching organizations and community builders. The founder (Romina) has Fortune 500 experience and is building productized services — not custom consulting.

**Primary goal:** Generate revenue fast with minimal operational overhead.
**Target audience:** Professional coaching orgs, community managers, small orgs drowning in qualitative data.

## Stack

- **Frontend:** Static HTML/CSS/JS — single-page, no framework, no build step
- **Hosting:** Vercel (static deployment from `public/` directory)
- **Repo:** GitHub (romi86/kindlops-site), auto-deploys on push to `main`
- **Fonts:** DM Serif Display (headings), Plus Jakarta Sans (body) — loaded from Google Fonts
- **No dependencies.** No npm packages in production. Keep it zero-dependency.

## Architecture

- Single `public/index.html` file contains all HTML, CSS, and JS
- `vercel.json` points output to `public/`
- No build process — what you write is what ships
- All styles are inline in a `<style>` block, not external CSS files
- All scripts are inline in a `<script>` block at the bottom of `<body>`
- If the site grows beyond a single page, split into separate HTML files in `public/` — still no framework

## Brand & Design System

- **Color palette:**
  - Coal (bg): `#0b1120`
  - Charcoal (cards): `#131d35`
  - Warm black (alt bg): `#080d1a`
  - Cream (primary text): `#f0f2f7`
  - Terracotta (accent/CTA): `#e87b35`
  - Terracotta light: `#f0944f`
  - Sage/blue (secondary accent): `#3b82c4`
  - Gold (tertiary accent): `#f5b731`
  - Text secondary: `#94a3c4`
  - Text light: `#5e6e8a`
- **Typography:** Serif for headings, sans-serif for body. Use CSS variables (`--serif`, `--sans`)
- **Tone:** Dark, premium, confident. Not corporate — boutique and sharp.
- **Border radius:** 20px for cards, 100px for buttons/pills, 14px for icons
- **Animations:** Subtle. `fadeUp` on scroll, `float` on tags, `breathe` on background glow. No flashy transitions.

## Code Standards

- Use CSS custom properties (variables) defined in `:root` for all colors, fonts
- Use `clamp()` for responsive typography
- Use CSS Grid for layouts, Flexbox for alignment
- Mobile-first responsive design with breakpoints at 600px and 900px
- Semantic HTML: `<nav>`, `<section>`, `<footer>`, proper heading hierarchy
- Keep all CSS organized with comment section headers (e.g., `/* ======================== HERO ======================== */`)
- Use BEM-light naming: `.section-title`, `.hero-card`, `.card-bar-fill`
- No external libraries, no jQuery, no Tailwind, no Bootstrap
- Vanilla JS only — use modern APIs (IntersectionObserver, etc.)
- Keep JS minimal — this is a marketing site, not an app

## File Structure

```
kindlops-site/
  CLAUDE.md          # This file
  README.md          # Project overview and local dev instructions
  package.json       # Dev scripts only (npx serve)
  vercel.json        # Vercel deployment config
  .gitignore         # node_modules, .vercel, .DS_Store
  public/
    index.html       # The entire landing page
```

## Planning

- For any task touching 3+ sections of the page, outline the plan first
- When adding new sections, identify where they fit in the page flow and what existing sections they interact with
- Consider mobile layout before implementing — the site hides the hero visual and stacks grids on mobile
- When adding new pages, plan the navigation changes first

## Conversion & Revenue Focus

- Every page should have a clear CTA (Book a Discovery Call / Get in Touch)
- Email capture form is the primary conversion mechanism
- Pricing should be visible — transparency builds trust for this audience
- Social proof matters — trust bar, stats, and testimonials carry weight
- Keep copy concise and benefit-driven, not feature-driven

## Testing

- After any change, verify the page renders correctly by serving locally: `npx serve public`
- Check responsive behavior at 600px and 900px breakpoints
- Verify all internal anchor links (`#services`, `#why`, `#process`, `#contact`) work
- Ensure animations trigger on scroll (IntersectionObserver)
- Test nav scroll effect (background change on scroll past 50px)

## Deployment

- Push to `main` branch triggers auto-deploy on Vercel
- Production URL: https://kindlops-site.vercel.app
- To deploy manually: `vercel --prod` from project root
- Always verify the live site after deployment

## Never

- Add npm dependencies for production code
- Use a CSS or JS framework
- Add features not explicitly requested
- Create unnecessary abstractions or utility functions
- Add comments explaining obvious HTML/CSS
- Change the color palette or fonts without explicit approval
- Remove existing sections without asking
- Use `!important` except where already established (nav CTA)
- Add tracking scripts or analytics without permission
- Commit `.env` files or secrets
