# Ardonio Site

Hugo static site for Ardonio Ltd. — Klaas Ardinois's consulting business.

## Purpose
Simple consulting website with three goals:
1. Quick booking link (cal.com/klaas-ardinois/30min)
2. Brief "about" and "services" pages
3. Blog posts / thought leadership

## Stack
- **Hugo** static site generator
- **hugocoder** theme (custom fork at `themes/hugocoder/`, tracked as git submodule)
- Deployed via GitHub Actions (`.github/workflows/hugo.yaml`)
- GA4 tracking: G-TP6K8JELXS

## Key files
- `hugo.toml` — all site config: nav, social links, params
- `content/about.md` — Klaas's story page ("The Story")
- `content/services.md` — services/offerings page
- `content/posts/` — blog posts (Markdown)
- `static/images/avatar.jpg` — profile photo
- `themes/hugocoder/` — theme (modify here for layout/style changes)
- `themes/hugocoder/assets/scss/` — styles
- `themes/hugocoder/layouts/` — templates

## Local dev
```bash
hugo server -D        # serve with drafts
hugo                  # build to public/
```

## Content structure
- `about.md` and `services.md` are top-level pages (no title in frontmatter — title is set via H1 in body)
- Posts live in `content/posts/` with standard Hugo frontmatter
- Navigation menu defined in `hugo.toml` under `[[menu.main]]`
- Social/CTA icons defined under `[[params.social]]`

## Theme customisation
The `themes/hugocoder` directory is a custom fork (not the upstream hugo-coder). Override theme templates by placing files in the project-level `layouts/` directory (currently empty — all layout is in the theme). Override styles via `assets/scss/custom.scss` (uncomment `customSCSS` in `hugo.toml`).

## Design intent
Keep it minimal. No fancy features. The site should load fast and get visitors to either book a call or read a post.
