# CRM and Email Data: Notes for Report Agents

All three files are **simulated** and consistent with the GA4 exports and `targets.md`. Snapshot date: 2026-10-30.

## Files

| File | What it is |
|------|-----------|
| `crm-contacts-2026-08-03-to-10-29.csv` | 264 contacts, one row per contact. 257 were created Sep 1 to Oct 29; 7 were created in early August because they are the primary contacts of deals opened before September |
| `crm-deals-2026-10-30.csv` | 30 deals (6 won, 9 lost, 15 open), as of the snapshot date. Each deal has a `Primary Contact ID` |
| `email-2026-09-10-to-10-27.csv` | 13 email sends, one row per campaign |

## CRM notes

- **Lead Source** uses the CRM's own names (Organic Search, Direct Traffic, Paid Search, Paid Social, Referrals, Organic Social, Email Marketing, Offline Sources). They map to the GA4 channel groups, except Offline Sources, which has no GA4 equivalent.
- **UTM fields are often blank**, as in real exports. Organic Search, Direct Traffic, Offline Sources and most Referrals have none. Do not treat blank UTMs as an error or a gap to flag.
- **A few UTM values are inconsistently cased** (for example `LinkedIn`, `CPC`). Normalize to lowercase before grouping.
- **Deals join to contacts on `Primary Contact ID`** (deals column) = `Contact ID` (contacts column). It is one to one: every deal has exactly one primary contact, and no contact has more than one deal. Only August contacts linked to a deal are included from before Sep 1, so do not use the contacts file to measure August lead volume.
- **Linked records are consistent.** A deal's primary contact was created on or before the deal's create date, became SQL on or before it, and has the same Lead Source. Contacts on won deals are `Customer`; contacts on open or lost deals are `Opportunity`. Every Opportunity and Customer contact has a deal.
- **Deal Amount is annual contract value (ACV)** in USD, based on the pricing tiers: Essential $4,788, Professional $9,588 (or $11,988 billed monthly), Scale $18,228.
- **Close Date is blank for open deals.** It is an actual close date, not an expected one.
- **"Closed Won/Lost"** is `Won`, `Lost` or `Open`.
- **Stale deal rule (assumption):** an open deal with no activity for more than 14 days since the snapshot date is stale. Confirm this threshold with sales.
- **`Demo Requested Date`** is the date the contact submitted the demo form (blank if they never did). It is populated from Sep 1 only; the 7 August contacts are left blank because they pre-date the demo tracking window, so do not count demo requests from August.
- **Demo requests reconcile to GA4.** For Oct 16-22 (16) and Oct 23-29 (19), the number of contacts with a `Demo Requested Date` in the week matches GA4 `demo_request` events exactly, for every channel. See `demo-request-reconciliation-2026-10-16-to-10-29.csv`. Channel names map as: GA4 `Direct` = CRM `Direct Traffic`, `Referral` = `Referrals`, `Email` = `Email Marketing`. `Offline Sources` has no GA4 equivalent and has no demo requests.
- **Demo requests by month (from the CRM):** September 62, October 1-29 72. Earlier weeks in the window run at 14 to 17 a week.
- **Order of dates:** `Created Date` ≤ `Demo Requested Date` ≤ `Became MQL Date` ≤ `Became SQL Date`, and a deal's primary contact requested the demo (if at all) before the deal was created. Not every MQL has a demo request; some qualify another way.
- **Funnel snapshot:** 65 Subscribers, 110 Leads, 42 MQLs, 17 SQLs, 24 Opportunities, 6 Customers. The contacts file includes MQL and SQL dates, so stage conversion and time-in-stage can be calculated directly.

## Email: how to read the metrics

Paste the block below into the report instructions.

```
EMAIL METRICS: HOW TO JUDGE THEM

Open rate is unreliable. Apple Mail Privacy Protection loads emails
automatically, which inflates opens, so a high open rate does not mean
people read the email. Treat it as a rough signal only.

- Weight unique clicks, click rate, click-to-open rate and conversions
  most heavily. Lead with these when summarising performance.
- Never call a campaign "strong" or "successful" because of its open rate
  alone. Do not celebrate a high open rate.
- Use open rate only to compare like with like (same list, same email
  type), and say it is directional.
- A rise in open rate with flat or falling clicks is not an improvement.
- Click-to-open rate is also affected by inflated opens. Prefer click
  rate (clicks ÷ delivered) as the main engagement measure.
- Compare campaigns within the same Email Type. Nurture sends go to small,
  warm segments and will always beat newsletters on rates; do not rank
  them against each other.
- Watch the negatives too: unsubscribes and spam complaints per send.
- Conversion means different things by campaign: demo request, trial
  start, webinar registration, or a G2 review submitted. State which
  one when reporting it.
```

## Email data notes

- **Conversions are tracked for every campaign** in this file.
- **Clicks reconcile with GA4:** unique clicks in the week of Oct 16-22 (31) and Oct 23-29 (29) match the GA4 Email sessions for those weeks, and conversions match Email key events (2 in each week).
- **Rates are decimals** (0.4920 = 49.2%), as in the GA4 files.
- **Newsletter clicks are drifting down:** click rate fell from 1.95% (Sep 15) to 1.20% (Oct 27). This is worth surfacing in the report, even though open rates look healthy.
