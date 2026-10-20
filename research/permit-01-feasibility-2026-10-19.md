# PERMIT-01 Feasibility Report — Municipal Permit-Status Monitoring for Small Contractors

**Observation date:** 2026-10-19. **Method:** adversarial commercial feasibility investigation. Primary sources (official municipal pages, unauthenticated portal inspection, firsthand contractor accounts, vendor sites) preferred; search snippets, third-party directories, and vendor marketing labeled as such. **Verdict: NO-GO.**

Investigation home is `~/workspace/leadgen/` (mission's `C:\Dev\leadgen` does not exist on this Linux VM; substitution recorded). No AGENTS.md, README.md, HYPOTHESES.md, or PA-01/META-01 material existed at start; all artifacts are newly created and separately identified.

---

## 1. Five-portal matrix (all findings source-linked in the evidence CSV)

| Municipality | Official landing | Portal vendor | Public (no login) | Requires account | Status fields / history / timestamps | Alerts / export / API (public docs) | Automation permission | Key barriers |
|---|---|---|---|---|---|---|---|---|
| Lowell | https://www.lowellma.gov/1631/Online-Permitting | Tyler Munis Citizen Self Service | Checklists, forms, fees, delay causes, contact | Applying; Contractor/Customer ID (CID) issued by staff | **UNKNOWN** — cookie/JS interstitial blocked inspection; record-level status not observable | YES — applicant emails from donotreply@lowellma.gov; no export/API found | Not established | Cookie interstitial; docs subdomain unreachable; **new construction and remodel/alteration are in-person only** (never in portal) |
| Chelmsford | https://www.chelmsfordma.gov/664/Online-Permits | PermitEyes (Full Circle Technologies / Schneider Geospatial) | Permit type list, procedures, contacts; public pages exist on platform (dog-license search observed without login) | Applicant status tracking (town links only the login page) | **UNKNOWN** — no building-permit public view located | None documented | Not established | Town surfaces login link only |
| Dracut | https://www.dracutma.gov/186/Building-Department | OpenGov (ViewPoint Cloud), current URL dracutma.viewpointcloud.com | FAQs, fee schedules, checklists, zoning guidance | Record-level search/status | **UNKNOWN** | None documented | Not established (terms page 403) | Portal 403s unauthenticated fetches; portal link buried in FAQs; **stale third-party URL** (dracutma.portal.opengov.com) is dead |
| Tewksbury | https://www.tewksbury-ma.gov/Directory.aspx?did=9 | OpenGov (ViewPoint Cloud), current URL tewksburyma.viewpointcloud.com | Staff directory, hours, permit FAQs | Record-level search/status | **UNKNOWN** | None documented | Not established | Portal 403s unauthenticated fetches; **all inspections must be called in by phone** — key events invisible to any portal monitor |
| Billerica | https://www.billerica.gov (Building Dept.) | PeopleGIS Simplicity (MapsOnline), public page at mapsonline.net | Public building-permits page exists (per secondary sources, no account needed) | Applying (contractor registration) | **UNKNOWN** — page 403'd text fetch | None documented | Not established | 403 on fetch; town site migration may strand links |

**Cross-cutting:** (1) automation permission is **not established** on any portal — no explicit grant, no explicit prohibition retrieved; public visibility does not imply permission; (2) technical access is unevenly gated — OpenGov and MapsOnline actively deny unauthenticated fetches, Munis requires cookies/JS; (3) status fields, history, and timestamps are unobservable without accounts in every case; (4) the one documented proactive notification is Lowell's own applicant emails — a free substitute.

## 2. Commercial pain — what was actually found

**Three strongest documented pain points (all with limitations):**

1. **Repeated manual status checks because the contractor never reported status (Oak Park, IL investor, firsthand).** Over ~6 weeks the investor called the city multiple times, discovering corrections sent 3/25 that the contractors never relayed and permits never submitted. Workaround: bypass the contractor and call the city. Source: biggerpockets.com forum thread (≈ Aug 2025). *Limitation: IL, not MA; an investor, not a contractor; documents manual checking, not demand for a monitoring service.*
2. **Month-long inspection queues destroying holding costs (Nashville contractor, firsthand).** Electrical/trade inspections "started to take over a month"; on 12–15% hard-money financing, "sitting on a project for a month not being able to do absolutely anything" — workaround was skipping permits entirely. Source: biggerpockets.com (≈ Nov 2025). *Limitation: pain is inspection scheduling capacity, which monitoring cannot fix.*
3. **Labor paid to wait for trade inspectors (LA GC, firsthand, dated).** Seven trade inspectors across two inspections per week; "a 10k job can turn 20k with permits" because a worker sits waiting; workaround is running parallel jobs. Source: biggerpockets.com (≈ 2017–2018). *Limitation: dated; again scheduling, not detection.*

A vendor baseline (signedoff.io, 2026-04-02) claims GCs run 20–40 permits across 3–5 portals, spending 2.5–5 hrs/week checking, with correction notices unnoticed ~10 days and reinstatement at 50–100% of the permit fee — but it is **vendor marketing**, figures uncited, and must not be used as evidence. No Massachusetts-specific contractor account was found. No contractor willingness-to-pay for third-party monitoring was documented anywhere.

**Three strongest counterarguments:**

1. **Free built-in notifications already cover detection.** Lowell's portal sends system application-update emails; modern municipal portals (Cloudpermit model) auto-email on every status change, correction request, and inspection result; TEKConnectGov pushes SMS+email. Where this exists, a paid monitor duplicates a free municipal feature.
2. **The niche is already occupied.** PermitFlow (Series B, ~$90.6M funding per third-party data) bundles real-time tracking and alerts into filing/expediting software embedded in Procore and Autodesk; Portafor sells hourly permit alerts in 6+ US cities with a 30-day free trial. Both figures are vendor-claimed, but the existence of direct substitutes is documented.
3. **The job is not status detection.** The dominant documented pain is inspection *scheduling and queue capacity*, plus correction *resolution* — expediters and dedicated permit coordinators (real hiring postings exist) sell those jobs. Monitoring reports the queue; it does not shorten it.

## 3. Competitive comparison (condensed; full table in evidence)

| Offering | Job | Price posture | Threat to a monitoring operator |
|---|---|---|---|
| Free municipal email alerts (Lowell, Cloudpermit-type) | Status detection | Free (paid by municipalities) | Duplicates the core detection function at zero marginal cost |
| Portafor | Hourly permit alerts | Vendor-claimed free trial; pricing not independently verified | Direct substitute for automated alerts |
| PermitFlow | Filing + tracking + expediting | Not published (custom quotes) | Superior bundle; venture-funded; Procore/Autodesk integrations |
| Expediters (permitplace.com) | Approval acceleration | $1,500–$5,000+ residential; $4,000–$12,500+ commercial | Sell the outcome (faster approval), not awareness |
| Procore/Excel/manual + permit coordinators | Status bookkeeping | Internal labor cost | Established workaround; coordinators are the human alternative |
| permits.llc permit-data plans | Lead generation | Paid (not independently verified) | Different job (selling new-permit data to trades), not status tracking |

**Net:** a pure status-monitoring product is squeezed from both ends — free municipal notifications below, PermitFlow/expediters above — with no demonstrated contractor demand in the middle.

## 4. Muse feasibility (Phase 4, verified this session)

- **Muse Code CLI: not installed in this workspace** (no `muse`, `code`, or `claude` binary; official installer at dev.meta.ai — installing it was outside this mission's stop conditions). Muse Code is a separate product from the consumer Muse agent running this investigation: a local terminal coding agent with shell access, approval-gated tools, subagent fan-out, and session event logs — it has no built-in live browser; web access is via the user's own network tooling and approved skills.
- **This session verified:** `browser.search` (web retrieval), `browser.open` (page text fetch), and `browser.browse` (live browser navigation — opened lowellma.gov successfully, no cookie banner or bot check on the homepage) all work.
- **What Muse can demonstrably do in this workspace:** read public web pages and search results (with citations), maintain a local evidence trail in files/CSVs, draft reports and pilot scripts, run read-only shell commands, and drive a live browser session under approval gates.
- **What is blocked or requires the customer:** any authenticated portal access (requires the customer's own account credentials via Secure Vault); any automated recurring checking (stop conditions prohibit scheduled monitoring and scrapers); any outreach to contractors.
- **Do not equate** Muse Code's terminal access with the consumer Muse cloud browser — they are different products, different sandboxes, different permission models.

## 5. Payer-first investment decision

- **Economic buyer (hypothesized, unverified):** operations manager or owner of a small GC doing 10+ concurrent projects across 2+ of these towns. Permit coordinators exist at larger firms, so the buyer is the too-small-to-hire-a-coordinator GC — precisely the buyer least able to pay for a service.
- **Current substitute:** free portal applicant emails + manual portal checking + phone calls to town hall.
- **Event the buyer would pay to know about:** "reviewer requested a document/correction on date X and no response has been logged" — deadline triage, not raw status pings.
- **Effective deliverable:** a weekly human-reviewed email listing every held permit, its last known state, and any reviewer-requested action with its deadline. This is a labor service, not a scalable product.
- **Willingness to pay:** explicitly unverified — no contractor was contacted (outreach unauthorized). No invented prices; only a falsifiable pricing test is proposed (see below).
- **Compliance and liability:** automation permission not established on any portal; three portals already block unauthenticated fetches; a missed correction under a paid contract creates direct liability. Any pilot must use customer-authorized accounts and human review.

## 6. Verdict and next step

**Verdict: NO-GO** for selling permit-status monitoring to small contractors in this five-town scope. The central hypothesis fails on all three prongs: reliable capture is not demonstrated (status fields unobservable without accounts; automation permission unknown), existing alternatives already deliver detection (free municipal emails, Portafor, PermitFlow), and willingness to pay is entirely unverified — while the best-documented pain (inspection queues) is a problem monitoring cannot solve.

**Single most valuable next validation step:** the payer-first pricing test — 5 conversations with small MA contractors, asking for a signed letter of intent at a named monthly price for a weekly human-reviewed permit-status-and-deadline email. Falsification condition: fewer than 2 of 5 sign, or median named price below operator labor cost. Requires explicit approval before any outreach.
