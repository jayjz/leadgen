# PERMIT-01 — PHASE 3 raw subagent report (competitive/substitute analysis)

Observation date: 2026-10-19. Received 2026-10-19 18:36 EDT.

## Category discipline

Five distinct services, not interchangeable:

| Category | What the buyer gets | Example vendors |
|---|---|---|
| **Status monitoring** (pure play) | Alerts when a filed permit's status changes; read-only, no filing | None found as a standalone paid product for contractors |
| **Permit filing** | Preparation, assembly, and submission of permit applications | PermitFlow (software+service), some expediters |
| **Expediting** | Human-driven acceleration: jurisdiction knowledge, reviewer relationships, corrections management, phone/office work | Traditional expediters (permitplace.com marketplace), regional firms |
| **Inspection booking** | Scheduling, cancelling, and result retrieval of inspections | Municipal portals (Cloudpermit et al.), some expediters, PermitFlow |
| **Regulatory advice** | Code interpretation, compliance strategy | Code consultants, architects/engineers — not permit software |

## (a) Competitive/substitute table

| Vendor/product | Category | Published features (verbatim-sourced) | Published price | Coverage | What remains manual | Source URL |
|---|---|---|---|---|---|---|
| PermitFlow | Filing + monitoring + expediting (hybrid software/service) | AI-powered application prep, real-time tracking, instant alerts on status changes / correction requests, municipal coordination handled by platform, expert pre-submission review, integrations: Procore, Autodesk Construction Cloud, Slack, Google Drive, Teams | **Not published** — "project-based pricing model tailored to construction volume and jurisdiction complexity"; custom quote/demo required; no public self-service plan, no free trial | Nationwide; serves retail, F&B, real estate; contractor-facing | Initial setup/sync with existing workflows; availability "may vary by specific local municipality" | https://softwarefinder.com/construction/permitflow ; https://nerdisa.com/permitflow/ |
| Traditional permit expediters (via permitplace.com marketplace) | Expediting (human) | Own full permit process end-to-end, call building departments, manage corrections, jurisdiction-specific code knowledge, reporting/tracking | **Published ranges**: residential $1,500–$5,000; commercial TI (3–5 trades) $4,000–$8,500; simple signage ~$1,500; complex commercial $7,500–$12,500+; very complex $10,000+ (permit fees extra, passed through at cost) | Per-firm; national firms sell rollout programs; local firms jurisdiction-specific | Client must supply plans/documents; pricing per project; software "cannot replace relationships with plan reviewers" | https://permitplace.com/best-permit-expediters/ ; https://www.permitdivision.com/blog/permit-expediter-vs-diy-permitting |
| Boston-area permit pullers (e.g., Permit Puller / movingpermits.com, Boston Permits / bostonpermits.com) | Filing (narrow niche: street-occupancy/moving permits) | Moving permit acquisition, street-occupancy bond handling ($200 bond arrangement fee seen on one Boston form) | **Not published** for the pulling service itself; one sample form shows $200 bond fee and $250 route-survey fee | Boston / City of Boston | Client provides dates, routes, entity name | http://www.movingpermits.com/ ; https://form.jotform.com/200246267416047 |
| Procore | Construction management (manual tracking workaround, NOT a permit-status monitor) | Community-confirmed workarounds: tracking permits via Tasks tool, Excel in Documents tool, Observations, Action Plans — i.e., **manual** status tracking; no automated municipal status ingestion published | **Not published** — annual subscription priced on customer's Annual Construction Volume (per investor factsheet), not per user | North America, UK, AU, Middle East | Everything permit-status: users manually check town/city websites ("We don't track permit status thru Procore. This can be done thru most town/city web sites.") | https://community.procore.com/s/question/0D52T00005YBDxgSAH/best-practices-on-how-to-track-permit-status-co-holds-and-which-procore-tool-is-best-to-use-to-track ; https://construbim.com/bim-software-cde.html |
| Autodesk Construction Cloud | Construction management (generic compliance/status tracking, no municipal permit integration published) | Listed features include "Permit Management," compliance/status tracking — at generic CDE level; no documented municipal-portal status ingestion | Published per-user list prices exist on Autodesk's store (Build from ~$400+/user/yr typical; I will not state a number not re-verified today — **not confirmed in this session**) | Global | Any actual municipal status detection is manual | https://www.softwareworld.co/compare/procore-vs-autodesk-construction-cloud/ |
| Cloudpermit (municipal portal vendor — free substitute) | **Free built-in notification (substitute for paid monitoring)** | Automatic **email notifications** on every status change, correction request, inspection result; in-app status tracking; applicant communication channel | Free to applicants (paid by municipalities) | Canada-focused; used by Brockville, Bluewater, Anmore, Kenora in sources | Applicant must register an account; notifications are email only; no multi-jurisdiction aggregation | https://support.cloudpermit.com/support/solutions/articles/67000717971-email-notifications-in-the-approval-application-process ; https://anmore.com/building-development/building-renovating/building-guide/cloudpermit/ |
| Shovels (permit-data platform) | Data/intelligence (lead-gen, NOT contractor status monitoring) | 170M+ standardized permit records, 3M+ contractors, contractor match rates 60–80%, REST API, CRM integrations, twice-monthly updates, approval dates/status included | **Not published** — pricing page promises low-volume plan; enterprise/API quotes | Nationwide jurisdictions | Not a contractor-facing tracker; records update "within days" of issuance, not real-time; no alerting product for the contractor's own permits | https://www.shovels.ai/ ; https://docs.shovels.ai/docs/foundations-building-blocks ; https://www.shovels.ai/building-materials |

## (b) Three analytical framings

**1. Jobs-to-be-Done.** The small contractor's actual job isn't "receive permit alerts" — it's "get the job started on schedule without babysitting a portal." Existing solutions already hire for most sub-jobs: Cloudpermit-style portals auto-email status changes (free); Procore-task/Excel workarounds and admin staff cover the bookkeeping; expediters get hired when the real pain is *speed of approval*, not *awareness of status*. A monitoring operator only wins if there's a sub-job nobody covers: cross-municipality aggregation in one view, or proactive detection where portals don't email (e.g., inspection-result windows or correction deadlines that require log-in). That gap is narrow and municipality-specific.

**2. Transaction-cost analysis.** The transaction costs a monitoring operator removes: (a) periodic portal-checking labor, (b) latency cost of learning about corrections, (c) coordination across 5 towns. The evidence shows (a) is already ~free where portals email applicants (Cloudpermit auto-notifies on every change); (b) expediters sell *resolution* of corrections, not just detection — detection alone leaves the highest-cost step (the response) still on the contractor; (c) multi-jurisdiction aggregation is the one genuine friction, but each town's portal has different fields/auth, so the operator inherits the worst transaction costs — brittle scraping, login dependencies, and false-negative liability — which scale badly for a solo operator.

**3. Porter's Five Forces (solo monitoring operator).**
- **Buyers (contractors):** strong — low switching cost to free portal emails; price sensitivity high for small contractors.
- **Suppliers (the municipalities/portal vendors):** strong — they control the data, change the portals, add built-in notifications (Cloudpermit), and can block automated access via ToS/robots.
- **Substitutes:** strong — free portal email alerts, Excel/Procore-manual, municipal emails, permit coordinators, and PermitFlow's bundled tracking all substitute for pure monitoring at zero or bundled marginal cost.
- **Rivals:** moderate — PermitFlow bundles monitoring into a full filing+expediting product with real-time alerts; expediters ($1.5k–$5k+ per project) sell a strictly better bundle for urgent jobs.
- **New entrants:** easy — a Shovels-style API plus a dashboard is replicable; no moat in read-only monitoring.

## (c) Net assessment: duplication vs. defensible incremental value

**Duplicated (free/cheap already covers it):** status-change awareness where portals auto-email (Cloudpermit model); generic status bookkeeping (Procore tasks, Excel); correction *resolution* (expediters, PermitFlow).

**Potentially defensible slivers of incremental value for a solo operator:**
1. **Multi-jurisdiction aggregation** — one dashboard across 5 towns' portals, since no free tool aggregates them. Value depends entirely on read access being automatable without violating portal ToS.
2. **Detection in no-email portals** — towns whose portals require log-in to see changes without auto-notification; a human-reviewed check cadence could beat manual checking.
3. **Correction-deadline triage** — surfacing "reviewer asked for missing document on date X, no response logged" as an actionable nudge rather than a raw status ping.

**Net:** a pure status-monitoring product is **mostly duplicative** — the free built-in municipal notifications, PermitFlow's bundled real-time alerts, and expediter's relationship-driven acceleration bracket it from both ends. The only defensible wedge is a *human-reviewed, multi-town aggregation + deadline triage* service, which is a low-margin labor business with automation-permission risk on every portal — not a product moat. Any pricing test should benchmark against the free substitute (portal email alerts) as the control, not against expediters.

## Evidence hygiene (per original brief)
- All vendor facts from vendor's own site or named third party unless marked "not published." No prices or customers invented.
- Observation date 2026-10-19.
