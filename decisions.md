# TraceDesk: Decision Log (decisions.md)

Why things are the way they are in this repo, newest first. Each entry gives the decision, the reason and the files it affects. When a decision changes, add a new entry rather than editing the old one, and note what it replaces.

---

## October 30, 2026: Campaign process and the SyncBridge brief

| Decision | Why | Files affected |
|---|---|---|
| **The SyncBridge campaign targets Scale customers first, then Professional.** Scale customers turn SyncBridge on; Professional customers book a demo to upgrade. | SyncBridge is on the Scale plan only, and proof-points.md rules out calling it free or available at no cost. The original brief assumed customers only needed to enable it. | `briefs/syncbridge-adoption.md` |
| **Campaign baselines come from company-facts.md.** The SyncBridge goal is 75% of Scale customers, up from 60% (41 of 68). | The brief started from an assumed 25% baseline that contradicted company-facts.md. | `briefs/syncbridge-adoption.md`, `briefs/template.md` |
| **Briefs are internal; campaign assets are customer-facing.** Internal numbers (adoption rates, churn, goals) can go in briefs but never in assets. | The team needs real targets in the brief without risking them leaking into copy. | `CLAUDE.md`, `briefs/template.md`, `.claude/commands/campaign.md`, `.claude/commands/review.md` |
| **Briefs write proof points and quotes out in full, not as IDs.** | People won't look things up in a second file. | `briefs/template.md`, `.claude/commands/campaign.md` |
| **Briefs use headings, bullets and bold, and drop the template's prompts in parentheses.** Each brief also includes a schedule with go-live dates. | Easier to scan. The prompts help when filling in a brief but clutter the finished one. | `briefs/template.md`, `.claude/commands/campaign.md` |
| **`/campaign` checks the brief against company-facts.md and products.md before writing anything,** and stops to ask if they conflict. | Both SyncBridge brief errors (plan access and baseline) would have been caught before any drafting. | `.claude/commands/campaign.md` |
| **Quotes come from testimonials.md, not proof-points.md,** in both `/campaign` and `/review`. | proof-points.md refers to quotes by ID only; the text and attribution format are in testimonials.md. | `.claude/commands/campaign.md`, `.claude/commands/review.md` |
| **Every campaign keeps a review log** (`campaigns/[campaign-name]/review-log.md`), linked from the brief. `/review` and `/campaign` add an entry each time they run. | A record of what was checked, what was found and what was fixed. | `.claude/commands/review.md`, `.claude/commands/campaign.md`, `README.md` |
| **Campaign images are named `[campaign-name]-[asset].png`,** with editable HTML sources in `graphics/src/`. | Files stay identifiable outside their folder, for example once they're uploaded to an email or social tool. | `CLAUDE.md`, `README.md`, `.claude/commands/campaign.md` |
| **brand-guidelines.md overrides the TraceDesk brand skill** when they disagree. | The skill still says to use Forest text on solid green; v1.1 in the repo says Parchment. | `CLAUDE.md` |
| **Decisions live in this file, not in README.md.** | Keeps the README a plain index of where things are. | `README.md`, `CLAUDE.md` |

---

## October 2026: Initial setup

Decisions made when the knowledge base was first assembled.

| Topic | Decision |
|---|---|
| Company | HQ Chicago with a Toronto office; founded March 2022; 64 employees; 487 customers; about $4.7M ARR |
| Timeline | SyncBridge announced March 9, 2026 (private beta), generally available May 15, 2026; all dates as of October 2026 |
| Pricing | $399 / $799 / $1,499 per month on annual billing, named Essentials / Professional / Scale |
| Plan naming | The top plan is named Scale, not Enterprise, so it doesn't contradict the "not an enterprise tool" positioning |
| ICP size | 100–1,000 employees (core 200–500; SyncBridge growth segment 500–1,000); 30–500 vendors; 0 or 1 compliance coordinator |
| Personas | Buyer personas and user personas are defined separately |
| Metrics | Company-wide averages are primary (94% adoption, 11 hours a week, 4-day go-live, 100% audit compliance); named customers are used for stories only |
| Halloran quote | Rewritten so the math works ($9,588 a year versus a $140,000 lapse) |
| Derek Chu quote | The one-pager wording is the standard; the near-duplicate attributed to Rachel Halloran was removed |
| SyncBridge claims | "Under 3 hours" with "minimal IT support"; ERP is the source of truth by default with an optional two-way roster setting |
| Category | Market label "vendor compliance management"; product descriptor "vendor compliance tracking tool" |
| Positioning | One canonical statement plus a support line; "runs itself" is figurative and always paired with it |
| Competitors | All named competitors are fictional; claims match the comparison table |
| Sales motion | Hybrid: free trial and demo; primary call to action is Book a demo |
| Spelling | US spelling; regulatory vocabulary includes Canadian equivalents |
| Brand guidelines | Updated to allow full-width green bands as used on the one-pager |
