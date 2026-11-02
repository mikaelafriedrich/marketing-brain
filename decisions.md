# TraceDesk: Decision Log (decisions.md)

Why things are the way they are in this repo, newest first. Each entry gives the decision, the reason and the files it affects. When a decision changes, add a new entry rather than editing the old one, and note what it replaces.

---

## November 2, 2026: Weekly marketing report

| Decision | Why | Files affected |
|---|---|---|
| **A `/weekly-report` command builds an offline HTML report** from the exports in `data/` and the targets in `goals.md`. | One repeatable summary of what changed, what needs attention and what to try next, instead of pulling numbers by hand. | `.claude/commands/weekly-report.md`, `README.md`, `GUIDE.md` |
| **The default audience is the marketing lead, with analyst detail kept in the source sections and Data Notes.** | The lead needs a short summary and scorecard; the analyst needs method, denominators and sample sizes without crowding the summary. | `goals.md` |
| **Targets live in `goals.md`, rated On track, Watch or Off track.** Weekly reports use the pacing column. Targets are proposed until the marketing lead confirms them. | The command needs one place to judge numbers against. "On track" replaces "On target" so the labels match the command. | `goals.md` |
| **Reports, goals and data are internal,** like briefs. Their numbers never go into `campaigns/`. | They include pipeline, deal values and targets. | `goals.md`, `.claude/commands/weekly-report.md` |
| **Range and snapshot exports are sliced into the same Friday-to-Thursday weeks as GA4.** | The CRM exports cover several weeks in one file; slicing by date column keeps every source on the same week. | `.claude/commands/weekly-report.md` |
| **When deal amounts disagree with products.md, the report shows the data as exported and flags it.** | products.md is the source of truth, but the report should reflect what the CRM says. The first run found Scale deals at $18,228 instead of $17,988. | `.claude/commands/weekly-report.md` |
| **Email metrics lead with clicks, click rate and conversions,** not open rate. | Apple Mail Privacy Protection inflates opens. | `.claude/commands/weekly-report.md` |
| **Demo requests come from the GA4 `demo_request` event, or the CRM `Demo Requested Date` when there is no GA4 key-events export.** Weekly demo status: 20 or more On track, 16–19 Watch, 15 or fewer Off track. | GA4 "Key events" mix demo requests with trial starts. The reconciliation file shows the CRM and GA4 counts match for every channel. | `goals.md`, `.claude/commands/weekly-report.md` |
| **Brand search is excluded when the report suggests where to move budget.** | The first run recommended moving LinkedIn budget into brand search because it had the lowest cost per demo, but brand volume is capped by brand demand. | `.claude/commands/weekly-report.md` |
| **Data notes move out of the report into `reports/YYYY-MM-DD-data-notes.md`,** which starts with next week's upload checklist. | The technical detail cluttered the report for its main reader; the checklist makes each week's upload clear. | `.claude/commands/weekly-report.md`, `README.md`, `GUIDE.md` |
| **Each week, add only that week's files.** Weekly exports accumulate in `data/`; the CRM contacts and deals files are full snapshots, re-exported each week, and only the newest is used; email files are combined and de-duplicated. | Uploading everything each time is error-prone. The CRM changes after the fact (stages, deal outcomes), so it can't be added week by week. | `.claude/commands/weekly-report.md` |
| **Report layout: date range as the headline, Internal tag top right, weekly stats first, then the goals scorecard as bullet charts, then short cards with small charts whose titles say plainly whether a finding is good or bad.** | The marketing lead needs the week's numbers and the goal status at a glance; the summary was too dense, and "is under goal" read as bad news in the good column. | `.claude/commands/weekly-report.md` |
| **Ad campaigns show readable names from `data/campaign-names.csv`.** Codes appear only in the campaign table. | Leaders outside the day-to-day don't know codes like `li-vendor-audit-fb`. Names are unconfirmed until marked. | `data/campaign-names.csv`, `.claude/commands/weekly-report.md` |
| **Each run also writes a Markdown summary, `reports/YYYY-MM-DD-summary.md`,** with the weekly stats, scorecard, a Mermaid demo-request chart and the key findings. The HTML stays the full report. | GitHub shows HTML as code, so the report couldn't be read there. Markdown can't show the HTML's SVG charts, so the summary keeps to tables and simple Mermaid charts. | `.claude/commands/weekly-report.md`, `README.md`, `GUIDE.md` |
| **Reconciled files replace the exports they contradict.** | The Nov 2 data refresh added 17 contacts and a demo-request field; the old contacts export undercounted. | `data/`, `.claude/commands/weekly-report.md` |

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
