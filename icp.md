# TraceDesk: Ideal Customer Profile (icp.md)

As of October 2026. Company, pricing and metric details are in [`company-facts.md`](company-facts.md); quotes are in [`testimonials.md`](testimonials.md).

---

## 1. Company profile

| Attribute | Detail |
|---|---|
| Employees | **100–1,000** (core 200–500; growth segment 500–1,000, driven by ERP integration through SyncBridge) |
| Active vendors | **30–500** (larger by custom scope). Under 30, a spreadsheet usually works; 30–75 fits Essentials |
| Industries | Manufacturing, logistics, food & beverage, construction, facilities management |
| Geography | North America (US and Canada) |
| Procurement team | 1–5 people |
| Dedicated compliance coordinator | **0 or 1.** Teams with one face the same problem (Continental's coordinator spent three days a week on follow-up; PacFirst was about to hire one) |
| Current system | Spreadsheet (Excel in SharePoint or Google Drive), shared drives, email inboxes |
| Obligation | Regulatory or contractual need to hold vendor documents (insurance certificates, ISO, food safety, SOC 2, safety training) |
| Size logic | Large enough that manual tracking is visibly breaking down; small enough that large enterprise procurement suites are overkill |

**Not a fit**

- Fewer than 30 vendors.
- More than 1,000 employees, or an enterprise procurement suite already in place.
- No contractual or regulatory obligation to track vendor credentials.
- Buyers who want broad vendor lifecycle management. TraceDesk is purpose-built for compliance tracking and says so.
- Construction firms that only track COIs, have under 50 subs and don't need risk scoring. CertTrackr is a reasonable choice, and we say so.

**Vertical notes**

- **Food & beverage (priority vertical, NPS +61):** Audit pressure from FDA, USDA, CFIA, SQF and BRCGS. A gap means a production hold or a regulator finding. The daily user is often the Food Safety & Compliance Manager.
- **Construction:** A lapsed COI can stop work on a live project. Often incident-triggered.
- **Logistics:** High carrier volume and turnover. Headcount avoidance is the ROI story.
- **Manufacturing:** ISO 9001, 14001, 45001, IATF 16949; recurring formal audits.
- **Facilities management:** Subcontractor-heavy; the departure of the spreadsheet owner is a common trigger.

**Small-vendor-count note:** Lakefront Cold Storage (67 vendors, dual-regulated) and Cascade Metal Works (88 vendors, team of one) show that vendor count alone doesn't decide fit. Regulatory burden and team size do.

---

## 2. Buyer personas vs user personas

**Buyer personas** hold the budget or sign off. **User personas** work in the product day to day. They are often different people, and they frame the value differently (users say time; senior buyers say risk).

### Buyer personas

| Persona | Titles | Role in the deal | Frames the value as | Priorities |
|---|---|---|---|---|
| **Champion and budget owner** | Procurement Manager, Vendor Operations Manager, Supply Chain Manager | Finds TraceDesk, builds the case, often holds budget up to about $1,000/month (Essentials and Professional) | Time saved | Ease of use, vendor adoption, time to value, peer validation |
| **Economic buyer** | COO, VP Operations, Director of Procurement, Supply Chain Director; CFO or VP Finance on larger deals | Approves the purchase, especially on the Scale plan | Risk avoided | ROI clarity, risk reduction, a CFO-defensible case. Derek Chu and Rachel Halloran both said procurement pitched time savings and they approved on risk |
| **Technical evaluator (ERP deals)** | IT & Procurement Systems Manager, IT lead | Can block or enable a Scale deal | "Is it another silo?" | ERP as source of truth, no custom integration project, minimal IT effort |

### User personas

| Persona | Titles | What they do in TraceDesk |
|---|---|---|
| **Primary user** | Procurement Manager, Procurement Coordinator, Vendor Operations Manager | Manage the vendor roster, review the dashboard, handle exceptions |
| **Compliance-side user** | Food Safety & Compliance Manager, Quality Manager, Operations Manager | Audit prep, risk review, certification tracking (common in food & beverage and manufacturing) |
| **Executive viewer** | COO, VP Operations | Checks RiskMap every couple of weeks; uses it in monthly ops reviews |
| **Finance and AP viewer (Scale plan)** | Finance team, AP | Sees compliance status inside ERP vendor records before approving POs or invoices |
| **Vendor contact (external user)** | Account manager or admin at the vendor | Uploads and renews documents through the portal; sees their own status. Their experience drives adoption |

**One person often plays several roles.** At a company with a team of one (Cascade Metal Works), the Procurement Coordinator is champion, user and often the budget owner.

---

## 3. Trigger events (what makes them start looking)

1. A vendor certificate lapsed and caused a project delay or audit finding (Halloran: 8-day stoppage, about $140,000).
2. An audit exposed documentation gaps (Redvale: three suppliers with lapsed ISO certificates; Suncrest: a two-week FDA scramble).
3. The owner of the spreadsheet left, went on leave or was promoted (Redvale, Meridian, Cascade, Harvest & Grain).
4. Headcount was cut, or compliance volume outgrew the team (PacFirst nearly hired a coordinator).
5. Vendor count doubled and the spreadsheet hit a cliff (Continental: 90 to 200 vendors).
6. A near-miss (Ironshore: a COI 11 days from lapsing, found by accident).
7. A new regulatory requirement raised the documentation burden.
8. For ERP users: SyncBridge removed the integration blocker (Cascadia re-engaged within a week of the announcement).

Deals are won on a triggering event and lost to "we already have a process." The real competitor is the spreadsheet.

---

## 4. Pains

**Primary user and champion**
1. Hours every week chasing vendors for updated certificates (7–12 hours a week reported; Lakefront about 4).
2. Finding out about lapsed certificates during an audit or when work stops.
3. No single source of truth: documents spread across email, shared drives and one spreadsheet.
4. Being the single point of failure ("if I'm out, nothing happens").
5. Carrying a list in their head of who might expire next.
6. Being the one sending the fourth or fifth reminder to an unresponsive vendor.

**Economic buyer**
1. Compliance gaps surface as expensive surprises on their desk.
2. No cross-vendor visibility until something fails.
3. Headcount pressure as vendor volume grows.
4. Compliance knowledge living in one person's head and spreadsheet.

**ERP users**
1. "Two systems telling two different stories": the ERP vendor list and TraceDesk drift apart, and vendors slip through the manual import step.
2. Finance approving invoices against vendors flagged as expiring or lapsed.

---

## 5. Goals

- Stop chasing; manage exceptions instead.
- Walk into an audit with a report ready in minutes (Suncrest: 45 minutes instead of two weeks).
- Know who is at risk before anything lapses.
- A compliance process that keeps running when one person is away.
- Scale vendor volume without adding headcount.
- A one-sentence ROI that a CFO or board accepts.

---

## 6. What they have tried before

- Excel in SharePoint or Google Drive, maintained by one person.
- Manual reminder emails ("Monday mornings sending reminders").
- Inherited or duplicated spreadsheets ("three versions of the same spreadsheet, none authoritative").
- Considering hiring a compliance coordinator (PacFirst).
- Enterprise procurement suites, evaluated and rejected as overbuilt, with 3+ month implementations and IT required.
- CompliGrid: organizes documents but has no vendor-facing portal.
- CertTrackr: COI-only.
- Custom ERP integration scoping (Vertex Industrial) before SyncBridge.

---

## 7. Objections and responses

| Objection | Response |
|---|---|
| "We already have a spreadsheet that works." | It works until it doesn't. The first audit or lapse shows when. Name it, respect it, then show where it breaks. Never call it legacy |
| "Will our vendors actually use it?" | 94% average portal adoption within 30 days across our customers. Lead with a customer's surprise story: 8 of 11 interviewees assumed vendors wouldn't |
| "Does it connect to our ERP?" | Yes, SyncBridge: SAP S/4HANA, Oracle NetSuite, Dynamics 365. No code, live in under 3 hours with minimal IT support. Available on Scale |
| "We don't have time to implement something new." | Live in 4 days on average, no IT team required |
| "We need more than compliance tracking." | TraceDesk is purpose-built for compliance tracking; for broader lifecycle management there are better fits |
| "It's too expensive." | Compared to what? If your last lapse cost more than a year of TraceDesk, you're already behind |
| "Your competitor is cheaper." | CertTrackr is cheaper and COI-only. Fine if that is all you track |
| "We already check certificates before we onboard a sub." | The problem is renewals six months into a project when no one is watching |
| "We're too small." | Under 30 vendors, a spreadsheet is probably fine. At 67, Lakefront still lost about four hours a week |
| "We need approval." | Build the business case together; the Halloran story is the fastest route to a CFO |

---

## 8. Language customers use

The ranked signal-word list lives in [`brand-voice.md`](brand-voice.md). Verbatim lines most useful for ICP work:

- "I used to chase vendors. That was the job. Now I manage exceptions. They're different jobs." (Paul Bergman)
- "I was the system. I was literally the only thing standing between our suppliers and lapsed certs." (Shelly Okafor)
- "My spreadsheet was probably fine when we had 60 vendors. By the time we got to 180, it was a full-time job on its own." (Karen Wolfe)
- "There's a cliff somewhere in the middle." (Jasmine Tate)
- "Compliance gaps don't fail quietly in construction. They fail as a project stopping at 7am." (Rachel Halloran)
- "My procurement manager sold it as a time-saving tool. I approved it as a risk management tool. We were both right." (Derek Chu)

**Vocabulary by vertical:** "vendor" is the default umbrella term in general copy. In vertical copy, lead with the local term: suppliers (manufacturing, food & beverage), carriers (logistics), subcontractors or subs (construction), vendors and subcontractors (facilities management).

---

## 9. Regulatory vocabulary: US and Canada

| Area | US term | Canadian equivalent |
|---|---|---|
| Food safety regulator | FDA, USDA | CFIA; Safe Food for Canadians Regulations (SFCR) |
| Food safety schemes | SQF, BRCGS, FSSC 22000, HACCP | The same GFSI-benchmarked schemes apply; preventive control plans under SFCR |
| Carrier authority | FMCSA operating authority (USDOT / MC number) | National Safety Code (NSC) number; Ontario CVOR |
| Workers' compensation | Workers' comp certificate | WSIB clearance certificate (Ontario); WorkSafeBC clearance letter (British Columbia); other provincial boards |
| Workplace safety | OSHA compliance | Provincial occupational health and safety legislation (for example Ontario's OHSA); COR (Certificate of Recognition) programs |
| Insurance | COI, general liability | Certificate of insurance, commercial general liability (same documents) |
| Supply chain due diligence | US import and due diligence rules | Fighting Against Forced Labour and Child Labour in Supply Chains Act |
| Quality management | ISO 9001, 14001, 45001, IATF 16949 | Same |

These are provided for copy vocabulary. Confirm specifics with a compliance specialist before publishing regulatory claims. Use US spelling throughout.

---

## 10. Segment signals

- NPS +47 overall (Q1 2026); +61 food & beverage; +29 for 500+ employee accounts before SyncBridge GA.
- NPS by tenure: +31 at 0–3 months, +61 at 12+ months. Value deepens after the first renewal cycle.
- 4.8% of customers churn in the first 90 days, mostly before their first self-completed renewal cycle.
