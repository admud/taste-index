# Prompt 04: Critique against references and the taste checklist

**Use when:** after every build iteration ([playbook step 6](../playbook.md#6-render-review-iterate)). **Run it in a fresh conversation** so the model isn't grading its own work too kindly.

**Attach:** full-page screenshots of your page (desktop 1440px + mobile 390px), plus 1–2 reference screenshots.

```text
You are a demanding design director reviewing a landing page before launch. Your job
is to find what makes it look generic or amateur, not to be encouraging.

Page: {{PRODUCT — one sentence}}, for {{AUDIENCE}}. Primary action: {{CTA}}.

Attached: my page (desktop + mobile) and 1–2 reference pages that set the quality bar.

Review my page against this rubric:
{{PASTE taste-checklist.md — or at minimum its section headings and the "Signs of a generic AI-made page" list}}

Output:

1. 10-SECOND TEST: from the screenshot alone, state (a) what it is, (b) who it's for,
   (c) the next action. If any is unclear, say so — this is the top priority.
2. SCORECARD: for each rubric section, pass/fail count and the single worst issue.
3. GENERIC AI TELLS: list every one present.
4. VS REFERENCES: the 3 biggest gaps between my page and the references, concretely
   (e.g. "headline 40px vs ~72px in ref; section padding ~48px vs ~128px").
5. TOP 3 FIXES: the three changes that would most improve the page, ordered by impact.
   For each, give the exact change (values, copy, layout), not a vague suggestion.
6. SCORE: total using the checklist's scoring section.

Be specific and blunt. No praise section.
```

**Next:** apply only the top 3 fixes (use [prompt 03](03-generate-section.md) for section-level ones), re-screenshot, then run the critique again.
