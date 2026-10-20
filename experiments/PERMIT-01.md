# PERMIT-01 — Municipal Permit Monitoring Feasibility

**Status:** investigation complete, 2026-10-19. **Verdict: NO-GO.**
**Investigation home:** `~/workspace/leadgen/` (the mission's `C:\Dev\leadgen` path does not exist on this machine; substitution recorded, not hidden). No pre-existing PA-01, META-01, AGENTS.md, README, or HYPOTHESES files were found at investigation start; nothing was overwritten or mixed.

## Central hypothesis

Contractors experience recurring, costly administrative friction tracking permit reviews, missing submissions, inspection status, corrections, and municipal decisions across fragmented portals. A paid service run by a solo operator using Muse-assisted workflows is viable **only if** it can (a) capture permission-accessible information reliably, (b) surface actionable changes sooner or more accurately than existing alternatives, and (c) save enough billable time or delay cost that a buyer willingly pays.

## Falsifiers (each individually sufficient to reject the hypothesis as framed)

- **F1 — Access.** Status fields, status history, or update timestamps cannot be observed without an account on the target portals, OR automation permission is explicitly restricted. *Observed: status fields UNKNOWN on all five portals unauthenticated; OpenGov and MapsOnline actively deny unauthenticated fetches (403); automation permission NOT ESTABLISHED on any portal.*
- **F2 — Substitutes.** A free or bundled alternative already delivers timely status-change awareness to the buyer. *Observed: Lowell's portal sends system update emails from donotreply@lowellma.gov; modern portals (Cloudpermit model) auto-email on every change; PermitFlow bundles real-time alerts; Portafor sells hourly alerts.*
- **F3 — Demand.** No contractor demonstrates willingness to pay for third-party status monitoring (as distinct from filing, expediting, or scheduling). *Observed: zero MA contractor accounts; zero willingness-to-pay evidence; the strongest documented pain is inspection-queue waiting, which monitoring cannot fix.*
- **F4 — Coverage.** Key permit/inspection workflow events never enter the online portal. *Observed: Lowell's new-construction and remodel permits are in-person only; Tewksbury inspection scheduling is phone-only.*

All four falsifiers are at least partially triggered. The hypothesis as framed is rejected for the five-town scope.

## Gates (that a GO would have required — none cleared)

| Gate | Required evidence | Result |
|---|---|---|
| G1 Read access | Public, automatable read access to status fields on ≥3 of 5 portals with automation explicitly allowed | FAIL — no portal grants explicit automation permission; record-level data behind logins/403s |
| G2 Observable change | ≥1 documented, previously unknown actionable status change detectable by an unauthenticated operator | FAIL — no status fields observed at all |
| G3 Pain | ≥3 primary contractor accounts in the service area documenting repeated manual checking with time/financial consequence | FAIL — none in MA; closest is an IL investor's manual calls |
| G4 Beating substitutes | Service faster/more accurate than free portal notifications or incumbent trackers | FAIL — free municipal emails and Portafor/PermitFlow already cover detection |
| G5 Payer | A named buyer role confirms the event they'd pay to know about and the deliverable they'd accept | FAIL — unverified; no contractor engagement authorized or performed |

## Explicit risks

1. **Automation-permission risk.** Public visibility ≠ permission. Every portal is "not established," not "allowed." Automated checking risks ToS violations and IP/user-agent blocking — and three of five portals already 403 unauthenticated fetches.
2. **False-negative liability.** A paid monitor that misses a correction notice causes the exact loss it claims to prevent. The dead Dracut portal URL (stale third-party directory, 2026-09-16 "verified") is direct evidence of how easily monitoring goes silently stale.
3. **Supplier power.** Municipalities and portal vendors control the data, add built-in notifications (shrinking the gap), and can block automated access. No moat exists in read-only monitoring.
4. **Wrong-job risk.** The dominant documented contractor pain is inspection scheduling *capacity* (month-long queues, 7 trade inspectors across 2 inspections/week), not status-change *detection*. Monitoring solves neither.
5. **Buyer economics.** Small contractors are price-sensitive, switching cost to free portal emails is ~zero, and larger contractors internalize this as a permit coordinator or buy PermitFlow/expediters for projects that matter.

## What survives (narrow, unverified)

- **Multi-jurisdiction aggregation + correction-deadline triage** as a *human-reviewed labor service* (not an automated product): one contractor dashboard across 5 towns' portals, surfacing "correction requested on date X, no response logged." This is a low-margin service business, not a product, and it still needs customer-authorized accounts on every portal.
- **Lead-generation data** (permits.llc model) is a *different job* from status monitoring — selling newly filed permit data to trades who want jobs, not tracking status for the filer.

## Next experiment (falsifiable, no build)

**Payer-first pricing test.** Do not build. Recruit 5 small MA contractors for a 15-minute conversation each and ask for a signed letter of intent: "Would you pay $X/month for a weekly human-reviewed email listing every permit you hold in Lowell, Chelmsford, Dracut, Tewksbury, Billerica plus any reviewer-requested document or deadline?" Falsification condition: fewer than 2 of 5 sign, or the median named price is below the operator's per-customer labor cost. No outreach was authorized or performed in this run; this experiment requires explicit approval.

## Deliverables

- `research/permit-01-feasibility-2026-10-19.md` — primary-source analysis, portal matrix, competitive comparison, recommendation
- `research/permit-01-evidence.csv` — source/verification log
- `evidence/permits/README.md` — evidence standards
- `evidence/permits/phase{1,2,3}-*-raw-report.md` — raw research reports
