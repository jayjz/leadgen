# Evidence standards — evidence/permits/

## Scope and integrity

This directory holds the PERMIT-01 evidence trail. It is a **research investigation**, not authorization to develop, operate, or sell anything. No accounts were signed in, no forms submitted, no scrapers run, no records enumerated, no contractors contacted.

- Existing repository material was not present at investigation start (no PA-01, META-01, AGENTS.md, README.md, or HYPOTHESES.md found); PERMIT-01 files are separately identified and do not mix with other investigations.
- The mission's `C:\Dev\leadgen` path does not exist on this machine; the investigation was conducted at `~/workspace/leadgen/`. This substitution is recorded, not hidden.

## Evidence tiers

| Tier | Meaning | Examples in this investigation |
|---|---|---|
| Primary | Direct observation or firsthand account, date-stamped | Unauthenticated text fetch of official municipal pages; live browser load of lowellma.gov; firsthand contractor forum posts |
| Secondary | Credible third-party reporting of primary material | Search snippets of town minutes; permits.llc portal mappings cross-checked against town sites |
| Vendor / marketing | Vendor's own claims about its product | signedoff.io baseline figures; PermitFlow/Portafor/permits.llc feature and pricing claims |
| Speculative | Inference, clearly labeled as assumption | Any frequency, cost, or willingness-to-pay figure not sourced |

Rules applied: public visibility ≠ automation permission; a failed fetch (403, cookie interstitial) is recorded as a barrier observation, not worked around; third-party portal URLs are treated as stale until confirmed against the town's own site; dated, secondhand, or geographically remote accounts are flagged as limitations; unknowns remain unknown.

## File layout

| File | Contents |
|---|---|
| `README.md` (this file) | Evidence standards and layout |
| `phase1-portal-raw-report.md` | Raw Phase 1 portal-inspection report: per-municipality matrix + source list |
| `phase2-pain-raw-report.md` | Raw Phase 2 pain/counterevidence report with per-example fields |
| `phase3-competitive-raw-report.md` | Raw Phase 3 competitive/substitute report with vendor table and JTBD/transaction-cost/Five Forces |
| `../research/permit-01-evidence.csv` | Machine-readable source/verification log: source ID, municipality, source type, URL, access method, observation time, claim, evidence tier, limitation, verification status |
| `../research/permit-01-feasibility-2026-10-19.md` | Synthesized feasibility report |
| `../experiments/PERMIT-01.md` | Hypothesis, falsifiers, gates, risks, next experiment |

## Verification log conventions (CSV)

- `observation_time` is always `2026-10-19` EDT unless noted.
- `access_method`: text fetch, search snippet, live browser, or vendor claim (for marketing material).
- `verification_status`: `confirmed` (direct observation), `cross-checked` (verified against a second independent source), `unverified` (single source or snippet), `conflicted` (sources disagree — e.g., permits.llc's Dracut URL vs the live page).
- Claims about automation permission are recorded as `not established` everywhere; no portal yielded an explicit grant or prohibition.
- No claim of contractor willingness to pay, fabricated permit status, customer interview, or payment appears anywhere in this trail.
