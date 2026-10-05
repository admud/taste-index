# Landing Page Taste Checklist

> **A concrete, checkable rubric for what separates a beautiful landing page from a generic one.** Use it to review your own page, to brief a designer, or as the scoring rubric when you ask an AI to critique its own output ([critique prompt](prompts/04-critique.md)).

Each item is a yes/no check. "Taste" is mostly the sum of many small acts of restraint.

## Contents

- [The 10-second test](#the-10-second-test)
- [Typography](#typography)
- [Layout & spacing](#layout--spacing)
- [Colour](#colour)
- [Imagery & product visuals](#imagery--product-visuals)
- [Copy](#copy)
- [Hero section](#hero-section)
- [Social proof](#social-proof)
- [Motion & interaction](#motion--interaction)
- [Mobile](#mobile)
- [Technical polish](#technical-polish)
- [Signs of a generic AI-made page](#signs-of-a-generic-ai-made-page)
- [Scoring](#scoring)

## The 10-second test

Show the page to someone for 10 seconds, then close it. Can they say:

- [ ] **What it is**, in their own words?
- [ ] **Who it's for**?
- [ ] **What to do next** (the one primary action)?

If not, fix this first. Nothing else on the list matters until it passes.

## Typography

- [ ] **At most two typefaces** (often one family is enough). Use a display face only if it has character and you use it on purpose.
- [ ] **A clear type scale** with real jumps between sizes (e.g. 64 / 40 / 24 / 18 / 16). Avoid near-equal sizes like 18 vs 20.
- [ ] **Tight leading on headlines** (~1.0–1.15) and **relaxed leading on body text** (~1.5–1.7).
- [ ] **Slightly negative letter-spacing on large headlines.** Big type at default tracking looks loose.
- [ ] **Body lines are 50–75 characters long.** Full-width paragraphs are hard to read.
- [ ] **Hierarchy comes from size and weight, not colour.** Don't make headings purple to make them "stand out".
- [ ] **No widows on headlines** (a single word left alone on the last line). Use `text-wrap: balance`.

## Layout & spacing

- [ ] **A consistent spacing scale** (e.g. 4/8px base). No arbitrary 13px or 37px gaps.
- [ ] **Generous section padding.** Beautiful pages breathe: 96–160px between sections on desktop is normal.
- [ ] **A visible grid.** Edges line up across sections.
- [ ] **Sections vary in rhythm** (full-bleed, split, dense, sparse). Avoid twelve identical centred blocks.
- [ ] **One idea per section.** If a section needs two headlines, it should be two sections.
- [ ] **Alignment is deliberate.** Centre the hero if you like, but long text reads better left-aligned.

## Colour

- [ ] **A neutral base plus one accent colour.** The accent is reserved for the primary call to action and key highlights.
- [ ] **Neutrals are tinted, not pure #000 or #FFF.** Slightly warm or cool greys look expensive.
- [ ] **Text contrast meets WCAG AA** (4.5:1 for body text).
- [ ] **No more than one gradient idea**, and only if it means something for the brand.
- [ ] **Dark mode, if offered, is designed**, not just inverted.

## Imagery & product visuals

- [ ] **Real product UI is shown**, either in screenshots or in recreated UI built in code. This is the strongest single signal of a real product.
- [ ] **No stock photos** of people pointing at laptops, and no generic 3D blobs.
- [ ] **Screenshots are cropped to the point**, zoomed into the part that matters, not a whole tiny dashboard.
- [ ] **One consistent illustration and icon style** across the page.
- [ ] **Images are sharp on retina screens** and still load fast (AVIF/WebP, sized correctly).

## Copy

- [ ] **The headline is specific and ≤ ~10 words.** It says what the product does or what changes for the reader.
- [ ] **No filler verbs:** "supercharge", "unlock", "revolutionize", "elevate", "seamless", "next-generation", "empower".
- [ ] **The subhead adds information** (how it works, who it's for) rather than repeating the headline.
- [ ] **Feature copy states outcomes with specifics** ("Deploys in 40s", not "Blazing fast").
- [ ] **Button labels are verbs about the outcome** ("Start free trial", "Get the template"), not "Submit" or "Learn more".
- [ ] **The voice is consistent** from top to bottom.

## Hero section

- [ ] **One primary call to action** with a strong visual, and at most one secondary action with a weaker one.
- [ ] **The headline, subhead, CTA and product visual all show without scrolling** on a 1440×900 screen.
- [ ] **The visual explains the product**, not just decorates it.
- [ ] **Nothing competes with the headline** for attention.

## Social proof

- [ ] **Real logos, real names, real faces.** No placeholder testimonials.
- [ ] **Logos are greyscale or monochrome** in a single quiet row.
- [ ] **Testimonials are specific** ("cut our onboarding from 3 days to 4 hours") rather than generic praise.
- [ ] **Numbers are believable and sourced** where possible.

## Motion & interaction

- [ ] **Motion has a purpose**: it reveals hierarchy, shows how the product works, or confirms an action.
- [ ] **Duration is ~150–400ms with natural easing.** Nothing bounces for no reason.
- [ ] **`prefers-reduced-motion` is respected.**
- [ ] **No scroll-jacking** unless the page is a deliberate experiential piece.
- [ ] **Hover and focus states exist** on every interactive element.

## Mobile

- [ ] **It's designed for mobile, not just stacked.** The hero visual still works at 390px wide.
- [ ] **Tap targets are ≥ 44px.**
- [ ] **No horizontal scroll** at 360–430px widths.
- [ ] **Headline sizes are scaled down** (fluid type with `clamp()`), so headlines don't wrap one word per line.

## Technical polish

- [ ] **Largest Contentful Paint < 2.5s** and **Cumulative Layout Shift < 0.1** (Core Web Vitals).
- [ ] **Fonts don't cause layout shift** (`font-display`, size-adjusted fallbacks).
- [ ] **The favicon, social preview image and page title** are all set and on-brand.
- [ ] **Links are checked**, the footer is complete, and the legal pages exist.

## Signs of a generic AI-made page

AI-generated pages often fall into the same defaults. Each one isn't wrong on its own, but several together read as "made by AI, no taste applied":

- [ ] Purple-to-blue gradient hero on a dark background
- [ ] "Supercharge / Unlock / Elevate your workflow" headline
- [ ] Three identical feature cards, each with a rounded icon and a two-line blurb
- [ ] Glassmorphism or glowing borders on everything
- [ ] Emoji used as feature icons
- [ ] Every section centred with the same width and padding
- [ ] Placeholder testimonials ("Sarah J., CEO")
- [ ] A pricing table with three tiers where the middle one says "Most popular" by default
- [ ] One default sans-serif at a few similar sizes, with no real hierarchy
- [ ] Generic abstract 3D shapes instead of the product

**Score: 0–1 checked is fine. 3 or more means start again from references.**

## Scoring

To score a page:

| Section | Points |
|---|---|
| 10-second test | 3 (one per check; **must be 3/3**) |
| Typography, Layout, Colour, Imagery, Copy, Hero | 1 point per check passed |
| Social proof, Motion, Mobile, Technical | 1 point per check passed |
| Generic AI tells | −2 per tell |

Track the score across iterations rather than judging it in absolute terms. Each critique pass should raise it. Compare your score with one of your ★★★ references, scored the same way.

---

Part of **[Taste Index](README.md)**, a curated index of the best landing page inspiration galleries and design resources.
