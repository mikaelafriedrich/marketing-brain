# How to Use the Marketing Brain

A guide for anyone on the team who wants to plan and write TraceDesk campaigns with Claude Code. No coding or git knowledge needed.

---

## What this is

The Marketing Brain is a folder of files that teaches Claude everything it needs to write TraceDesk marketing: who we sell to, how we position the product, how we sound, and which facts and quotes we're allowed to use.

When you open this folder in Claude Code, Claude reads those files automatically. You describe what you want in plain language, and Claude writes it in the TraceDesk voice, using only approved facts. It also checks its own work, keeps a record, and saves everything to GitHub when you say so.

**What you get:** first drafts that are on-brand, accurate and traceable to a source, in minutes instead of days.

**What you still do:** set the goal, make the judgment calls Claude flags, and approve the final copy.

---

## Before you start

1. Open the **Claude desktop app** and go to the **Code** tab, or run `claude` in a terminal.
2. Open this folder: `marketing-brain`.
3. That's it. Claude loads the instructions in `CLAUDE.md` and the core files on its own.

You talk to Claude in normal sentences. Anything that starts with `/` is a shortcut command (see [Commands](#commands)).

---

## How it works

The files fall into four layers. Claude reads them in this order of authority: when two files disagree, the higher layer wins.

| Layer | Files | What they do |
|---|---|---|
| **1. Source of truth** | `company-facts.md`, `products.md` | Company details, dates, plans, pricing, customer numbers. These always win. |
| **2. Evidence** | `proof-points.md`, `testimonials.md` | The only statistics, results and quotes Claude may use. If it isn't here, it doesn't get published. |
| **3. Guidance** | `icp.md`, `positioning.md`, `brand-voice.md`, `brand-guidelines.md` | Who we sell to, what we say, how we sound, how things look. |
| **4. Workflow** | `briefs/`, `campaigns/`, `.claude/commands/`, `decisions.md` | Where campaigns are planned, written, reviewed and recorded. |

**`CLAUDE.md`** is the instruction sheet that ties these together. It tells Claude which files to read, which rules to follow, and to ask you before saving anything to GitHub.

---

## Running a campaign, step by step

### 1. Write the brief

Ask Claude to copy the template, then fill it in yourself or describe the campaign and let Claude draft it:

> Copy the brief template to briefs/holiday-renewals.md

**See [`briefs/BRIEF-GUIDE.md`](briefs/BRIEF-GUIDE.md)** for field-by-field guidance, tips, a checklist and common mistakes. The brief is the most important input: Claude writes every asset from it.

**Tip: start small.** Ask for one email and one LinkedIn post first. Check the tone and direction, then ask for the rest.

### 2. Generate the assets

Run:

> /campaign briefs/holiday-renewals.md

Claude will:

1. **Check the brief against the facts.** If something conflicts with `company-facts.md` or `products.md` (a wrong price, or a feature on the wrong plan), it stops and asks you first.
2. **Write each asset** as its own file in `campaigns/[campaign-name]/`.
3. **Make any graphics** the assets need (email headers, social images), following the brand guidelines.
4. **Review its own work** against the five checks in `/review`, and fix what it finds.
5. **Record the review** in the campaign's `review-log.md`.
6. **Update the brief** with the proof points written out in full, plus a schedule table linking every asset.
7. **Give you a short summary** and a list of anything that needs your decision.

### 3. Make your decisions and edits

Answer the questions Claude raises, then ask for changes in plain language:

> Make the second subject line shorter.
> Use a quote from a construction customer instead.
> Change the webinar date to November 19.

### 4. Review again before anything goes live

Run:

> /review campaigns/holiday-renewals/

You'll get a table of every issue with a suggested fix. Say "apply the fixes" if you agree. Each review is added to the campaign's `review-log.md`.

### 5. Save

When Claude finishes changing files, it asks whether to commit and push to GitHub. Say **yes** and it saves everything with a clear description. You never need to run git yourself.

---

## Commands

| Command | What it does | Example |
|---|---|---|
| `/campaign [brief]` | Writes every asset in a brief, makes graphics, reviews and fixes, logs the review, and updates the brief. | `/campaign briefs/holiday-renewals.md` |
| `/review [folder]` | Checks a campaign folder and reports issues. Doesn't change the assets. Logs the review. | `/review campaigns/holiday-renewals/` |
| `/weekly-report [audience]` | Reads the exports in `data/` and the targets in `goals.md`, then writes an offline HTML report to `reports/`: a goals scorecard, what changed, what needs attention and what to try next. It also writes a Markdown summary you can read on GitHub and a data notes file with next week's upload checklist. With no audience it uses the one in `goals.md`. | `/weekly-report` or `/weekly-report the CEO, who wants a 2-minute summary` |

### What `/review` checks

1. **Sources:** every number, result and quote, and where it comes from.
2. **Unsupported claims:** anything not in `proof-points.md` or `testimonials.md`, and any `[NEEDS SOURCE]` marker.
3. **Brand voice:** words on the avoid lists, and anything off-tone.
4. **Plans and internal figures:** features missing their plan label (for example SyncBridge must say "Scale"), and internal numbers in customer copy.
5. **Dates and links:** dates that don't match their weekday, and broken file or image links.

---

## Where things live

| Location | What's there | Who it's for |
|---|---|---|
| `briefs/template.md` | The blank brief | Copy it for each new campaign |
| `briefs/BRIEF-GUIDE.md` | How to fill in each field, with tips and a checklist | Anyone writing a brief |
| `briefs/[campaign-name].md` | The campaign's brief: goals, audience, proof points, schedule, open questions | **Internal**, team only |
| `campaigns/[campaign-name]/` | The finished assets, one file each | **Customer-facing** |
| `campaigns/[campaign-name]/graphics/` | Images, named `[campaign-name]-[asset].png` | Upload these to email or social tools |
| `campaigns/[campaign-name]/graphics/src/` | Editable versions of the images | Ask Claude to change the text and re-export |
| `campaigns/[campaign-name]/review-log.md` | Every review, what it found, what was fixed | **Internal**, team only |
| `goals.md` | Marketing targets and the default report audience | **Internal**, team only |
| `data/` | Exports (GA4, ads, CRM, email), notes on how to read them, and readable campaign names. Each week, add only that week's files and re-export the two CRM files; the latest data notes file has the checklist | **Internal**, team only |
| `reports/` | Weekly reports (`YYYY-MM-DD-weekly-report.html`; open it in a browser, since GitHub shows only the code), a GitHub-readable summary (`YYYY-MM-DD-summary.md`) and data notes (`YYYY-MM-DD-data-notes.md`) | **Internal**, team only |
| `decisions.md` | Why things are set up the way they are | Anyone wondering "why do we do it this way?" |
| `README.md` | An index of every file | Finding things |

---

## The rules that keep copy accurate

Claude follows these automatically. Knowing them helps you understand its questions.

- **Only approved facts.** Every statistic comes from `proof-points.md`. If Claude needs a fact that isn't there, it writes **`[NEEDS SOURCE]`** instead of making one up. That's your cue to find the fact or cut the line.
- **Only approved quotes.** Quotes come word for word from `testimonials.md`, with name, title and company.
- **Internal numbers stay internal.** Goals, adoption rates and churn can go in briefs, never in customer-facing assets.
- **Features carry their plan.** RiskMap and escalation say "Professional." SyncBridge, the API and SSO say "Scale."
- **The brand voice is strict.** No exclamation marks, no hype words, no "real-time," "no IT" or "fool-proof." The full list is in `brand-voice.md`.

---

## Changing the facts

When something real changes, such as a new customer count, a price change or a new quote, tell Claude:

> Our customer count is now 512 as of December 31.

Claude updates the source-of-truth file first, then searches every other file for the old value and lists what still needs changing.

When the team makes a decision about **how** things work (a new rule, a new folder, a new process), Claude adds it to `decisions.md` with the date and the reason.

---

## Graphics

- Graphics are made in TraceDesk's colors and fonts, from `brand-guidelines.md`.
- To change a graphic, ask Claude: "Change the LinkedIn image headline to …" It edits the source and re-exports the PNG.
- Images use sample data where they show the product. Check the review log for any notes about them.

---

## Troubleshooting

| If… | Then… |
|---|---|
| A draft has a number you don't recognize | Run `/review`. It traces every claim to its source or flags it. |
| Claude stops and asks about a conflict | That's working as intended: the brief disagrees with the facts files. Decide which is right; if the facts files are outdated, update them first. |
| You see `[NEEDS SOURCE]` | Claude needed a fact we don't have. Add it to `proof-points.md`, or ask Claude to rewrite the line without it. |
| You want to undo a change | Ask Claude: "Undo the last change to the email." Every saved version is on GitHub. |
| You're not sure why something is set up a certain way | Check `decisions.md`, or ask Claude. |

---

## A worked example: SyncBridge Adoption

See [`briefs/syncbridge-adoption.md`](briefs/syncbridge-adoption.md) for a complete brief, and [`campaigns/syncbridge-adoption/`](campaigns/syncbridge-adoption/) for the assets, graphics and review log. The brief guide covers what went wrong in the first draft and how it was fixed.
