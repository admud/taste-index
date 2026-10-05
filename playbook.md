# How to Make a Beautiful Landing Page (with or without AI)

> **A step-by-step playbook: start from curated references, turn them into a style spec, write the copy, build the page (by hand or with an AI coding tool), then review it against a taste checklist until it holds up next to the references.**

The core idea is that **taste comes in through references and goes out through review**. AI tools and templates produce generic pages because they start from nothing and nobody checks the result against a high bar. This playbook fixes both ends.

## Contents

1. [Define the page's job](#1-define-the-pages-job)
2. [Collect references by section](#2-collect-references-by-section)
3. [Extract a style spec](#3-extract-a-style-spec)
4. [Write the copy first](#4-write-the-copy-first)
5. [Build it](#5-build-it)
6. [Render, review, iterate](#6-render-review-iterate)
7. [Pre-launch checks](#7-pre-launch-checks)

**Time:** ~2–4 hours for a solid v1 with AI assistance.

## 1. Define the page's job

Before you look at anything pretty, write down four lines:

```text
Audience:      who lands here (e.g. "seed-stage founders evaluating analytics tools")
One job:       the single action we want (e.g. "start a free trial")
Core claim:    what changes for them, in one sentence
Proof:         the strongest evidence we have (customers, numbers, demo)
```

If you can't fill in **Proof**, the page will be weak however beautiful it is. Get proof first.

## 2. Collect references by section

Don't copy one site. **Pick the best example of each section** from the strict galleries in the [index](README.md#landing-page--website-galleries).

| Section | Where to look |
|---|---|
| Hero | [Godly](https://godly.website), [One Page Love](https://onepagelove.com), [Awwwards](https://www.awwwards.com/websites/) |
| Features / how it works | [Saaspo](https://saaspo.com), [Land-book](https://land-book.com) |
| Pricing | [Saaspo pricing pages](https://saaspo.com) |
| Social proof / logos | [Saaspo](https://saaspo.com), [DesignforB2B](https://www.designforb2b.com) |
| Components (tabs, accordions, nav) | [The Component Gallery](https://component.gallery), [Lapa Ninja Elements](https://www.lapa.ninja/elements/) |
| Industry-matched whole sites | [DesignforB2B](https://www.designforb2b.com) (filter by industry and funding stage), [Lapa Ninja](https://www.lapa.ninja) (categories) |

**Aim for 3–6 references in total**, with notes on *what* you're taking from each:

```text
refs/
  01-hero-linear.png        → type scale, tight headline, product shot bleeding off-edge
  02-features-vercel.png    → bento grid rhythm, monochrome icons
  03-pricing-raycast.png    → two tiers, toggle, restrained accent
  04-footer-stripe.png      → dense multi-column footer
```

Take full-page screenshots of the **live sites** yourself with [Playwright](https://playwright.dev):

```bash
npx playwright screenshot --full-page --viewport-size "1440, 900" https://example.com refs/01-desktop.png
npx playwright screenshot --full-page --device "iPhone 13" https://example.com refs/01-mobile.png
```

> **Rule:** references are for learning *principles* (scale, spacing, restraint, rhythm). Never copy a brand's distinctive layout, illustrations, copy or assets.

## 3. Extract a style spec

Turn the references into a short written spec of design tokens and rules. This is what keeps the build consistent, and it's the most important input for an AI tool.

Use the **[style extraction prompt](prompts/01-extract-style.md)** with your reference screenshots, or write it by hand:

```text
Type:     Display = Inter Tight 600, -2% tracking; Body = Inter 400/16/1.6
Scale:    72 / 48 / 28 / 20 / 16 / 14
Colour:   bg #FAFAF9, text #1C1917, muted #78716C, accent #EA580C (CTA only)
Spacing:  8px base; sections 128px desktop / 72px mobile; max width 1200px
Radius:   8px cards, 999px buttons
Imagery:  real product UI, cropped tight, soft 1px border, no drop shadows
Motion:   fade-up 300ms ease-out on scroll, once; respect reduced motion
Avoid:    gradients, emoji icons, centred body copy, more than 1 accent
```

## 4. Write the copy first

Design around real words, not lorem ipsum. Placeholder text hides the hierarchy problems that real copy exposes.

Use the **[copy prompt](prompts/05-copy.md)**, then cut it hard. For each section:

- **Headline:** specific, ≤ ~10 words
- **Subhead:** how it works or who it's for, in 1–2 lines
- **Body:** outcomes with numbers, no filler verbs (see the [checklist](taste-checklist.md#copy))

## 5. Build it

### Option A: by hand (Figma → code, or straight to code)

Build section by section against the style spec. Use a modern stack you know (Next.js / Astro + Tailwind is common) and put the spec's tokens in the Tailwind or CSS variables config first.

### Option B: with an AI coding tool (Claude Code, Cursor, v0, Lovable, Bolt…)

1. Give the tool the **style spec** (step 3), the **copy** (step 4) and **2–3 reference screenshots**.
2. Use the **[page generation prompt](prompts/02-generate-page.md)**. It tells the model to apply the *principles* in the references, not to copy their layout.
3. **Build one section at a time** with the [section prompt](prompts/03-generate-section.md) when a section isn't working. Regenerating the whole page tends to undo good parts.
4. Agents can also search curated design corpora directly. [Taste Labs](https://tastelabs.com) offers an MCP server that searches real sites by aesthetic.

## 6. Render, review, iterate

This loop is where the quality comes from.

1. **Screenshot your page** at desktop and mobile sizes, using the same Playwright commands as step 2.
2. **Put it next to your references.** Does it hold up? Be honest.
3. **Run the [critique prompt](prompts/04-critique.md)**, which scores the page against the [taste checklist](taste-checklist.md) and returns the top 3 fixes.
4. **Fix only those 3 things.** Re-screenshot and re-score.
5. **Stop when** the score stops rising, there are **0–1 [generic AI tells](taste-checklist.md#signs-of-a-generic-ai-made-page)** left, and the page passes the [10-second test](taste-checklist.md#the-10-second-test) with a real person.

Usually 3–5 loops is enough. If a page is still weak after 5, the problem is upstream: weak references, a vague job or missing proof.

## 7. Pre-launch checks

- [ ] [Taste checklist](taste-checklist.md) score is at least that of one ★★★ reference scored the same way
- [ ] Lighthouse: Performance ≥ 90, Accessibility ≥ 95 ([PageSpeed Insights](https://pagespeed.web.dev))
- [ ] Tested on a real phone, not just devtools
- [ ] Page title, meta description, social preview image and favicon are set
- [ ] Analytics and the primary CTA event fire correctly
- [ ] Shown to 3 people from the target audience, and they pass the 10-second test

---

Part of **[Taste Index](README.md)**, a curated index of the best landing page inspiration galleries and design resources.
