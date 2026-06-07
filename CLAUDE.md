# CLAUDE.md

Guidance for AI assistants working in this repository.

## What this repo is

A static marketing site for **The Freelancer's Command Center** — a paid Notion
template (CRM/project tracker for freelancers) sold on Gumroad. The repo is the
landing page + SEO blog that drives traffic to the Gumroad listing. There is no
build step, framework, package manager, or backend — just plain HTML files
deployed as-is via GitHub Pages.

## Repo structure

```
index.html      Landing/sales page (hero, mockup dashboard, testimonials,
                features, pricing, email capture, footer)
privacy.html    Privacy policy
terms.html      Terms of service
robots.txt      Points crawlers at sitemap.xml
sitemap.xml     Lists indexable pages with <lastmod> dates
DEPLOY.md       Step-by-step guide for hosting on GitHub Pages + sharing tips
blog/           SEO content marketing posts (one .html file per article)
```

There are no JS/CSS asset directories — every page is self-contained with
inline `<style>` blocks (and a small inline `<script>` in `index.html` for the
email capture form).

## Conventions

### Page structure
- Each HTML file is a complete standalone document with its own `<head>`,
  inline `<style>`, and (for `index.html`) inline `<script>`.
- `index.html` uses a dark theme defined via CSS custom properties in `:root`
  (`--bg`, `--accent`, `--text`, etc.). Reuse these variables rather than
  hardcoding new colors when editing that page.
- Blog posts use a simpler light theme (`color: #333`, accent `#0052cc`) with
  a shared layout: breadcrumb (`Home > Blog > Post Title`) → `<h1>` → article
  body → `.cta-box` promoting the product.

### SEO / metadata
- Every page sets `<title>` and `<meta name="description">`. Match the tone
  and keyword focus of existing posts when adding new ones (benefit-driven,
  includes the target audience, e.g. "freelance photographer", "ADHD student").
- When adding or changing a page that should be indexed, update `sitemap.xml`
  (add a `<url>` entry with `<loc>` and `<lastmod>` in `YYYY-MM-DD` format)
  and ensure `robots.txt` still points at it.
- `og:title` / `og:description` meta tags exist on `index.html` for social
  sharing previews — keep them in sync with the `<title>`/description if you
  change the core pitch.

### Links and placeholders
- The Gumroad product link `https://gumroad.com/l/freelancer-command-center`
  and contact address `hello@freelancercommandcenter.com` are already live —
  use them as-is for new CTAs.
- A few **unresolved placeholders** remain in the codebase — don't treat them
  as real values, and flag/replace them if you touch nearby code:
  - `blog/best-notion-templates-for-freelancers.html` — `YOUR_GUMROAD_LINK_HERE`
  - `index.html` — `formspree.io/f/YOUR_FORM_ID` and the commented-out
    ConvertKit (`YOUR_FORM_ID`) integration for the email capture form
  - `robots.txt` / `sitemap.xml` / `DEPLOY.md` — `YOUR_USERNAME` references
    (the GitHub Pages URL pattern)
- All internal navigation uses root-relative paths (`/`, `/blog`, `/privacy.html`).

### Pricing / copy consistency
- The advertised price appears in multiple places (`index.html` nav CTA, hero,
  pricing section, and several blog CTAs). If the price changes, search for
  all occurrences (`$12`, `$19`, "Launch price") and update them together —
  there's no single source of truth to edit.

## Working in this repo

- **No build/test/lint tooling exists.** Changes are plain HTML/CSS/JS edits;
  "testing" means opening the file in a browser (or `python3 -m http.server`
  from the repo root) and checking it visually/functionally.
- Keep edits self-contained per file — don't introduce shared CSS/JS files or
  a build pipeline unless explicitly asked; the simplicity is intentional for
  free GitHub Pages hosting (see `DEPLOY.md`).
- Match existing formatting (2-space indentation, inline styles) rather than
  reformatting whole files.
- Blog posts follow a content-marketing pattern: hook → problem → product
  pitch (with a `.cta-box`/`cta-button` linking to Gumroad or `/`) → FAQ-style
  closing. New posts should follow this same arc and include a breadcrumb back
  to `/` and `/blog`.

## Git history note

Many commits are titled "Autonomous update: Added ... professional assets" —
these are prior automated content-generation passes that added new blog posts.
Follow the same commit-message style (concise, descriptive of what content/page
was added or changed) when committing similar content additions.
