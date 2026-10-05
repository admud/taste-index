# Prompt 02: Generate the full landing page

**Use when:** you have a style spec ([prompt 01](01-extract-style.md)) and real copy ([prompt 05](05-copy.md)).

**Attach:** 2–3 reference screenshots (the strongest ones).

```text
Build a production-quality landing page.

STACK: {{e.g. Next.js App Router + Tailwind CSS | single self-contained HTML file with inline CSS}}

STYLE SPEC (follow exactly — these are constraints, not suggestions):
{{STYLE_SPEC}}

COPY (use verbatim; do not invent extra claims, testimonials, logos or numbers):
{{COPY}}

REFERENCES: the attached screenshots show the quality bar. Apply their PRINCIPLES —
type scale, spacing, restraint, section rhythm, how the product is shown. Do NOT copy
their layout, brand, illustrations or copy.

Requirements:
- Hero: headline, subhead, one primary CTA (+ max one secondary, visually weaker),
  and a product visual, all above the fold at 1440×900.
- Show the product with realistic UI recreated in HTML/CSS (not a grey placeholder box,
  not stock images, not abstract blobs). Use plausible data relevant to the product.
- Vary section rhythm; do not centre every section at the same width.
- Responsive: designed for 390px wide, not just stacked; fluid headline sizes with clamp().
- Accessibility: semantic HTML, AA contrast, visible focus states, alt text,
  prefers-reduced-motion respected.
- Performance: no heavy libraries for simple effects; system or Google fonts with
  font-display: swap.

Hard bans (these make pages look generic):
- purple/blue gradient hero backgrounds, glassmorphism, glowing borders
- emoji as icons
- "supercharge / unlock / elevate / revolutionize / seamless" or any copy not provided
- three identical icon feature cards
- fake testimonials or placeholder logos

Before writing code, list in 5 bullets the key design decisions you're taking from the
references. Then output the complete code.
```

**Next:** screenshot the result and run [prompt 04](04-critique.md). Fix weak sections with [prompt 03](03-generate-section.md).
