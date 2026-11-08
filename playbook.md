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

### Match the reference to the job

[Aman Singh's UI/UX resource roundup](https://x.com/amananimates/status/2119127905666314632) (8 November 2026) is a useful starting kit when you know which part of a page needs work. It links five different kinds of resource, rather than five interchangeable whole-site galleries:

| Resource | What to study | Access and scope |
|---|---|---|
| [Scrolltide](https://www.scrolltide.co/) | Scroll-driven templates, prompts and individual components | Free and premium items; [plan restrictions](https://www.scrolltide.co/pricing) apply to 3D and other collections |
| [Scroll Shaders](https://scrollshaders.com/) | WebGL backgrounds and shader components, with React/HTML and video formats | Public previews; code and downloads require a paid plan |
| [Footer Design](https://www.footer.design/) | Footer hierarchy, link grouping and how a page ends; browse by type and style | Publicly browsable footer gallery with links to the original sites |
| [CTA.gallery](https://www.cta.gallery/) | Calls to action by purpose, including forms, newsletters, downloads and pricing | Publicly browsable inspiration; screenshots do not prove conversion performance |
| [Refero Styles](https://styles.refero.design/) | Product-site design systems: colours, typography, spacing, components and DESIGN.md references | Public style browsing; check the individual resource's access and reuse terms |

**Apply the roundup:** these are our working principles, not claims that the post demonstrates a complete design process.

1. **Name the gap first.** Choose a footer reference for navigation and closure, a CTA reference for the next action, a style reference for consistency, or a motion reference for a specific visual effect.
2. **Extract one useful decision.** Write down the hierarchy, spacing rule or interaction you want to improve. Translate it into your own style spec instead of importing unrelated visual systems from every library.
3. **Protect the page's job.** Keep the primary action and text clear. Use shaders and 3D only when they support the message; test contrast, mobile performance and a reduced-motion or static fallback before shipping.
4. **Check the live implementation.** A gallery image is inspiration, not evidence of responsive behaviour, accessibility or conversion gains. Visit the original site and test the relevant states.

The post text, a visible frame of its component-demo video and the linked sites were reviewed on 8 November 2026. No timing or performance claims are inferred from the clip. Library counts are omitted because the post and current site catalogues differ. The author's X profile identifies him as Scrolltide's co-founder, so treat the list as a creator's recommendations, not an independent ranking. Linked screenshots, prompts and code retain their owners' terms; this repository's CC0 license does not cover them.

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

### App UI and motion workflow

[Breeje Anadkat's app-building thread](https://x.com/BreejeAnadkat/status/2119040284088787421) (7 November 2026) is a useful companion to this playbook when a page includes interactive product UI or the work extends into an app.

The thread describes repeated refinement with UI and motion references. The [visual comparison example](https://x.com/BreejeAnadkat/status/2119041908312003042) shows specific corrections to text, a gauge and corner radii. For harder animations, the author [draws two or three states in Figma](https://x.com/BreejeAnadkat/status/2119042314849202236); the image shows a swipe control at successive positions. The final step is [testing the app directly](https://x.com/BreejeAnadkat/status/2119042592411377801), because a transition can look convincing in a clip but feel slow to use.

**Apply the method:**

1. Choose one interaction with a clear user outcome. Gather a still reference for hierarchy and a motion reference for behaviour.
2. Sketch its starting, intermediate and final states. Specify the trigger, timing, what changes and what stays anchored.
3. Build a small working version, then compare matching screenshots side by side. Request concrete changes to spacing, type, colour and component shape.
4. Tap through the actual flow. Try repeated input, cancellation and returning to the previous screen. Fix delays and lost state before adding decoration.

These application checks extend the source: keep keyboard and tap alternatives for gestures, respect reduced motion, and make confirmation understandable without animation. Do not make urgent actions wait for a transition. Borrow the process while retaining the product's own visual language and accessibility requirements.

The linked post and its comparison and state images were reviewed on 8 November 2026. Creator media remains at its source; this entry does not grant reuse rights.

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
