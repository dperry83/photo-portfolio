# Photography Website README

This document is the working record for the new photography website build.

The goal is to build a simple, clear, on-brand website for a founder-focused photography business, using a stack that strengthens core web fundamentals now and leaves room to grow later. Version 1 is intentionally a static front end built with HTML, CSS, and vanilla JavaScript, with progressive enhancement for light interaction.~

## Project goal

Build a founder-focused photography website that:

- Feels credible, clear, and low-drama
- Starts as a static marketing site
- Strengthens core front-end skills through direct HTML, CSS, and JavaScript work
- Is built in a way that can grow later
- Leaves room for future custom backend features such as client galleries or image selection tools

## Decisions made

### Version 1 tech stack

**Decision:** Use **HTML, CSS, and vanilla JavaScript only** for version 1.

**Why:** This keeps the build grounded in web fundamentals instead of adding framework complexity too early. HTML provides structure and semantics, CSS handles presentation, and JavaScript is reserved for simple interactive behaviors and direct DOM work.

**Decision timing:** Updated now after revising the build strategy.

### Frameworks for version 1

**Decision:** **No Nuxt, no Vue, and no framework-led architecture in version 1.**

**Why:** The current priority is to get more reps with fundamentals and reduce stack overwhelm. Frameworks remain possible future layers, but they are not the starting point for this version.

**Decision timing:** Updated now after revising the build strategy.

### Styling approach

**Decision:** Use **plain CSS** with a small custom design system layer.

**Why:** Version 1 should strengthen direct layout, spacing, typography, and responsive design skills. A simple custom design system still helps the site feel consistent and on-brand without bringing in a CSS framework too early.

**Decision timing:** Updated now.

### JavaScript scope for version 1

**Decision:** Keep JavaScript **focused and intentional**.

**Planned uses:**

- Gallery filtering
- Lightbox behavior
- Menu toggles
- Simple form behavior

**Why:** These features support the portfolio experience while giving useful practice with DOM manipulation, event handling, and simple browser state changes.

### Version 1 scope

**Decision:** Start with a **beautiful static website**.

**Why:** This keeps version one focused on the public-facing marketing site instead of turning it into a larger software project too early. The public site should do the main job first: communicate credibility, show the work, and convert the right visitors into inquiries.

**Decision timing:** Decided now.

### Content management for version 1

**Decision:** **No CMS in version 1.**

**Why:** The content model is intentionally being deferred. Version one will use hardcoded content in static files until a more formal content workflow becomes necessary.

**Decision timing:** Decided now.

### Sitemap and navigation

**Decision:** Version 1 sitemap is **Home, Portfolio / Gallery, About, Contact**.

**Why:** This keeps the site tightly focused on the core portfolio experience and reduces scope while version 1 is being built from core web fundamentals.

**Decision timing:** Updated now after revising version 1 scope.

### Design direction

**Decision:** The visual tone for version 1 is **credible, calm, modern, human, clear, and low-drama**.

**Why:** The site needs to feel like a trusted business tool with taste. It should avoid both generic corporate stiffness and over-styled photography-portfolio clichés.

**Decision timing:** Decided now, before visual design and component work.

## Working assumptions

These are current assumptions, not permanent commitments:

- The site should stay simple and easy to reason about.
- The first version should prioritize clear messaging, portfolio presentation, and inquiry flow.
- The stack should support future expansion without forcing that expansion into version one.
- Future app-like or backend features, if built, should be treated as later layers rather than shaping version 1.

## Decisions still to make

### Hosting platform

**Status:** Not decided yet.

**Current shortlist:**

- Netlify
- GitHub Pages
- Cloudflare Pages

**When to decide:** Before the first public deploy.

**What will drive the choice:** Simplicity, static hosting workflow, custom domain setup, and how easy it is to keep deploys low-drama for a plain HTML/CSS/JS site.[cite:112][cite:116]

### Contact form handling

**Status:** Not decided yet.

**Question:** Should the contact form use a simple third-party form service, a static host form feature, or just email/contact links in the earliest version?

**When to decide:** Before the contact page is finalized.

### Initial content structure

**Status:** Not decided yet.

**Question:** Should version one stay fully hardcoded, or should a lightweight content convention be created across HTML files and data objects?

**When to decide:** During early implementation, before page build gets too far.

### CMS for later

**Status:** Deferred by design.

**Current shortlist:**

- Storyblok
- Strapi
- Sanity

**When to decide:** Only after the static site is live and the content model becomes a real workflow problem.

**What will drive the choice:**

- Storyblok if visual editing for marketing pages becomes the main need
- Strapi if backend control becomes more important
- Sanity if content modeling becomes more complex over time

### Future backend features

**Status:** Explicitly out of scope for version 1.

**Examples:**

- Client gallery portal
- Selection workflow
- Protected client pages
- Admin tools

**When to decide:** After the public site is live and doing its core job well.

**What will drive the choice:** Whether there is a real business workflow problem worth solving with custom software.

## Current implementation phases

### Phase 1: Foundation

- Confirm stack
- Confirm sitemap and navigation
- Confirm design direction
- Define basic design system
- Set up static project structure
- Set up base HTML, CSS, and JavaScript files

### Phase 2: Static marketing site

- Build homepage
- Build portfolio / gallery page
- Build about page
- Build contact page
- Refine accessibility, SEO basics, and performance

### Phase 3: Progressive enhancement

- Add gallery filtering
- Add lightbox behavior
- Add menu toggle behavior
- Add simple form behavior

### Phase 4: Future expansion

- Revisit Tailwind if styling workflow becomes slow
- Revisit Vue if componentization or reactive UI becomes genuinely useful
- Revisit Nuxt only if the project later benefits from a framework-level setup
- Revisit CMS options
- Revisit backend architecture and client workflow tools

## What this README is for

This file is the project memory for stack and architecture decisions.

As the project moves forward, this README should be updated whenever:

- A major tool decision is made
- Scope changes
- The deployment plan changes
- A deferred decision becomes active
- A new phase begins

## Current recommendation snapshot

If work started today, the build would use:

- **HTML** for structure
- **CSS** for styling and responsive layout
- **Vanilla JavaScript** for light interaction
- **A static version 1 site** with no CMS and no backend
- **A later review** for frameworks, content tooling, CMS, and client gallery features

## Recommended folder structure

The recommended version 1 repo structure is:

```txt
photography-site/
├── README.md
├── docs/
│   ├── sitemap.md
│   └── design-direction.md
├── index.html
├── portfolio.html
├── about.html
├── contact.html
├── assets/
│   ├── css/
│   │   ├── reset.css
│   │   ├── tokens.css
│   │   ├── base.css
│   │   ├── layout.css
│   │   └── components.css
│   ├── js/
│   │   ├── main.js
│   │   ├── gallery.js
│   │   ├── lightbox.js
│   │   └── contact.js
│   └── images/
│       ├── portfolio/
│       ├── portraits/
│       ├── icons/
│       └── brand/
└── favicon.ico
```

### Why this structure

This structure keeps version 1 grounded in plain web fundamentals. HTML files map directly to pages, CSS is separated into a small design system and layout layer, and JavaScript is split by behavior so interactions stay easy to reason about as the site grows.

A few project-specific rules go with this structure:

- Keep documentation in `docs/` once the repo exists.
- Keep CSS organized by responsibility, not by page, unless page-specific styles become unavoidable.
- Keep JavaScript small and behavior-based.
- Do not create backend or build-tool complexity in version 1 unless a real need appears.

## Deployment setup

### Recommended default

The current recommended default is to keep the repo and deploy it as a plain static site from Git.

A good starting setup is:

- GitHub for version control
- Netlify, GitHub Pages, or Cloudflare Pages for static hosting

### Why this is the default

A plain HTML/CSS/JS site does not need a framework-specific deployment pipeline. Static hosting platforms can deploy directly from a Git repository, and Netlify also supports deploying a static site from Git without a build command when the repo already contains the static files.

### Version 1 deployment flow

1. Create the static site files locally.
2. Commit the project to Git.
3. Push to GitHub.
4. Connect the repository to the chosen static host, or upload the static folder manually if needed.
5. Connect the custom domain once the homepage and contact flow are ready.

### Deployment status

**Current status:** Static hosting is the direction, but the final host is not locked yet.
