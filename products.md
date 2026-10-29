# TraceDesk: Products, Plans and Pricing (products.md)

What TraceDesk sells: modules, plans, pricing, sales motion and SyncBridge facts. **As of October 29, 2026.** Company details and customer-base metrics are in [`company-facts.md`](company-facts.md). Positioning is in [`positioning.md`](positioning.md).

---

## 1. Products

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

## 2. Plans and pricing

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

### Sales motion (hybrid)

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

## 3. Case-study customers by plan

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

## 4. Value anchors

| Customer | Annual cost | Documented value | Multiple |
|---|---|---|---|
| Halloran Construction | $9,588 | About $140,000 cost of the last lapse | About 14.6x |
| PacFirst Freight | $17,988 | About $68,000 per year hire avoided | About 3.8x |
| Redvale Components | $9,588 | 11 hrs/week × about $50/hr × 52 weeks = about $28,600 | About 3.0x |
