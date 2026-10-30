# TraceDesk Knowledge Base

As of October 29, 2026. TraceDesk, its customers, competitors and data are fictional, created for world-building and workflow testing. Real regulators, ERPs and review sites are referenced for context.

## Files

| File | Purpose |
|---|---|
| [`company-facts.md`](company-facts.md) | Source of truth: company snapshot, timeline, customer-base metrics, NPS, research |
| [`products.md`](products.md) | Source of truth: modules, plans, pricing, sales motion, SyncBridge facts, customers by plan |
| [`icp.md`](icp.md) | Ideal customer profile; buyer versus user personas; triggers, pains, objections; US and Canadian regulatory vocabulary |
| [`positioning.md`](positioning.md) | Canonical statement, category, competitive landscape (October 2026), message house, SyncBridge and vertical positioning |
| [`brand-voice.md`](brand-voice.md) | Voice, master signal-word list, words to avoid, examples from the one-pager |
| [`brand-guidelines.md`](brand-guidelines.md) | Visual identity v1.1 (color bands, text colors, one-pager layout) |
| [`proof-points.md`](proof-points.md) | Fact-checker: customer-base metrics, case studies, research findings, claim guardrails |
| [`testimonials.md`](testimonials.md) | Approved quote library with IDs |
| [`decisions.md`](decisions.md) | Dated log of decisions behind this repo, and why |
| [`briefs/template.md`](briefs/template.md) | Blank campaign brief: goal, audience, message, proof points, assets, deadline, things to avoid |
| [`.claude/commands/campaign.md`](.claude/commands/campaign.md) | `/campaign <brief>`: writes every asset in a brief to `campaigns/<name>/`, then runs `/review` and fixes what it finds |
| [`.claude/commands/review.md`](.claude/commands/review.md) | `/review <folder>`: checks sources, unsupported claims, brand voice, plan labels, dates and links; reports issues and records them in the campaign's review log |

**Campaign folders**

- `briefs/[campaign-name].md`: one internal brief per campaign, copied from `briefs/template.md`. Includes goals, proof points in full, and the asset schedule with links.
- `campaigns/[campaign-name]/`: customer-facing assets, one file each.
- `campaigns/[campaign-name]/review-log.md`: internal record of every `/review` run, its findings and their status, newest first.
- `campaigns/[campaign-name]/graphics/`: images named `[campaign-name]-[asset].png`, with editable HTML sources in `graphics/src/`.

**Precedence when documents disagree:** `company-facts.md` and `products.md`, then `proof-points.md`, then everything else.
