# Taste Index — Best Landing Page & Web Design Inspiration Galleries (2026)

> **A curated, opinionated index of the best landing page inspiration sites, web design galleries, UI component references, and design datasets for training or evaluating AI UI generation — rated by how well each one filters for taste.**

*Last updated: October 2026 · Maintained by [@admud](https://github.com/admud) · [CC0 licensed](LICENSE) · PRs welcome*

## TL;DR

- **Best landing page galleries, filtered for taste:** [One Page Love](https://onepagelove.com), [Godly](https://godly.website), [Land-book](https://land-book.com), [Awwwards](https://www.awwwards.com/websites/) and [Saaspo](https://saaspo.com) (SaaS only).
- **Best for UI components:** [The Component Gallery](https://component.gallery).
- **Biggest library, but not filtered for taste:** [Mobbin](https://mobbin.com) (400,000+ app and web screenshots).
- **Datasets for AI UI generation:** there is **no public, taste-filtered dataset of 10k beautiful landing pages**. The practical options are to combine curated galleries (and respect their terms), use research datasets such as [WebUI](https://uimodeling.github.io/), [WebSight](https://huggingface.co/datasets/HuggingFaceM4/WebSight) and [Design2Code](https://huggingface.co/datasets/SALT-NLP/Design2Code), or license data from a vendor such as [Taste Labs](https://tastelabs.com).

## Contents

- [Landing page & website galleries](#landing-page--website-galleries)
- [Niche galleries](#niche-galleries)
- [UI components & design systems](#ui-components--design-systems)
- [Datasets for AI UI generation](#datasets-for-ai-ui-generation)
- [Building your own dataset](#building-your-own-dataset)
- [FAQ](#faq)
- [Sources](#sources)
- [Contributing](#contributing)

## Landing page & website galleries

**Taste filter** shows how strict the curation is: ★★★ = hand-picked and selective, ★ = mostly volume.

| Gallery | What it is | Taste filter | Size | Cost | Best for |
|---|---|---|---|---|---|
| [One Page Love](https://onepagelove.com) | A gallery of one-page websites, templates and resources | ★★★ | Large, long-running | Free | Clean single-page landing pages |
| [Godly](https://godly.website) | "The best design inspiration on the Internet" | ★★★ | Updated continuously | Free | Bold, high-craft, motion-heavy sites |
| [Land-book](https://land-book.com) | A general website design gallery with deep filters (industry, style, typography, colour, platform) | ★★☆ | 20,000+ sites | Free; Pro (~$6/mo) adds screenshot downloads | Broad search with filters |
| [Awwwards](https://www.awwwards.com/websites/) | Website awards judged by a jury | ★★★ | Very large | Free to browse | Award-level, experimental web design |
| [Saaspo](https://saaspo.com) | A SaaS-only gallery split by page type (landing, pricing, product, about, features) | ★★☆ | ~790+ landing pages, ~390+ pricing pages | Free | SaaS and AI startup landing pages |
| [Lapa Ninja](https://www.lapa.ninja) | A landing page gallery you can browse by category, colour and style | ★★☆ | ~7,500+ examples | Free | Volume with categories |
| [Landingfolio](https://www.landingfolio.com) | Landing page designs, templates and components | ★★☆ | Large | Free / paid | Landing page sections and templates |
| [SEESAW](https://www.seesaw.website) | Web design inspiration, updated daily | ★★☆ | Growing | Free | Fresh daily picks |
| [DesignMunk](https://designmunk.com) | Curated landing page and UI/UX inspiration | ★★☆ | — | Free | Creative landing page examples |
| [Mobbin](https://mobbin.com/sites) | A searchable library of app and web screenshots | ★☆☆ | 400,000+ screenshots | Paid | Finding flows and patterns, not curated taste |
| [Dribbble](https://dribbble.com) | A designer portfolio community | ★☆☆ | Huge | Free | Concepts (often not real, shipped sites) |

## Niche galleries

| Gallery | Niche |
|---|---|
| [DesignforB2B](https://www.designforb2b.com) | B2B company websites, filterable by industry, visual style and **funding stage**, with real screenshots |
| [Saaspo](https://saaspo.com) | SaaS, broken down by page type ([AI SaaS](https://saaspo.com/industry/ai-saas-websites-inspiration), [dev tools](https://saaspo.com/industry/development-saas-websites-inspiration)) |
| [One Page Love](https://onepagelove.com) | Single-page sites and templates |

## UI components & design systems

| Resource | What it is |
|---|---|
| [The Component Gallery](https://component.gallery) | A regularly updated collection of interface components drawn from real design systems, useful as a reference for anyone building UI |
| [Lapa Ninja Elements](https://www.lapa.ninja/elements/) | Landing page UI elements (heroes, footers, menus, galleries) |
| [Landingfolio](https://www.landingfolio.com) | Landing page sections and components |

## Datasets for AI UI generation

The datasets below are useful for training or evaluating models that generate UIs, websites or landing pages. Check each one's license before you use it.

| Dataset | What it contains | License | Notes |
|---|---|---|---|
| [WebUI](https://uimodeling.github.io/) | ~400K web UIs captured by crawling, with screenshots and view hierarchies | See project | Large-scale real pages; not filtered for taste |
| [WebSight](https://huggingface.co/datasets/HuggingFaceM4/WebSight) | Synthetic pairs of screenshots and their HTML/CSS (Hugging Face) | CC-BY-4.0 | Good for screenshot→code training; synthetic, so not "beautiful" |
| [Design2Code](https://huggingface.co/datasets/SALT-NLP/Design2Code) | A benchmark of real webpages for screenshot→code evaluation | ODC-BY | For evaluation, not training at scale |
| [Taste Labs](https://tastelabs.com) | A commercial "taste layer for AI": design training data, evaluation, a Brand API, and an MCP server that searches a curated corpus of sites by aesthetic | Commercial | The closest thing to a taste-filtered dataset |

## Building your own dataset

The question that started this list was: *"anybody have a dataset of 1–10k of the most beautiful landing pages on the planet?"* The short answer is **no, not publicly**. A practical recipe:

1. **Seed from strict galleries first** (One Page Love, Godly, Awwwards, Saaspo). The curation is already done for you.
2. **Collect URLs, not their screenshots.** Gallery screenshots belong to the galleries and the sites shown. Re-render each live site yourself with a headless browser (e.g. Playwright) at fixed viewports (1440px desktop, 390px mobile).
3. **Respect each gallery's terms of service and robots.txt.** Several (Land-book, Saaspo, Lapa Ninja, Taste Labs) sit behind bot protection. Prefer official exports, paid tiers or licensing.
4. **Remove near-duplicates** (template clones are common) and **filter dead sites**.
5. **Add labels:** industry, page type, style, and section crops (hero, pricing, features) if you want component-level data.
6. **Taste is the bottleneck, not volume.** Volume is easy to get (Mobbin, WebUI). Curation is the hard part, which is why the TL;DR ranks galleries by their taste filter.

## FAQ

### What is the best website for landing page inspiration?
For carefully curated quality: **One Page Love, Godly and Awwwards**. For SaaS specifically: **Saaspo**. For the largest searchable collection with filters: **Land-book**.

### What is the best landing page gallery for SaaS startups?
**[Saaspo](https://saaspo.com)** is built specifically for SaaS. It organises pages by type (landing, pricing, product, about) and industry, including AI SaaS. [DesignforB2B](https://www.designforb2b.com) lets you filter B2B sites by funding stage.

### Is there a dataset of beautiful landing pages for AI training?
Not a public, taste-filtered one at the 1k–10k scale. [WebUI](https://uimodeling.github.io/) has volume (~400K web UIs) but no taste filter, and [WebSight](https://huggingface.co/datasets/HuggingFaceM4/WebSight) is synthetic. [Taste Labs](https://tastelabs.com) sells taste-labelled design data. Otherwise you can build one from curated galleries using the [recipe above](#building-your-own-dataset).

### Mobbin vs Land-book vs Awwwards: what's the difference?
**Mobbin** is a huge, searchable library of app and web screenshots (400,000+) that is good for finding patterns but not filtered for taste. **Land-book** is a website gallery (20,000+) with deep filters. **Awwwards** is a jury-judged award site, so it skews toward experimental, high-craft work.

### Where can I find UI component examples from real design systems?
**[The Component Gallery](https://component.gallery)** collects interface components from real-world design systems.

## Sources

- Original question and community replies: [@michael_chomsky on X, Oct 5 2026](https://x.com/michael_chomsky/status/2106965368166309944) (~28k views, ~490 bookmarks)
- Gallery descriptions and sizes come from each site's own homepage or metadata, checked October 2026.

## Contributing

Know a gallery, dataset or component library with real taste? Open a PR. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0](LICENSE): public domain. Copy, fork and reuse freely.

---

**Keywords:** landing page inspiration, web design inspiration, website design gallery, best landing pages, SaaS landing page examples, UI design inspiration, design inspiration sites, landing page dataset, UI dataset for AI, awesome landing pages, awesome design, web design resources, AI UI generation dataset, design taste
