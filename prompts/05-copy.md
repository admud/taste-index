# Prompt 05: Write landing page copy

**Use when:** before designing ([playbook step 4](../playbook.md#4-write-the-copy-first)). Real copy reveals hierarchy problems that lorem ipsum hides.

```text
Write landing page copy. Be specific, plain and confident. Write like the best
product companies, not like an ad agency.

FACTS (only use these; never invent customers, numbers or quotes):
- Product: {{what it is, one sentence}}
- Audience: {{who lands on the page}}
- Primary action: {{e.g. start free trial}}
- What changes for the user: {{the outcome}}
- How it works: {{2–4 steps or mechanisms}}
- Key features → outcomes: {{feature: outcome, with numbers if real}}
- Proof: {{real customers, quotes, metrics — or "none yet"}}
- Pricing: {{if any}}
- Objections people have: {{e.g. "too complex to set up", "security"}}

Write these sections:
1. Hero: 3 headline options (≤ 10 words, specific, no filler verbs), 1 subhead
   (≤ 25 words: how it works or who it's for), primary + secondary CTA labels.
2. Proof bar: one line that introduces the logos/metric (only if proof exists).
3. How it works: 3 steps, each a 3–5 word title + one sentence.
4. Features: 3–5 blocks. Each is a title stating the outcome + one sentence with a
   concrete detail.
5. Objection handling: answer each objection in 1–2 sentences (works well as an FAQ).
6. Final CTA: a short closing headline + CTA label.

Banned words: supercharge, unlock, elevate, revolutionize, seamless, next-generation,
empower, cutting-edge, game-changer, effortless, robust, leverage.

After writing, cut every sentence by ~20% and remove any claim not backed by FACTS.
Output the final copy only.
```

**Next:** use the output as `{{COPY}}` in [prompt 02](02-generate-page.md).
