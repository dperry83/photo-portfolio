# Photography Website README

This document is the starting record for the new photography website build.

The goal is to build a simple, clear, on-brand website for a founder-focused photography business, using a stack that is enjoyable to build with now and flexible enough to grow later. The current plan is to start with a beautiful static site first, then add more structure only when it becomes useful.[cite:19][cite:21]

## Project goal

Build a founder-focused photography website that:

- Feels credible, clear, and low-drama
- Starts as a static marketing site
- Is built in a way that can grow later
- Leaves room for future custom backend features such as client galleries or image selection tools[cite:19]

## Decisions made

### Frontend framework

**Decision:** Use **Nuxt**.

**Why:** Vue.js is already the most familiar frontend tool for this project, and Nuxt adds the website-level structure that makes page-based sites easier to build and maintain. Nuxt provides file-based routing, built-in SEO/meta support, and static deployment options that fit a photography business site well.[cite:63][cite:20][cite:50][cite:55][cite:23]

**Decision timing:** Decided now, before build begins.

### Styling approach

**Decision:** Use **Tailwind CSS** plus a small custom design system layer.

**Why:** Tailwind speeds up layout, spacing, typography, and responsive styling, while still allowing a custom visual system. The plan is not to rely on raw utility classes everywhere, but to pair Tailwind with brand tokens and a few reusable components so the site stays clean and does not feel generic.[cite:64][cite:33][cite:71]

**Decision timing:** Decided now, before UI build begins.

### Version 1 scope

**Decision:** Start with a **beautiful static website**.

**Why:** This keeps version one focused on the public-facing marketing site instead of turning it into a larger software project too early. The public site should do the main job first: communicate credibility, show the work, and convert the right visitors into inquiries.[cite:19][cite:21]

**Decision timing:** Decided now.

### Content management for version 1

**Decision:** **No CMS in version 1.**

**Why:** The content model is intentionally being deferred. Version one will use hardcoded content or simple local content files until a more formal content workflow becomes necessary.[cite:19]

**Decision timing:** Decided now.


### Sitemap and navigation

**Decision:** Version 1 sitemap is **Home, Work, About, Services, FAQ, Contact** with primary navigation of **Work, Services, About, FAQ, Contact**.

**Why:** This keeps the site small, clear, and aligned with the founder buyer journey. Each page has a distinct job, and the navigation supports a low-friction path toward inquiry.

**Decision timing:** Decided now, before wireframing and page planning.

### Design direction

**Decision:** The visual tone for version 1 is **credible, calm, modern, human, clear, and low-drama**.

**Why:** The site needs to feel like a trusted business tool with taste. It should avoid both generic corporate stiffness and over-styled photography-portfolio clichés.

**Decision timing:** Decided now, before visual design and component work.

## Working assumptions

These are current assumptions, not permanent commitments:

- The site should stay simple and easy to reason about.
- The first version should prioritize clear messaging, portfolio presentation, and inquiry flow.
- The stack should support future expansion without forcing that expansion into version one.
- Future app-like features, if built, should be treated separately from the public marketing site architecture where possible.[cite:19][cite:21]

## Decisions still to make

### Hosting platform

**Status:** Not decided yet.

**Current shortlist:**

- Vercel
- Netlify

**When to decide:** Before the first deploy preview is set up.

**What will drive the choice:** Simplicity, deployment workflow, preview deploy experience, and whether one feels more natural with the Nuxt setup.[cite:23]

### Initial content structure

**Status:** Not decided yet.

**Question:** Should version one use fully hardcoded content in components, or local content files for easier editing?

**When to decide:** During early implementation, before page build gets too far.

**What will drive the choice:** How often content is expected to change during the first build, and whether lightweight editing flexibility is worth the extra setup.

### Nuxt Content in version 1 or 1.5

**Status:** Not decided yet.

**Question:** Should local content remain simple, or should Nuxt Content be added once the pages start to multiply?

**When to decide:** After the first pass of the core marketing pages is complete.

**What will drive the choice:** Whether content editing becomes annoying enough to justify adding structure.[cite:24][cite:67]

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

**What will drive the choice:** Whether there is a real business workflow problem worth solving with custom software.[cite:19]

## Current implementation phases

### Phase 1: Foundation

- Confirm stack
- Confirm sitemap and navigation
- Confirm design direction
- Define basic design system
- Set up Nuxt project
- Set up Tailwind and custom tokens

### Phase 2: Static marketing site

- Build homepage
- Build portfolio/work page
- Build about page
- Build services page
- Build FAQ/contact flow
- Refine SEO basics and performance

### Phase 3: Content structure

- Decide whether local content files are enough
- Add Nuxt Content only if it solves a clear problem
- Revisit editorial/case-study structure if needed

### Phase 4: Future expansion

- Revisit CMS options
- Revisit backend architecture
- Consider gallery and client workflow tools

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

- **Nuxt** for the frontend framework
- **Tailwind CSS** for styling
- **A small custom design system layer** for brand feel
- **A static version 1 site** with no CMS and no backend
- **A later review** for hosting, content tooling, CMS, and client gallery features[cite:23][cite:33][cite:19]



## Recommended folder structure

The recommended version 1 repo structure is:

```txt
photography-site/
├── README.md
├── docs/
│   ├── sitemap.md
│   └── design-direction.md
├── nuxt.config.ts
├── package.json
├── app/
│   ├── app.vue
│   ├── pages/
│   │   ├── index.vue
│   │   ├── work.vue
│   │   ├── about.vue
│   │   ├── services.vue
│   │   ├── faq.vue
│   │   └── contact.vue
│   ├── components/
│   │   ├── site/
│   │   ├── home/
│   │   ├── work/
│   │   ├── about/
│   │   ├── services/
│   │   ├── faq/
│   │   └── shared/
│   ├── layouts/
│   │   └── default.vue
│   ├── assets/
│   │   ├── css/
│   │   └── images/
│   └── composables/
├── public/
│   ├── favicon.ico
│   └── og/
├── content/   (optional later)
└── server/    (later, if needed)
```

### Why this structure

This structure follows Nuxt's directory conventions while keeping version 1 simple. Nuxt uses `app/pages/` for file-based routing, `components/` for Vue components, `assets/` for processed assets, `public/` for files served as-is, and `server/` for API and server handlers if they are needed later.[cite:53][cite:89][cite:77]

A few project-specific rules go with this structure:

- Keep documentation in `docs/` once the repo exists.
- Keep page-specific components grouped by page until there is a strong reason to abstract more.
- Do not add `content/` until local structured content is actually useful.
- Do not add `server/` code in version 1 unless a real feature requires it.[cite:19]

## Deployment setup

### Recommended default

The current recommended default hosting setup is:

- GitHub for version control
- Vercel for hosting and preview deploys
- `main` as the production branch[cite:78]

### Why Vercel is the current default

Nuxt's Vercel deployment guide describes a zero-configuration deployment flow: push to a Git repository, import the project into Vercel, and Vercel detects Nitro and applies the correct settings. It also creates Preview Deployments for subsequent branch pushes and production deployments from the production branch.[cite:78]

### Version 1 deployment flow

1. Create the Nuxt project locally.
2. Commit the project to Git.
3. Push to GitHub.
4. Import the repository into Vercel.
5. Let Vercel create preview deploys while the site is being built.
6. Connect the custom domain once the homepage and contact flow are ready.[cite:78]

### Deployment status

**Current status:** Vercel is the recommended default, but not yet treated as irreversible.

If a good reason appears to prefer Netlify later, that can still change. For now, Vercel is the simplest recommended path for this project.[cite:78]
