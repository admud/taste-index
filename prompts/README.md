# Landing Page Prompts for AI Tools

> **Copy-paste prompt templates for making beautiful landing pages with AI coding and design tools** (Claude, ChatGPT, Cursor, v0, Lovable, Bolt). They follow the [playbook](../playbook.md): references → style spec → copy → build → critique.

| # | Prompt | Use it to | Input |
|---|---|---|---|
| 01 | [Extract style](01-extract-style.md) | Turn reference screenshots into a style spec of tokens and rules | 2–6 reference screenshots |
| 02 | [Generate page](02-generate-page.md) | Build the full landing page | Style spec, copy, references |
| 03 | [Generate section](03-generate-section.md) | Rebuild or improve one section | Style spec, the section's copy, 1 reference |
| 04 | [Critique](04-critique.md) | Score your page against the [taste checklist](../taste-checklist.md) and get the top 3 fixes | Screenshots of your page and references |
| 05 | [Copy](05-copy.md) | Write specific, filler-free landing page copy | Product facts and proof |

## Tips

- **Always attach images.** Models match visual quality far better from screenshots than from text descriptions.
- **Use one conversation per page**, so the style spec stays in context.
- **Fix sections, not pages.** Regenerating everything undoes what was already good.
- **Run prompt 04 in a fresh conversation** so the critic isn't grading its own work too kindly.
- Replace every `{{PLACEHOLDER}}` before sending.

---

Part of **[Taste Index](../README.md)**.
