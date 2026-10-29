# TraceDesk: Company Facts (company-facts.md)

The single source of truth for company details, timeline, pricing and customer-base metrics. All other documents defer to this file. **As of October 29, 2026** (customer-base metrics as of September 30, 2026).

---

## 1. Company snapshot

| | |
|---|---|
| **Company** | TraceDesk, Inc. |
| **What it makes** | Vendor compliance tracking software for mid-market procurement teams |
| **Category** | Mid-market vendor compliance management (the market category); a vendor compliance tracking tool (what the product is) |
| **Founded** | March 2022 |
| **Headquarters** | Chicago, Illinois, with an office in Toronto, Ontario (engineering and customer success) |
| **Founders** | Jonathan Reyes, CEO (former procurement operations lead at a regional food manufacturer); Anita Brooks, CTO (former ERP integration engineer) |
| **Team** | 64 employees |
| **Funding** | $3.2M seed (2022); $14M Series A (November 2024) |
| **Stage** | Early growth; product-market fit established |
| **Customers** | 487 active customers (September 30, 2026) |
| **ARR** | About $4.7M (list annual pricing) |
| **Geography** | North America: 91% of customers in the US, 9% in Canada |
| **Mission** | Give procurement teams a system that runs itself, so nothing expires on a spreadsheet no one owns |

**Origin story.** Jonathan spent three years as a procurement operations lead sending reminder emails to suppliers every Monday morning. The spreadsheet he used worked because he maintained it. When an expired supplier certificate surfaced during a customer audit and put a major contract at risk, he saw that the problem wasn't getting suppliers to care. It was that nobody, including the suppliers, could see what was about to expire. TraceDesk was built so vendors manage their own renewals and the procurement team manages exceptions.

---

## 2. Timeline

| Date | Milestone |
|---|---|
| March 2022 | Company founded |
| September 2022 | CertVault and the vendor portal go live with the first customers |
| February 2023 | RenewalPulse (automated reminders and escalation) released |
| October 2023 | RiskMap (compliance risk scoring) released |
| November 2024 | Series A closed |
| Q3 2025 | NPS +38 |
| Q1 2026 | NPS +47 (most recent survey) |
| March 9, 2026 | SyncBridge announced; private beta begins with five customers |
| May 4–8, 2026 | SyncBridge beta customer interviews |
| **May 15, 2026** | **SyncBridge generally available** (Scale plan) |
| June 2026 | Customer interviews (11 customers) |
| September 9, 2026 | Current one-pager published |
| Q4 2026 | Next NPS survey |

---

## 3. Products

| Module | What it does | Plan |
|---|---|---|
| **CertVault** | Document and expiry hub. Vendors upload to a self-service portal; expiry dates are parsed automatically; status shows valid, expiring soon or lapsed per vendor per document type | All plans |
| **RenewalPulse** | Automated renewal nudges to vendor contacts at 90, 60 and 30 days before expiry; escalation to the vendor's account owner if ignored | Reminders on all plans; configurable sequences and escalation routing on Professional and Scale |
| **RiskMap** | Rolling compliance risk score per vendor (document completeness, renewal history, coverage gaps); riskiest vendors first | Professional and Scale |
| **SyncBridge** | ERP integration with SAP S/4HANA, Oracle NetSuite and Microsoft Dynamics 365. Roster syncs from the ERP into TraceDesk; compliance status writes back to ERP vendor records; optional compliance-gated PO logic | Scale |

### SyncBridge facts (generally available since May 15, 2026)

- No-code setup. Customers are typically live in **under 3 hours** with **minimal IT support** (usually 20–30 minutes to confirm permissions or credentials).
- Since GA, 41 customers have connected SyncBridge (SAP S/4HANA 16, Oracle NetSuite 14, Microsoft Dynamics 365 11). Average setup time is 2 hours 25 minutes; median IT involvement is 25 minutes.
- **Sync direction.** By default the ERP is the source of truth for the vendor roster, and compliance status always writes back to the ERP. Admins can optionally enable two-way updates for non-financial roster fields (contact name, email, vendor category). All five beta customers asked for ERP-authoritative behavior; one team initially expected edits to flow back, which is why the option exists.
- **Sync window.** Updates appear within 15–20 minutes; it is not real-time.
- **Setup documentation published at GA:** a Dynamics 365 permission-scope checklist and a custom field-mapping guide for non-standard vendor category labels.
- **Compliance-gated POs** are optional and change how purchase approvals work. The recommended rollout is a pilot on the highest-risk vendors first.

---

## 4. Pricing and plans

All plans include CertVault, RenewalPulse reminders, the vendor self-service portal and unlimited document types. Prices are per month.

| | **Essentials** | **Professional** | **Scale** |
|---|---|---|---|
| **Annual billing (20% off)** | **$399/mo** | **$799/mo** | **$1,499/mo** |
| **Monthly billing** | $499/mo | $999/mo | $1,875/mo |
| **Active vendors** | Up to 75 | Up to 250 | Unlimited |
| **Internal user seats** | Up to 3 | Up to 10 | Unlimited |
| RiskMap risk scoring and dashboard | | ✓ | ✓ |
| Configurable reminder sequences | Standard fixed cadence | ✓ | ✓ |
| Escalation routing | | ✓ | ✓ |
| Compliance history reports | Basic (30 days) | Full history | Full history |
| Audit-ready PDF export | | ✓ | ✓ |
| SyncBridge ERP integration | | | ✓ |
| Compliance-gated PO logic | | | ✓ |
| API access, SSO / SAML | | | ✓ |
| Onboarding | Self-serve docs | Self-serve plus setup call | White-glove; live in 4 days, guaranteed |
| Support | Email (48h SLA) | Priority email (24h SLA) | Priority plus dedicated CSM |
| Uptime SLA | Standard | Standard | 99.9% |
| Typical buyer | 30–75 vendors, 1–2 person team | Core customer: 75–250 vendors | 250+ vendors, ERP users, 500–1,000 employees |

**Plan mix (September 30, 2026):** Essentials 117 customers (24%), Professional 302 (62%), Scale 68 (14%).

**Free trial:** 14 days, no credit card, full Professional features.

### Sales motion: hybrid

- Essentials and Professional: self-serve (trial, then card) or demo-assisted.
- Scale: demo required.
- Primary call to action: **Book a demo**. Secondary: **Start a free trial**.
- **Demo commitment:** the 30-minute live demo includes importing the prospect's vendor list, so they see their own compliance status. This is the offer on the one-pager.

### Discounts

| Scenario | Discount |
|---|---|
| Annual contract | 20% (built into annual pricing) |
| Multi-year (2+ years) | Up to 30%; VP approval |
| Competitive displacement from a paid tool | 15% first year; manager approval |
| Pilot for 500+ employee accounts | 60-day pilot at cost, converting to Scale annual |
| 500+ vendors, custom scope | Custom quote |

No discounts for urgency or to beat a spreadsheet; win those on value.

### Case-study customers by plan

| Customer | Vendors | Plan | Annual cost |
|---|---|---|---|
| Redvale Components | 187 | Professional | $9,588 |
| Suncrest Valley Foods | 94 | Professional | $9,588 |
| PacFirst Freight Solutions | 312 | Scale | $17,988 |
| Halloran Construction Group | 156 | Professional | $9,588 |
| Meridian Facilities Group | 230 | Professional | $9,588 |
| Cascade Metal Works | 88 | Professional | $9,588 |
| Summit Distribution | 175 | Professional | $9,588 (about $800/month) |
| Ironshore Construction | 142 | Professional | $9,588 |
| Harvest & Grain Co. | 108 | Professional | $9,588 |
| Continental Packaging | 204 | Professional | $9,588 |
| Lakefront Cold Storage | 67 | Professional (chose RiskMap for dual-regulated operations) | $9,588 |

### Value anchors

| Customer | Annual cost | Documented value | Multiple |
|---|---|---|---|
| Halloran Construction | $9,588 | About $140,000 cost of the last lapse | About 14.6x |
| PacFirst Freight | $17,988 | About $68,000 per year hire avoided | About 3.8x |
| Redvale Components | $9,588 | 11 hrs/week × about $50/hr × 52 weeks = about $28,600 | About 3.0x |

---

## 5. Customer base (September 30, 2026)

### Mix

| Industry | Share of customers |
|---|---|
| Manufacturing | 31% |
| Logistics | 22% |
| Food & beverage | 19% |
| Construction | 18% |
| Facilities management | 10% |

Median customer: 340 employees, 142 active vendors.

### Average results across the customer base

| Metric | Result | Basis |
|---|---|---|
| **Vendor portal adoption within 30 days of go-live** | **94% average** (median 95%) | 431 customers live at least 30 days; share of invited vendors who logged in and uploaded at least one document |
| **Time saved in manual vendor follow-up** | **11 hours per week average** (median 10) | 276 customers responding to the 90-day time-savings survey (self-reported) |
| **Time from signed contract to live** | **4 days average** (median 3; 86% within 5 days) | All 487 customers; "live" means first vendor invitations sent |
| **Audit compliance after go-live** | **100%** | 129 customers audited since go-live; none had audit findings tied to lapsed or missing vendor certificates |
| **SyncBridge setup time** | **Under 3 hours** (average 2 hr 25 min) | 41 customers connected since GA |
| Gross logo retention (trailing 12 months) | 93% | Internal |
| Churn within first 90 days | 4.8% | Internal; customers who leave before their first renewal cycle |

### NPS (Q1 2026 survey; source of truth)

| | |
|---|---|
| Overall | **+47** (up from +38 in Q3 2025) |
| Respondents | 312: 181 promoters (58%), 97 passives (31%), 34 detractors (11%) |
| By segment | Food & beverage +61; 500+ employee accounts +29 (before SyncBridge GA) |
| By tenure | +31 at 0–3 months rising to +61 at 12+ months |
| Detractors | 26 of 34 (76%) cited missing ERP integration |
| Passives | 62 of 97 (64%) named a specific fixable gap, ERP integration most often |
| Referrals | About 105 of the 181 promoters have made an informal referral; no structured referral program yet |
| Next survey | Q4 2026 |

### Reviews and channels

- G2: 61 reviews (up from 34 in May 2026 as the review program ran); top competitors have 180+.
- Top acquisition channels: organic search, peer referral (the leading discovery source), LinkedIn, G2 and Capterra, Google search ads.
- Best-converting content: the vendor compliance checklist for manufacturing teams, "5 signs your vendor compliance process has outgrown spreadsheets," and "What happens when a vendor's insurance lapses."
- The customer stories page converts best on the site.

---

## 6. Customer research

- **Customer interviews (June 2026):** 11 customers across five industries, 3–16 months of tenure.
- **SyncBridge beta interviews (May 4–8, 2026):** 5 beta customers, 4–8 weeks of use. Platforms: SAP S/4HANA ×2, Oracle NetSuite ×2, Microsoft Dynamics 365 ×1. 290–710 employees; 162–387 vendors.

Details are in `proof-points.md`; quotes are in `testimonials.md`.
