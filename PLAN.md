# Tech Nova Website Redesign Plan (Editorial Space)

## Context / Goal
- Techfest website named **Tech Nova**
- Visual direction: **dark, space-themed** but **minimal/editorial (blog-like)**; cozy, clean, aesthetic
- **Animations must be minimal**
- **Registration via Google Form** (URL will be provided later)
- **Homepage must be single-screen ("one frame")** with no scrolling needed; detailed content lives on other pages
- Design reference: your **Figma mockup screenshot** (single-frame home layout)

## Repo / Stack (as identified)
- **Astro** + **Tailwind**
- Key files/pages:
  - `src/pages/index.astro` (currently long multi-section home)
  - `src/pages/events.astro`
  - `src/pages/sponsors.astro`
  - `src/pages/team.astro`
  - `src/pages/accommodation.astro`
  - `src/layouts/baseLayout.astro`
  - `src/components/navbar.astro`
  - `src/components/footer.astro`
  - `src/styles/global.css`

## Issues Observed (why the current site feels off)
- Too many accents/glows everywhere (visual noise)
- Home page is long and "marketing-section" heavy, not editorial
- Placeholder/CTA behavior is inconsistent (e.g. `#register` only makes sense on home)
- Scroll animations and floating shapes add busyness

## Target Look & Feel ("deep space editorial")
- Narrow reading column; strong, clean typography; lots of negative space
- Subtle starfield/noise texture (atmosphere without distraction)
- One accent color used sparingly (avoid neon overload)
- Minimal motion (small fade-in, optional slow background drift)

## Planned Changes (implementation)
1) `src/pages/index.astro`
   - Replace long scrolling homepage with a **single full-viewport hero frame**
   - No sections below; links direct to subpages for details

2) `src/styles/global.css`
   - Simplify tokens/palette; reduce/remove excessive glows and gradients
   - Establish editorial typography scale and layout widths
   - Keep starfield/noise subtle; improve readability

3) `src/components/navbar.astro`
   - Replace `#register` with a `Register` link pointing to a placeholder URL (until Google Form is provided)
   - Simplify styling (less glass/glow), match editorial direction

4) `src/layouts/baseLayout.astro`
   - Remove/reduce scroll animation logic
   - Reduce ambient background effects if they compete with the new design

5) Subpages consistency pass
   - Keep Events/Sponsors/Team/Accommodation pages consistent with the new design system
   - Move any "details" off the homepage into these pages

## Open Question
- Should the homepage hard-lock scrolling (`body { overflow: hidden; }` on `/`) or just naturally fit one screen and allow scroll even though there is nothing below? (Recommended: fit naturally, no hard lock unless necessary.)

## Copy/Paste Prompt For Continuing Work
You are helping me redesign an Astro + Tailwind website for a techfest named "Tech Nova".

The repo has these key files:
- `src/pages/index.astro` (currently a long, multi-section scrolling marketing homepage)
- `src/pages/events.astro`, `src/pages/sponsors.astro`, `src/pages/team.astro`, `src/pages/accommodation.astro`
- `src/layouts/baseLayout.astro`
- `src/components/navbar.astro`, `src/components/footer.astro`
- `src/styles/global.css`

Current design is neon/glow-heavy with lots of cards, animations, and placeholder content. I want to refactor it to a **dark, space-themed but minimal editorial** style (cozy, clean, like a blog/editorial site). **Animations must be minimal**.

Registration will be via a **Google Form**, but I will paste the URL later, so use a placeholder constant or `#` for now.

Important requirement: **Homepage must be a single-screen "one frame" layout with no scrolling required**, based on my Figma mockup (starfield background, centered hero content, minimal text, 1-2 CTAs). All detailed content (events, sponsors, team, accommodation) should be on their respective pages; the home page should only show the main details.

What I need you to do next:
1) Implement the new one-frame homepage by rewriting `src/pages/index.astro` into a full-viewport hero frame (no additional sections below).
2) Update global styling in `src/styles/global.css` to match an editorial space aesthetic:
   - reduce or remove excessive glows and gradients
   - keep one subtle accent color
   - keep starfield/noise subtle
   - set a readable typography scale and narrow content width approach for inner pages
3) Update `src/components/navbar.astro`:
   - Replace `#register` with a `Register` link that points to a placeholder (I’ll paste the Google Form later)
   - Keep navigation simple and editorial (less glass, less glow)
4) Remove or reduce scroll animation logic in `src/layouts/baseLayout.astro` (since we want minimal animations and the homepage won’t scroll).
5) Ensure subpages still look consistent with the new design system (we can do them after the home + global styles are done).
