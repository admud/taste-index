# Prompt 01: Extract a style spec from reference screenshots

**Use when:** you've collected 2–6 reference screenshots ([playbook step 2](../playbook.md#2-collect-references-by-section)) and want a consistent design system to build from.

**Attach:** the reference screenshots, each labelled with what you're taking from it.

```text
You are a senior product designer with excellent taste.

I'm designing a landing page for {{PRODUCT — one sentence}} aimed at {{AUDIENCE}}.
Attached are reference screenshots. For each one, here is what I want to take from it:
{{e.g.
- ref 1: hero type scale and tight headline
- ref 2: features grid rhythm
- ref 3: pricing restraint, single accent colour}}

Study the references and write a STYLE SPEC that combines these qualities into one
coherent system for MY brand. Don't describe the references; write rules I can build from.

Output exactly these sections, with concrete values (px, hex, weights, ms):

1. Typography: typefaces (suggest freely available ones, e.g. Google Fonts), weights,
   type scale (6–7 sizes), line-heights, letter-spacing for display vs body.
2. Colour: background, surface, text, muted text, border, ONE accent (and where the
   accent is allowed). Tinted neutrals, not pure black/white. Check text contrast against WCAG AA.
3. Spacing & layout: base unit, section padding desktop/mobile, max content width,
   grid columns, how alignment works.
4. Shape: border radius, borders vs shadows, card style.
5. Imagery: how product UI/screenshots are shown, cropping, framing, what's banned.
6. Motion: what animates, duration, easing, reduced-motion behaviour.
7. Section rhythm: the order of sections and how each varies (full-bleed, split, dense, sparse).
8. Avoid list: 6–10 specific things this design must NOT do.
9. CSS variables: the tokens above as a :root { } block, ready to paste.

Keep the whole spec under 400 words plus the CSS block. Be decisive: one choice per
decision, no "or".
```

**Next:** paste the output into [prompt 02](02-generate-page.md) as `{{STYLE_SPEC}}`.
