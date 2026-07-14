# Ardonio Ltd. Brand Styleguide

> Use this guide when creating the website, documents, presentations, or any other materials for Ardonio Ltd.

---

## Writing rules (hard)

These are non-negotiable.

- **Never use em dashes (`—`).** They now read as "written by AI," and the brand is boutique, not generic slop. Use a period, comma, colon, or parentheses instead. Restructure the sentence rather than reaching for a dash. (En dashes in number ranges, like `2008–12`, are fine and correct.)
- **American spelling.** The audience is American. Write "organization", "judgment", "canceled", "smolder", "analyze", not "organisation", "judgement", "cancelled", "smoulder", "analyse". Don't make a reader stumble over a word they'd mark as a typo.
- **Spell out numbers below ten.** "three outcomes", "a day or two", not "3 outcomes". Ten and above take numerals ("a 20-second load time"). Three exceptions keep the numeral below ten: **units** (`$5m`, `5%`, `3km`), **decimals** (`2.5x`), and **time references** (`the 90s`, `Q3`).
- **Sentence case in copy.** Not Title Case. (Proper nouns and the wordmark aside.)
- **No superlatives without evidence** ("world-class", "leading", "best").
- **Say the thing once.** No long preambles before the point.

---

## Identity

**Company:** Ardonio Ltd.  
**Person:** Klaas Ardinois  
**Positioning:** *A hands-on technology operator for transformation and turnaround in the mid-market.*  
**Contact:** klaas@ardonio.com  
**Booking:** cal.com/klaas-ardinois/30min  
**Website:** ardonio.com

---

## Positioning: the north star

The guiding concept (internal) is the **corporate fixer**: the operator a CEO, board, or PE partner reaches for when the business is in a difficult, disruptive, or high-stakes situation and the usual playbook has run out. The reference points are **Winston Wolf** and **James Bond**: quietly competent, unhurried, obviously experienced. They never announce it. The room already knows.

**Public-facing language is the professional register of that concept** (*transformation, turnaround, value creation*), **not** the word "fixer." Let the substance imply the rest.

**The specialism is the situations without an obvious playbook:**
- Growth has stalled, and the reasons aren't clear
- Cash burning without a clear path to return
- A value-creation plan that isn't landing
- Attrition in the teams you can't afford to lose
- Engineering that can't reliably ship
- An executive team pulling in different directions

---

## Voice & Tone

A seasoned operator who has been in the room when the hard decisions were made. **Professional above all.** Confidence is *earned and implied*, never performed. It's simply not a discussion point, confidence and competence are just quietly present as a fact of life. Earned, not spelled out. 

**Key characteristics:**
- **Show, don't tell.** The experience is obvious through the specifics and the outcomes, never through adjectives about yourself. Bond doesn't tell you he's the best. The results do.
- **Plain and direct.** No jargon, no corporate filler. Say the thing, once.
- **Earned confidence.** Every claim is backed by a real outcome (revenue, exit multiple, share-price move, named situation). Vague gets cut.
- **Calm, not cute.** No gimmicks, no slogans, no jokes-as-strategy. A dry last line is welcome. A wink is not.
- **Practitioner, not pundit.** Opinions come from doing.

**The ROI rule: point "expensive" at the situation, never at the client.**  
Frame cost around the decision, the stakes, or the situation, not the reader's competence. Telling a prospect they'd "make expensive mistakes" tells them they're incompetent, which is a weak sales line even when true. The situation is the enemy. You're on their side against it.
> ✅ *"When the decision is expensive, an experienced hand is cheap."*  
> ❌ *"Working with me is cheaper than the mistakes I'll help you avoid."*

**Headline style: a quiet truth, stated once.**
> *"When the decision is expensive, an experienced hand is cheap."*  
> *"Built, scaled, acquired, divested, exited."*  
> *"Built for the situations without an obvious playbook."*  
> *"I can't name names, but I can list results."*

**Depth lives in long-form.** The proof of "been there, unflappable" cannot be bullet-pointed and must never be bragged. It belongs in anonymized accounts (the **"Tales from an operator"** format), told flat and first-person, with the *pattern recognition* as the payload, not the heroics. They let a reader recognize their own situation. They never cast Klaas as the hero.

**Avoid:**
- Superlatives without evidence
- Passive voice; long preambles; buzzword stacking
- Anything that reads as trying-too-hard, cute, or self-congratulatory

---

## Content architecture

Two classes of writing, and no more. The test for a separate section is not "different topic" but "different job and different rules." Only one class passes it, so the site stays simple.

**1. Tales get their own top-level nav.**
"Tales from an operator" sit at the same level as The Story and Services in the main navigation. They keep the tone and function set out in Voice & Tone: anonymized, flat, first person, pattern recognition as the payload, never Klaas as the hero. They are the referral substitute and a separate body of proof from the named record, so they must never link back to it. The working list and rules live under "Tales from an operator" in `ideas.md`.

**2. Everything else sits in one stream.**
All other writing shares a single stream (currently "posts" / "Latest Thoughts"). Operating guides, frameworks, and timely commentary are not split into separate sections. They do the same job (show how Klaas thinks, in his own name, freely linkable) and differ only in shelf-life, which does not earn a wall.

**Cornerstone guides are featured, not filed.**
The evergreen operating-model pieces (for example The 4 Stages of a CTO, the engineering-measurement framework) are the SEO and credibility hubs. They earn prominence through structure inside the stream, not a section of their own:
- Hub posts link to their related spoke posts, and the spokes link back. This hub-and-spoke linking is the underlying SEO structure.
- Tag each hub with a category (working name `playbook`) so the cornerstones can be recalled and curated later (for example a "Start here" list) without adding navigation.

Resulting nav: Home · Services · The Story · Latest Thoughts · Tales.

---

## SEO checklist

Every new post follows this. The theme already handles the plumbing (OpenGraph, Twitter cards, canonical tag, sitemap, RSS), so these are the content-side rules that need human attention.

### Required frontmatter
- **`title`**: the primary topic near the front, under about 60 characters so search results do not truncate it.
- **`description`**: hand-written, 140 to 160 characters. This is the search snippet and the social-card text. Never leave it blank. A blank description falls back to an auto-generated summary, which reads like a cut-off intro.
- **`slug`**: short, keyword-led, lowercase, hyphenated. Set it on publish and never change it afterwards. If a slug ever has to change, add the old path to `aliases` so the old URL redirects instead of 404ing.
- **`date`** and **`authors`**: always set.

### Structure
- **One H1 per page.** The theme renders the title as the H1, so body section headings start at `##`, never `#`. Subsections go `###`.
- **Front-load the answer.** State the topic in the first two sentences. This is the same instinct as the "say the thing once" writing rule.
- **One post, one primary query.** Do not publish two posts chasing the same phrase.

### Internal links (the hub-and-spoke)
- Link with Hugo's `{{< relref "target.md" >}}` shortcode, not raw `../slug/` paths. `relref` resolves at build time and fails the build if the target moves, instead of shipping a silent broken link.
- Anchor text is the target's topic (for example "the four stages of a CTO"), never "here" or "this post".
- Every post links up to its hub; each hub links down to its spokes. Tag hubs with the `playbook` category.

### Images
- Every image needs descriptive `alt` text.
- Give posts a share image (a default brand image at minimum) so social cards are not blank.

### Tags and categories
- Reserve `playbook` for cornerstone hubs. Use categories only for real groupings (for example `podcasts`). Avoid tag sprawl: thin taxonomy pages hurt more than they help. Empty `tags` is fine.

### Site-level (one-time, not per post)
- JSON-LD structured data: `Article` on posts, `Person` / `Organization` on About, `BreadcrumbList`. A theme partial, still to add.
- A `static/robots.txt` pointing at the generated sitemap.

---

## Color Palette

| Name | Hex | Usage |
|------|-----|-------|
| **Ink** | `#111214` | Headings, strong emphasis |
| **Blue** | `#1E5BFF` | Primary accent: links, CTAs, highlights, the mark, blockquote borders, list markers |
| **Gray Dark** | `#5A5D63` | Body text |
| **Gray** | `#8A8D93` | Secondary / meta text |
| **Hair** | `#E8E9EB` | Borders, dividers, background tints |
| **Paper** | `#FFFFFF` | Page background |
| **Surface** | `#F1F2F4` | Subtle card / code backgrounds |

**Primary brand color: Blue `#1E5BFF`.** Use it sparingly: one key element per slide or page (a mono label, a CTA, the mark, a highlighted data point). Overuse dilutes impact.

---

## The mark

- **Primary mark:** a **solid Blue `#1E5BFF` square** paired with **ARDONIO LTD.** in uppercase (Inter 500, letter-spaced). Small and confident. The square sits about 9px beside the wordmark in the site nav.
- **Favicon / app icon:** the same square with **rounded** corners. Rounding is an app-icon convention (the OS expects it), and is the **only** place the square is rounded.
- **Everywhere else the square is sharp.** It also recurs as a **list marker** (for example the "Where I come in" grid). The blue square is the one repeating graphic motif. Reach for it before an icon.

---

## Typography

### Typefaces

| Role | Font | Fallback |
|------|------|----------|
| **Primary (headings & body)** | Inter | -apple-system, Segoe UI, Roboto, Helvetica Neue, sans-serif |
| **Monospace / labels / code** | JetBrains Mono | SFMono-Regular, Consolas, Menlo, monospace |

Inter and JetBrains Mono are free Google Fonts.

### Signature device: the mono label

Small **JetBrains Mono**, uppercase, letter-spaced (about 0.08em), in Blue. Used for eyebrows, section labels, dates, counts, and meta ("WHERE I COME IN", "FILED UNDER", "05 formats", "12 MAR 2026"). This is a load-bearing brand device. Use it in place of an icon.

### Type scale (web reference, scale proportionally for print/slides)

| Level | Size | Weight | Notes |
|-------|------|--------|-------|
| Hero name | clamp 40–64px | 500 | Tight tracking (−0.03em) |
| H1 / Slide title | 32px | 500 | Tracking −0.03em |
| Section title | 30px | 500 | Tracking −0.02em |
| H2 / heading | 22px | 500 | Tracking −0.02em |
| Body | ~16–17px | 400 | Line height 1.6, tracking −0.01em |
| Small / meta | 12–14px | 400/500 | Mono label or Gray `#8A8D93` |
| Strong / bold | any | **700** | Sparingly, for emphasis |

---

## Layout Principles

- **White space is a feature.** Wide margins, generous spacing. Never crowd content.
- **Widths:** about 1040px for full-width chrome (nav, footer, section bands); about 760px for reading columns. In documents, keep text to roughly 65 to 75 characters wide.
- **Left-aligned text.** No centring of body copy. Centring is for the hero only.
- **Sharp corners.** The whole system is square-edged: buttons, CTAs, chips, cards, dividers, borders. The **only** rounded element is the favicon / app icon. Keep corners sharp in decks and docs.
- **Hairline rules do the dividing.** Thin `#E8E9EB` lines separate sections, list rows, and table rows, rather than boxes or shading.

---

## Iconography: minimal by default

The brand is deliberately **icon-light.** Prefer a **mono text label** over an icon (the site replaced Font Awesome folder/tag/social icons with labels like "FILED UNDER" and "TAGGED"). The recurring graphic motif is the blue square, not an icon set.

If icons are unavoidable in a deck:
- Sparse, line-style, in Ink or Blue
- Never decorative. Only where they carry real information
- Sized to text (1x to 1.5x cap height)

---

## Slide / Document Structure

### Cover / Title
- Company name: **Ardonio Ltd.** (with the blue square mark)
- Subject line in large Inter 500
- Context / date line as a mono label (Blue or Gray)

### Section divider
- Bold heading in Ink `#111214`
- A mono label above it, or a thin Blue left-border accent
- Minimal decoration, sharp corners

### Content slides / pages
- **One idea per slide.** Two ideas mean two slides.
- Lead with the *so what*. Conclusion at the top, evidence below.
- Short sentences beat nested bullets. Prefer one strong quote or stat over three mediocre bullets.

### Pull quotes / callouts
- Thin Blue `#1E5BFF` left border (sharp corners, no rounding on single-sided borders)
- Slightly larger text (1.1x to 1.2x body), weight 500
- For key insights or memorable phrases

---

## Photography & Imagery

- **Profile photo:** Klaas Ardinois headshot (`avatar.jpg`), professional and approachable, on a light background. On the site it sits as a circle in the hero.
- **Style:** Clean, light-background imagery. No stock-photo clichés (handshakes, lightbulbs, arrows going up).
- **Charts / data:** Simple, high-contrast, brand palette. Label directly and avoid separate legends.

---

## Services (quick reference for decks)

Order deliberately leads with turnaround/interim and closes with coaching.

| Service | Format |
|---------|--------|
| Interim & turnaround | Project-based |
| Problem solving session | 90 min · 1 problem |
| Strategy alignment workshop | Half or full day |
| Advisory retainer | Ongoing |
| CTO coaching | 6-month program |

---

## Key Messages by Audience

### For PE / investors
> *"Value creation at the core of driving growth through technology."*  
Focus: buy- and sell-side diligence, the value-creation plan when it isn't landing, cash-burn / ROI, technology restructuring, wrong-operator risk.

### For founders (CEO/CTO)
> *"Every CTO has a different path to becoming a business leader."*  
Focus: the founder-CTO ceiling, structure and process, decisions framed in commercial terms.

### General positioning
- Techie with a business brain. Quietly confident.
- People, process, technology, in that order
- The operator for difficult, disruptive, transformation situations
- Sector expertise: EdTech, media, telco
- Outcome-oriented: exits, take-private, share-price growth, revenue milestones

---

## What to avoid

- Em dashes (see Writing rules)
- British spelling, and bare numerals below ten (see Writing rules)
- Gimmicks, slogans, jokes-as-strategy, or anything trying too hard
- Copy that implies the client is incompetent (point cost at the situation, not at them)
- Dark backgrounds (the brand is light / paper; dark only for a deliberate contrast moment)
- Multiple accent colors (Blue is the only accent)
- Rounded corners anywhere except the favicon
- Decorative fonts, script typefaces, decorative icons
- Dense slides with small text; jargon that obscures the outcome

---

*Last updated: July 2026*
