You are building the weekly marketing report and its data notes. Read goals.md, utm-guide.md (if it exists), every CSV in data/, and every notes file (*.md) in data/. Also read products.md and brand-guidelines.md, and the most recent reports/*-data-notes.md (if any) for open questions from last week.

## Audience
- The audience for this report is: $ARGUMENTS
- If $ARGUMENTS is empty, use the "Report audience" section in goals.md. If that is missing too, ask me who the report is for before writing anything.
- If $ARGUMENTS looks like a filename (for example audience-exec.md), read that file and use it as the audience description.
- Write the summary, headline numbers, and suggested actions for that reader. Lead with what they care about and the decisions they make. Match their level of technical detail.
- Executives: put the three biggest changes and the goals scorecard first, keep the summary short, and keep metric jargon out of it.
- Team members or channel owners: include more detail by channel and campaign, and make the suggested actions tactical.
- Analysts: show the method, definitions, denominators, and sample sizes; keep this detail in the per-source sections and the data notes file so it doesn't crowd the summary.
- Clients: use a neutral, professional tone, explain what each number means, and avoid internal shorthand.
- Do not change any numbers or leave out bad news for the sake of the audience. Only the framing and level of detail change.
- State the intended audience in the header, in small type.

## Step 1: Inventory the data
- Identify which sources are present: GA4 traffic (ga4-<dates>), GA4 key events (ga4-key-events-*), ad platforms (google-ads-*, linkedin-ads-*, or ads-*), CRM contacts (crm-contacts-*), CRM deals (crm-deals-*), email (email-*), reconciliation files (*-reconciliation-*), and campaign display names (campaign-names.csv).
- data/ keeps every week. The person running this only adds the latest week, so build trends from all the files already there:
  - **Weekly files** (ga4-, ga4-key-events-, google-ads-, linkedin-ads-): one file per week. Use every week present, in date order.
  - **Email** (email-*): files may cover one week or many. Combine them all and drop duplicate rows (same Campaign Name and Send Date), keeping the row from the newest file.
  - **CRM snapshots** (crm-contacts-*, crm-deals-*): each file is a full export. Use only the newest one (latest end date in the filename) and ignore older ones.
- When newer files are added that contradict older ones (for example a corrected export with the same name), use the newer ones and say so in the data notes.
- Group files by source and sort by date in the filename.
- The "current week" is the most recent weekly period. The "previous week" is the one before it. Use the GA4 file dates to set the week boundaries when GA4 is present.
- Some exports cover a date range or are a snapshot (for example crm-contacts-2026-08-03-to-10-29.csv or crm-deals-2026-10-30.csv). Slice them into the same weeks using their date columns (created, MQL, SQL, close dates) rather than treating the whole file as one week.
- If a notes file in data/ describes a file that isn't there, treat that source as missing.
- If a source is missing for the current week, skip it and say so in the report. Do not estimate.
- If column names differ from what you expect, map them sensibly and list your mapping in the data notes.

## Step 2: Calculate these metrics (only when the data supports them)
GA4: sessions, users, new users, engagement rate, conversions/key events, sessions and conversions by channel, top landing pages.
Ads: spend, impressions, clicks, CTR, CPC, conversions, cost per conversion, by platform and campaign.
CRM contacts: new contacts, new contacts by lead source, demo requests (by Demo Requested Date) by lead source, new MQLs, new SQLs, lead-to-MQL and MQL-to-SQL conversion rates.
CRM deals: new deals created, pipeline value created, deals won, deals lost, win rate, average deal size, average sales cycle length, top lost reasons, open pipeline and stale open deals (rule in the data notes, if any).
Email: emails sent, delivered, bounce rate, unsubscribe rate, spam complaint rate, unique clicks, click rate, click-to-open rate, conversions, best and worst campaign by clicks.
Cross-source (only if UTM or campaign names allow a reliable match): cost per lead by channel (spend ÷ demo requests, as defined in goals.md), leads by campaign, email-driven sessions and conversions.

For each metric, show: this week, last week, and % change. Also show the trend across all weeks available.

## Step 3: Compare to goals
Compare results to the targets in goals.md, using its weekly pacing where there is one. Label each as On track, Watch, or Off track using the rules in goals.md, and show the number behind the label. If a target can't be measured with the data available, label it "Not measurable" and say what data is needed.

## Step 4: Build the HTML report
Create a self-contained HTML file at reports/YYYY-MM-DD-weekly-report.html (use today's date). It must work offline: no external scripts, fonts, images, or links. Draw all charts as inline SVG or with plain inline JavaScript. Make it clean, readable, and printable. Keep method, definitions, data checks and file details out of it: those go in the data notes file (Step 5).

Follow brand-guidelines.md for colors: Parchment page background, Midnight and Slate text, Compliance green for good, Alert red for bad, Amber for Watch. Because the file must work offline, use the font fallbacks (Georgia for display, system-ui for body) rather than loading web fonts.

Include, in this order (adjust emphasis for the audience, but keep every section):
1. **Header.** The week's date range is the largest text (for example "Oct 23 – 29, 2026"), with the comparison week under it. Add a small "Internal" tag in the top right. The prepared date and audience go in small type.
2. **This week at a glance**: a row of small tiles directly under the header for the weekly stats (sessions, new contacts, MQLs, pipeline created, deals won, ad spend), each with last week and % change (green for good, red for bad, neutral for spend).
3. **Goals scorecard**, under the weekly stats. One row per goal: name, a bullet chart (off track / watch / on track zones from goals.md, a marker for this week, a hollow marker for last week, labeled baseline and goal), the number, a status badge, and one short note.
4. **What changed**: the three biggest changes as cards. Each card has a short title, one big number, one or two sentences, and a small chart (for example an eight-week column chart or a this-week-vs-last bar).
5. **Needs attention** and **What's working**, side by side as cards: a title that states the finding with its number, one or two sentences, and a small chart where it helps. Up to four attention cards and three working cards.
6. **Try this week**: three numbered action cards, each tied to a specific number and small enough to do this week.
7. One section per source (Website, Paid ads, Leads and pipeline, Email) with:
   - A line chart of the main metrics across all weeks available (once there are three or more weeks; with two weeks, use a this-week-vs-last bar chart)
   - A bar chart of this week vs. last week
   - A small table of the top items (top channels, campaigns, lead sources, or emails)
   If a source is missing, keep its section with one line saying what's missing.
8. A one-line footer pointing to the data notes file.

Keep the writing in sections 4 to 6 short: no more than two sentences per card, and no caveats beyond "small sample". Card titles must make the direction obvious: say what is good or bad in plain words ("costs less per demo than the goal", not "is under goal"). Detail goes in the source sections and the data notes.

**Readable names.** Show ad campaigns by their display name from data/campaign-names.csv, with the code underneath in small type only in the campaign table. For a campaign not in that file, make a readable name from the code, use it, and list it in the data notes for confirmation. Name sources by what they are ("Google Analytics", "CRM", "Google Ads", "LinkedIn", "email platform"), not by file name.

Every chart needs a title, axis labels, the date range, and the data source (a short caption under small charts is enough). Never chart a metric you do not have data for. Do not use a chart where a table would be clearer (for example, a line chart with only two points).

## Rules
- Use plain language. Write for the audience, not for an analyst, unless the audience is an analyst.
- Use actual numbers from the files. Never guess or fill gaps. Write "not enough data" instead.
- Small numbers mislead. If a metric is based on fewer than 30 events (for example, 4 leads vs. 6 leads), say the sample is small and do not call it a trend.
- Be careful with cause and effect. Say "coincided with" rather than "caused" unless the data clearly shows it.
- If the same lead or conversion could appear in more than one source (for example, GA4 and the CRM), do not add them together.
- If numbers disagree between sources (for example, ad platform conversions vs. GA4 conversions), report both and flag the difference rather than choosing one.
- GA4 users summed across channels overcount unique users (one person can arrive through two channels). Say so when you report a total.
- Normalize UTM values to lowercase before grouping. Blank UTMs on Organic Search, Direct, Offline and most Referral contacts are expected, not a gap.
- If deal amounts or plan prices in the data disagree with products.md, products.md wins: report the data as exported, and flag the difference in the data notes.
- Suggested actions must be specific and small enough to do this week.
- Don't suggest moving budget into brand search campaigns: their volume is capped by how many people search the brand, so a low cost per lead there doesn't scale.
- Cost per lead uses demo requests only (goals.md), never the ad platforms' own conversions, which include trial starts. Show platform conversions alongside GA4 key events as a cross-check.
- Reports are internal, like briefs. Internal numbers are fine here, but never copy them into campaigns/.
- Use US spelling.

### Email metrics: how to judge them
Open rate is unreliable. Apple Mail Privacy Protection loads emails automatically, which inflates opens, so a high open rate does not mean people read the email.
- Weight unique clicks, click rate, click-to-open rate, and conversions most heavily. Lead with these.
- Never call a campaign strong or successful because of its open rate. A rise in open rate with flat or falling clicks is not an improvement.
- Click-to-open rate is also affected by inflated opens. Prefer click rate (clicks ÷ delivered) as the main engagement measure.
- Compare campaigns within the same email type. Nurture sends go to small, warm segments and will always beat newsletters on rates; do not rank them against each other.
- Watch the negatives too: unsubscribes and spam complaints per send.
- Conversion means different things by campaign (demo request, trial start, webinar registration, G2 review). Say which one when you report it.

## Step 5: Write the data notes
Create reports/YYYY-MM-DD-data-notes.md (same date as the report), in this order:
1. **Upload checklist for next week**, as Markdown checkboxes with the exact file names for the next Friday-to-Thursday week and where to export each one:
   - Add one new file per week: GA4 traffic, GA4 key events, Google Ads, LinkedIn Ads, email.
   - Replace with a fresh full export: CRM contacts, CRM deals.
   - Only when something changes: campaign-names.csv, notes files, reconciliation files.
   Then a table of this week's status for every source: received, missing, or not exported.
2. **Checks this run passed** (and any that failed): reconciliations between GA4, the CRM, ad platforms and email.
3. **Method and definitions**: week boundaries, how each metric and goal status was calculated, denominators, sample sizes.
4. **Column mappings.**
5. **Campaign display names** still to confirm.
6. **Not covered**: missing sources and anything you could not calculate.
7. **Odd values to fix.**

## Step 6: Finish
Print a short summary in the chat: both file paths, the audience you wrote for, the three biggest changes, and any data problems I need to fix (missing files, odd values, mismatched dates).
