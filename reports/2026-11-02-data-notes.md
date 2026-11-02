# Data notes: weekly report for Oct 23 – 29, 2026

Companion to `reports/2026-11-02-weekly-report.html`. Internal. Covers what to upload next week, what this run used, how the numbers were calculated, and what needs fixing.

## Upload checklist for next week (Oct 30 – Nov 5)

Add these to `data/` and run `/weekly-report`. Leave earlier weeks' files in place: weekly files build the trend lines, and the report only needs the newest snapshot of the CRM files.

**Add one new file per week** (covering Friday to Thursday)

- [ ] `ga4-2026-10-30-to-11-05.csv`: GA4 > Reports > Acquisition > Traffic acquisition, by Session primary channel group
- [ ] `ga4-key-events-2026-10-30-to-11-05.csv`: the same report with Event name as a secondary dimension, filtered to `demo_request` and `trial_start`
- [ ] `google-ads-2026-10-30-to-11-05.csv`: Google Ads campaign report (Campaign, Impressions, Clicks, Cost, Conversions)
- [ ] `linkedin-ads-2026-10-30-to-11-05.csv`: LinkedIn Campaign Manager campaign performance (Campaign Name, Impressions, Clicks, Total Spent, Conversions)
- [ ] `email-2026-10-30-to-11-05.csv`: email sends in that week, one row per campaign. Add a conversion-type column if the platform allows it

**Replace with a fresh full export each week** (these change after the fact: leads move stages, deals close)

- [ ] `crm-contacts-2026-08-03-to-11-05.csv`: all contacts since Aug 3, including `Demo Requested Date`, `Became MQL Date` and `Became SQL Date`
- [ ] `crm-deals-2026-11-06.csv`: all deals, as of the day after the week ends

You can delete the older CRM files or leave them; the report uses the newest one.

**Only when something changes**

- [ ] `campaign-names.csv`: add a row for any new ad campaign so it shows with a readable name
- [ ] `crm-and-email-notes.md`: if field definitions change
- [ ] A reconciliation file, if one is produced (optional)

### This week's status

| Source | File | Status |
|---|---|---|
| GA4 traffic | `ga4-2026-10-16-to-10-22.csv`, `ga4-2026-10-23-to-10-29.csv` | Received |
| GA4 key events | `ga4-key-events-2026-10-16-to-10-22.csv`, `ga4-key-events-2026-10-23-to-10-29.csv` | Received |
| Google Ads | `google-ads-2026-10-16-to-10-22.csv`, `google-ads-2026-10-23-to-10-29.csv` | Received |
| LinkedIn Ads | `linkedin-ads-2026-10-16-to-10-22.csv`, `linkedin-ads-2026-10-23-to-10-29.csv` | Received |
| CRM contacts | `crm-contacts-2026-08-03-to-10-29.csv` (264 contacts) | Received (reconciled version, Nov 2) |
| CRM deals | `crm-deals-2026-10-30.csv` (30 deals) | Received |
| Email | `email-2026-09-10-to-10-27.csv` (13 sends) | Received |
| Display ads | none | Not exported (no target; plan is to pause) |

## Checks this run passed

- GA4 key events split (`demo_request` + `trial_start`) adds up to the GA4 Key events column for every channel, both weeks.
- GA4 demo requests (16 and 19) match CRM contacts with a Demo Requested Date in each week, for every channel. The reconciliation file agrees (every difference is 0).
- Google Ads and LinkedIn conversions match GA4 key events for Paid Search and Paid Social (Google 5 and 5; LinkedIn 2 and 3).
- Email unique clicks match GA4 Email sessions (31 and 29), and email conversions match GA4 Email key events.
- Email click rate, click-to-open and open rates recalculated from counts match the export.
- Campaign-level demo requests from CRM UTM campaigns add up to the channel totals.

## Method and definitions

- **Weeks** run Friday to Thursday to match the GA4 exports. CRM files are sliced into the same weeks by date column: contacts by Created Date, demo requests by Demo Requested Date, MQLs and SQLs by the date they reached that stage, deals by Create Date and Close Date. The CRM trend starts Sep 4, the first full week after demo tracking began on Sep 1.
- **Demo requests** this week and last come from GA4 `demo_request` events. Monthly totals, the eight-week trend, lead-source counts and campaign-level counts use the CRM Demo Requested Date, which gives the same weekly numbers.
- **Trial starts** come from GA4 `trial_start` events.
- **Cost per demo request** = platform spend ÷ GA4 demo requests from Paid Search (Google) or Paid Social (LinkedIn). The platforms' own conversions include trial starts, so they aren't used. Two-week figures: Google $248.50, LinkedIn $506.33.
- **Goal status** uses the weekly pace from goals.md: users 1,350 a week on track, 1,110 baseline; demo requests 20 on track, about 16 baseline (68 × 7 ÷ 30 = 15.9); visitor-to-demo 1.8% / 1.4%; Google $225 / $248; LinkedIn $340 / $378. Better than baseline but short of goal is Watch.
- **Visitor-to-demo rate** = demo requests ÷ users. Users are summed across channels, which overcounts people who arrived through more than one channel, so the true rate is probably a little higher.
- **Weekly lead-to-MQL rates aren't shown**: MQLs in a week mostly come from contacts created in earlier weeks. The lead-source table shows the share of contacts created since Sep 1 that have reached MQL and SQL so far. Of 134 contacts who requested a demo since Sep 1, 78 became MQLs and 39 became SQLs.
- **Win rate, average deal size and sales cycle** use every closed deal in the snapshot (created Aug 5 – Oct 26), because weekly counts are too small.
- **Quiet deals** are open deals with no activity for more than 14 days before the Oct 30 snapshot. The threshold is an assumption from the data notes; confirm it with sales.
- **Small samples**: anything based on fewer than 30 events is marked "small sample" and isn't called a trend. Every channel has fewer than 30 key events a week, every ad platform has 1 to 3 demo requests a week, and every newsletter has fewer than 35 clicks.
- **Email**: compared within type (newsletter, promo, nurture). Open rates are left out of conclusions because Apple Mail Privacy Protection inflates them.
- **No double counting**: GA4 key events, CRM contacts and email conversions can be the same people, so they're never added together.
- **Charts**: GA4 and ads have only two weeks, so they're shown as this-week-vs-last bars. Trend lines appear once three or more weeks are in `data/`.

## Column mappings

- GA4 "Session primary channel group (Default Channel Group)" → channel. GA4 Direct = CRM Direct Traffic, Referral = Referrals, Email = Email Marketing. CRM Offline Sources has no GA4 equivalent.
- GA4 key events: "Event name" `demo_request` → demo requests, `trial_start` → trial starts; "Event count" → count.
- Google Ads "Cost" and LinkedIn "Total Spent" → spend. Campaign names match CRM and GA4 `utm_campaign`. No totals rows; campaign rows were summed.
- CRM "Deal Amount" → annual contract value; "Closed Won/Lost" → outcome. UTM values lowercased before grouping.
- Email: click rate = unique clicks ÷ delivered; bounce rate = bounces ÷ sent.

## Campaign display names

The report shows campaigns by readable names from `data/campaign-names.csv`. All names are confirmed.

## Not covered

- **Display ads**: no export.
- **GA4 new users and landing pages**: not in the export. Adding the landing page report would show which pages drove the Organic Search increase.
- **Email conversion type**: the export doesn't say whether a conversion is a demo request, trial start, webinar registration or G2 review.

## Odd values to fix

- **Scale deal amounts don't match products.md.** 7 Scale deals are recorded at $18,228 a year; products.md lists $17,988 (annual billing). Pipeline may be overstated by $240 per Scale deal ($720 across open Scale deals). The report shows amounts as exported.
- Deal names use "Essential"; the plan is "Essentials".
- The Oct 8 SyncBridge Spotlight subject line says "synced in under 2 hours (no IT project)". proof-points.md supports "live in under 3 hours with minimal IT support." Fix before reusing it.
- goals.md targets are still marked "Proposed."
