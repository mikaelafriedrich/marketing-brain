# How to Write a Campaign Brief

The brief is the most important input to a campaign. Claude writes every asset from it, so a vague or wrong brief produces vague or wrong copy. This guide walks through each field of [`template.md`](template.md), with tips and things to consider.

For how the whole system works, see [`GUIDE.md`](../GUIDE.md).

---

## Before you start

- **Check the facts files first.** Look up anything your campaign depends on in `company-facts.md` and `products.md`: which plan includes the feature, the current price, the current customer numbers. Most brief errors come from an assumption that doesn't match these files.
- **Know what's internal and what isn't.** The brief is **internal**, team only. Goals, adoption rates, churn and the business reasons behind the campaign belong here. None of it goes into customer-facing assets.
- **You don't have to fill it in alone.** Describe the campaign to Claude in a few sentences and ask it to fill in the brief. Then read it carefully and correct what's off.

---

## Creating the brief

Ask Claude:

> Copy the brief template to briefs/[campaign-name].md

When you fill it in, **delete the prompts in parentheses** (they're there to help you, not for the finished brief), and use headings, bullets and bold labels so it's easy to scan.

---

## Field by field

### Campaign name

- **Short, lowercase and hyphenated in the file name,** such as `syncbridge-adoption`.
- It becomes the campaign folder (`campaigns/syncbridge-adoption/`) and the prefix for every image (`syncbridge-adoption-email-1-header.png`), so pick something you'll recognize in an upload tool months from now.

### Primary goal

- **One number, one date.** "75% of Scale customers connected to SyncBridge by December 18" is a goal. "Increase adoption" isn't.
- **Pick the outcome, not the activity.** Opens and clicks are signs the campaign is working; the goal is what the business actually wants (connections, demos, renewals).
- **Make sure the campaign can actually move it.** If the goal needs 10 more customers to act, check that there are enough customers in the audience to get there.

### Baseline

- **Always state where the number comes from,** such as "41 of 68 Scale customers (60%), company-facts.md, September 30, 2026."
- **Don't use a number from memory or a rough guess.** The SyncBridge brief started with an assumed 25% baseline; the real figure in `company-facts.md` was 60%, which changed the whole goal.
- **If the number isn't in the files,** say so and note who will pull it. Add it to the open questions.

### Secondary goals

- **Use them for the steps on the way to the primary goal,** such as webinar registrations or demos booked.
- **Explain why each number is reasonable.** A sentence of reasoning ("26 of 34 detractors asked for ERP integration, so demand exists") lets the team challenge the number later.
- **Say whether it's a floor or a stretch.**
- **Count accounts, not just people,** when the goal is about companies. A buyer and an IT lead from the same customer are two attendees but one account.
- **Label assumptions.** If a number comes from an industry rule of thumb rather than TraceDesk data, say so.

### Measured on

- **Leave time after the last touch.** People act days or weeks after an email or webinar. About four weeks after the final asset goes out is a reasonable default.
- **Watch for holidays.** Late November (Thanksgiving is November 26 in 2026) and late December are slow for B2B.

### Audience

- **Name the segment and the roles,** using the personas in `icp.md`. The buyer (COO, VP Operations) frames value as **risk avoided**; the day-to-day user (Procurement Manager) frames it as **time saved**. Write for the one who makes the decision you need.
- **Split into tracks when the call to action differs.** In the SyncBridge campaign, Scale customers only needed to turn the feature on, while Professional customers needed to upgrade. Same message, different email.
- **Check plan access.** If a feature is plan-gated, the audience on a lower plan can't "just enable it." See the tier labels in `proof-points.md`.
- **Think about who else reads it.** Emails to buyers often get forwarded to IT or finance. Give each of them a line that answers their question.
- **Use the vertical's vocabulary** when the audience is one industry: suppliers, carriers or subs (see `brand-voice.md`).

### Key message

- **One sentence, then three supporting points at most.**
- **Lead with what changes for the customer,** not the feature name. "New vendors in your ERP appear in TraceDesk automatically" works better than "SyncBridge offers roster sync."
- **Reuse positioning.** Check `positioning.md` for an existing headline, battle line or vertical message before writing a new one.
- **Note your hypothesis,** such as "adoption is low because customers don't know about it." It tells Claude what problem the copy has to solve, and tells the team what to test.

### Proof points to use

- **Write them out in full,** not as IDs like "S-07" or "T-48." People won't open a second file to look them up.
- **Pick the strongest few for this audience.** Three to five claims and a handful of quotes is plenty. Group quotes by what they're good for (risk, IT, finance).
- **Prefer company-wide averages over single customers** for headline claims ("94% of vendors are on the portal within 30 days"). Use named customers for stories.
- **Use the current figures.** Beta or older numbers can be out of date. For SyncBridge, use the general-availability setup figures, not the beta timings.
- **Copy quotes exactly,** with name, title and company, from `testimonials.md`.

### Assets needed

- **Be exact:** "3 emails, 4 LinkedIn posts, 1 webinar outline, 1 sign-up page," not "some emails and social."
- **Start small.** Ask for one or two assets first, check the tone, then ask for the rest. Fixing the direction early is much cheaper than rewriting ten assets.
- **Include graphics** if the channel needs them (email headers, social images). Claude makes them from `brand-guidelines.md`.
- **Say who sends each email.** A dedicated CSM, a founder and a generic company address all read differently. Not every plan has a dedicated CSM.

### Webinar or events

- **Give the date, time and time zone,** such as "November 17, 2026, 1pm Eastern."
- **Allow about two weeks of promotion.** Work the asset dates back from the event.
- **Decide the format before the copy promises it.** Don't let an email say "time for your questions" until the outline confirms Q&A.
- **Plan the follow-up.** A recording or recap email after the event often converts better than the invite.

### Schedule

- **Give every asset a go-live date and a "final by" date.**
- **Work backward from the event or deadline.**
- **Double-check weekdays.** "Thursday, November 5" should actually be a Thursday. `/review` checks this, but it's easier to get right the first time.
- **Note what's handled elsewhere,** such as webinar confirmation and reminder emails sent by the webinar tool.

### Deadline

- **Check it against the schedule.** In the SyncBridge brief, a November 15 deadline left only two days to promote a November 17 webinar. Assets tied to an event need to be ready well before it.

### Anything to avoid

- **List the traps specific to this campaign,** such as claiming a feature is free or saying "real-time."
- **Always include:** internal numbers (goals, adoption rates) and internal arguments (retention, "stickiness") in customer copy.
- You don't need to repeat the general avoid list in `brand-voice.md`. Claude applies it to every campaign.

### Open questions

- **Write down what you don't know yet,** who owns it, and when you need the answer: a CRM data pull, a sender, a link, a webinar title.
- **Don't leave them in your head.** Claude uses placeholders like `[LINK]` until they're answered, and `/review` will keep flagging them.

---

## Checklist before running `/campaign`

- [ ] The baseline and goal numbers come from `company-facts.md` or another named source.
- [ ] Plan access is right for every audience track.
- [ ] Proof points and quotes are written out in full.
- [ ] Every asset has a go-live date, and the deadline fits the schedule.
- [ ] Event dates include a time zone and allow time for promotion.
- [ ] Internal-only figures are marked as internal.
- [ ] Open questions list an owner.
- [ ] The prompts in parentheses are deleted.

---

## Common mistakes (and how the SyncBridge brief caught them)

| Mistake | What happened | Fix |
|---|---|---|
| **Assuming plan access** | The first brief said customers only needed to enable SyncBridge. It's Scale-only. | Check `products.md`; split audiences into tracks by plan. |
| **Guessing the baseline** | The brief assumed 25% adoption; the real figure was 60%. | Take baselines from `company-facts.md` and cite them. |
| **IDs instead of content** | Proof points listed as "S-07, T-40 to T-48." | Write each claim and quote out in full. |
| **A deadline that doesn't fit the event** | Assets due November 15 for a November 17 webinar. | Build the schedule backward from the event. |
| **Copy promising an undecided format** | An email promised Q&A before the webinar was planned. | Decide the format first, or leave it out of the copy. |

See the finished example: [`syncbridge-adoption.md`](syncbridge-adoption.md).
