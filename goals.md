# TraceDesk: Marketing Goals (goals.md)

Targets and the report audience used by `/weekly-report`. Internal, like `briefs/`: never copy these numbers into `campaigns/`.

## Report audience

Primary reader: Marketing lead
What they care about: demo requests and pipeline, cost per lead by paid channel, website visitors, and whether we're pacing to this month's targets
Their technical level: not an analyst; wants plain language and the number behind every claim
Length they'll read: 5-minute skim of the summary and scorecard
Decisions they make from this report: budget shifts between Google Ads, LinkedIn Ads and Display; which campaigns or emails to pause; what the team works on this week

Secondary reader: Marketing analyst
What they need: method, definitions, denominators, sample sizes, and where sources disagree
Where it goes: the per-source sections and Data Notes, so the summary stays short for the marketing lead

---

## Targets

- **Status:** Proposed. Baselines are the last 30 days before November 2026. Targets are assumptions and should be confirmed by the marketing lead.
- **Effective:** November 2026 onward
- **Review cadence:** Monthly; weekly reports use the pacing column

| # | Metric | Direction | Baseline | Target | Weekly pacing | Source |
|---|--------|-----------|----------|--------|---------------|--------|
| 1 | Monthly demo requests (leads) | Higher is better | 68 | 85 | about 20 per week | GA4 `demo_request` key event |
| 2 | Visitor-to-demo conversion rate | Higher is better | 1.4% | 1.8% | n/a (rate) | Demo requests ÷ website visitors |
| 3 | Google Search Ads cost per lead | Lower is better | $248 | $225 or less | n/a (rate) | Google Ads spend ÷ demo requests from Paid Search |
| 4 | LinkedIn Ads cost per lead | Lower is better | $378 | $340 or less | n/a (rate) | LinkedIn Ads spend ÷ demo requests from Paid Social |
| 5 | Monthly website visitors | Higher is better | 4,820 | 5,800 | about 1,350 users per week | GA4 Users |

## How to rate a number

Apply the same rule to every target:

- **On track:** meets or beats the target.
- **Watch:** better than baseline but short of target.
- **Off track:** equal to or worse than baseline.

| Metric | On track | Watch | Off track |
|--------|-----------|-------|-----------|
| Monthly demo requests | 85 or more | 69 to 84 | 68 or fewer |
| Visitor-to-demo conversion | 1.8% or more | 1.5% to 1.7% | 1.4% or less |
| Google Search Ads CPL | $225 or less | $226 to $247 | $248 or more |
| LinkedIn Ads CPL | $340 or less | $341 to $377 | $378 or more |
| Monthly website visitors | 5,800 or more | 4,821 to 5,799 | 4,820 or fewer |

For weekly reports, compare against the pacing column (for example, weekly users of 1,350 or more is on pace; below about 1,110 is off track). Weekly demo requests: 20 or more is on pace; 16 to 19 is Watch; 15 or fewer is off track (the 68-a-month baseline is about 15.9 a week).

## Where each target's data comes from

| Target | Files | How to calculate |
|--------|-------|------------------|
| 1. Demo requests | `ga4-key-events-<dates>.csv` (CRM `Demo Requested Date` for monthly totals) | Sum `Event count` where `Event name` is `demo_request` (all channels). For a full month, count CRM contacts by `Demo Requested Date` |
| 2. Visitor-to-demo rate | `ga4-key-events-<dates>.csv` + `ga4-<dates>.csv` | Total `demo_request` events ÷ total `Users` |
| 3. Google Search Ads CPL | `google-ads-<dates>.csv` + `ga4-key-events-<dates>.csv` | Sum of `Cost` ÷ `demo_request` events where channel is `Paid Search` |
| 4. LinkedIn Ads CPL | `linkedin-ads-<dates>.csv` + `ga4-key-events-<dates>.csv` | Sum of `Total Spent` ÷ `demo_request` events where channel is `Paid Social` |
| 5. Website visitors | `ga4-<dates>.csv` | Sum of `Users` |

If there is no `ga4-key-events` file, count demo requests from the CRM `Demo Requested Date` by week and channel. The two sources match (see `data/demo-request-reconciliation-*.csv`).

## Notes for the report

- **Use `demo_request` events, not Key events.** The `Key events` column in `ga4-<dates>.csv` combines `demo_request` and `trial_start`. The key-events files split them, and the two always add up to that column.
- **Ignore the ad platforms' own Conversions and Cost / conv. columns for CPL.** They count demo requests and trial starts together, so they give a much lower cost per conversion than the CPL target measures.
- **GA4 has no ad cost.** If spend is missing, report CPL as "not available" rather than guessing.
- **Ad exports have no totals row.** Sum the campaign rows. Campaign names match the CRM and GA4 `utm_campaign` values.
- **Ad clicks exceed GA4 sessions.** This is normal (LinkedIn especially, as clicks include non-landing-page clicks). Do not flag it as a data error.
- **Weekly CPL rests on very few leads** (1 to 3 per channel per week), so a single lead swings it a lot. When the sample is under 5 demo requests, say so and avoid strong conclusions; the targets are really monthly.
- **GA4 and the CRM agree on demo requests.** For Oct 16–29, CRM `Demo Requested Date` counts match GA4 `demo_request` events for every channel. If a report shows a gap, treat it as a data error to flag, not a normal difference.
- **Mixed denominators.** The 1.4% baseline is demo requests per visitor (68 ÷ 4,820). Keep using users as the denominator so the comparison stays like for like.
- **Display ads** ($1,240 CPL) have no target and no export. The plan is to pause them and move the budget.
