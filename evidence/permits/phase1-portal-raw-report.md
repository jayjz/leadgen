# PERMIT-01 — PHASE 1 raw subagent report (portal inspection)

Observation date: 2026-10-19 (EDT). Method: read-only, unauthenticated text fetch of public pages (browser.open) plus public web search. No logins, no form submissions, no scraping. JavaScript/cookie-gated or 403-denied pages recorded as barriers, not worked around. No municipality required substitution — all five have identifiable portals.

## 1. LOWELL — Tyler Technologies Munis Citizen Self Service
- **Official landing page:** https://www.lowellma.gov/1631/Online-Permitting
- **Vendor:** Tyler Technologies Munis Citizen Self Service (portal at cityoflowellma.munisselfservice.com; help docs at css.lowellma.gov). Vendor ID from the town's own "Online Permitting" link target plus Tyler's documented CSS/Tyler Identity architecture.
- **Online permit types (public, primary source):** Plumbing, Gas, Electrical, Sheet Metal, Roofing, Siding, Windows, Insulation, Solar. **New Construction and Remodel/Alteration permits are NOT online** — in-person at City Hall only. Major coverage gap for any monitoring service.
- **Public (no login):** permit checklists, forms, fee/requirement info, delay-cause list, office contact (978-674-4144, buildingpermits@lowellma.gov).
- **Requires account:** applying requires a Contractor/Customer ID (CID) issued by Development Services, linked to the applicant's account; first-time applicants must contact staff in advance. Record-level status not observable without account.
- **Status fields / history / update timestamp:** UNKNOWN — portal text fetch returned only a cookie interstitial ("Your browser's ability to accept cookies from this domain has been turned off"), and docs subdomain css.lowellma.gov failed (DNS/timeout).
- **Alerts:** YES, applicant-facing — system-generated application-update emails from donotreply@lowellma.gov ("watch for emails from donotreply@lowellma.gov, as our system will send you updates about your application"). Existing substitute notification channel.
- **Export/API/integration:** none documented publicly.
- **Automation classification:** NOT ESTABLISHED (no automation terms retrieved; account + CID gate).
- **Barriers/errors:** cookie/JS interstitial blocks unauthenticated text retrieval; town's own Record Search TIP document unreachable; in-person-only categories invisible online; applicant errors documented by town as "significantly slow down" causes (unlinked CID, missing uploads).
- **Contractor error detection:** compare portal status against direct contact (phone/email); no public alert feed exists for third parties.

## 2. CHELMSFORD — PermitEyes (Full Circle Technologies, Inc.)
- **Official landing page:** https://www.chelmsfordma.gov/664/Online-Permits
- **Vendor:** PermitEyes, © Full Circle Technologies, Inc. (portal footer). Privacy policy published by Schneider Geospatial (Full Circle's parent): https://www.schneidergis.com/fct-privacy-policy.
- **Portal:** applicant login at https://permiteyes.us/chelmsford/loginuser.php. Public page at https://permiteyes.us/chelmsford/publichome.php rendered a dog-license renewal search with no login (fields: Site Address, Dog Owner Name, Dog Name), proving PermitEyes serves public pages without an account. A building-permit public status view for Chelmsford was NOT located; the town links only the login page.
- **Online permit types (public, primary source):** Building (residential, residential-short, commercial, commercial-short), Electrical, Gas, Plumbing, solid fuel appliances, Tent, Sheet metal, Mechanical, Signs, Certificate of inspection, Certificate of occupancy, Shed (200–260 sq ft), Smoke/CO modification, Demolition, Sprinkler/Fire alarm.
- **Public (no login):** permit type list, procedures, department contacts; public search pages exist on the platform.
- **Requires account:** applicant status tracking (Ipswich's PermitEyes directions describe an applicant "Transactions Monitor" behind login — different town, secondary).
- **Status fields/history/timestamp:** UNKNOWN for building permits (not observed).
- **Alerts/export/API:** none documented publicly.
- **Automation classification:** NOT ESTABLISHED. No automation clause found in inspected portal pages; privacy policy covers user data only, not scraping permission.
- **Barriers:** town surfaces only the login link; PermitEyes how-to docs for other towns note Chrome/Firefox-only support (secondary).

## 3. DRACUT — OpenGov (formerly ViewPoint Cloud)
- **Official landing page:** https://www.dracutma.gov/186/Building-Department
- **Vendor:** OpenGov. Town FAQ calls it "our online permitting system (Viewpoint)... Your one stop shop for all Building Department needs (i.e. permits, inspections, etc.)" and links **dracutma.viewpointcloud.com** (official, current).
- **Stale-data finding:** third-party directory (permits.llc) listed Dracut's portal as dracutma.portal.opengov.com, "verified 2026-09-16" — DEAD as of 2026-10-19: the page reads "An OpenGov portal does not exist for a community named 'dracutma'." Concrete evidence of third-party permit-data staleness.
- **Public (no login):** FAQs, fee schedules, checklists, zoning guidance.
- **Requires account:** record-level search/status — OpenGov permitting portals require login to "Search for Records" (secondary: permits.llc guide citing Needham's instructions). Direct inspection blocked: dracutma.viewpointcloud.com returned HTTP 403 to unauthenticated text fetch.
- **Status fields/history/timestamp:** UNKNOWN (not observable).
- **Alerts/export/API:** none documented publicly.
- **Automation classification:** NOT ESTABLISHED (OpenGov terms page also 403 to text fetch; no explicit grant or restriction retrieved).
- **Barriers:** portal link buried in FAQs, not prominent on Building Dept page; 403 bot-mitigation on the portal; stale third-party URL circulating.

## 4. TEWKSBURY — OpenGov (ViewPoint Cloud)
- **Official landing page:** https://www.tewksbury-ma.gov/Directory.aspx?did=9 (Building Department staff directory; town minutes confirm the OpenGov permitting transition).
- **Vendor:** OpenGov/ViewPoint Cloud. Town minutes (2022, primary): "We are transitioning our current permitting system to OpenGov... They will be able to see the process once they submit their application as well as communicate with staff through the program." permits.llc (verified 2026-09-16 vs town site): residential/commercial building, electrical, plumbing and gas permits filed through the ViewPoint Cloud portal at tewksburyma.viewpointcloud.com.
- **Public (no login):** staff directory, office hours (Mon 7:30–4:30; Tue 7:30–6; Wed–Thu 7:30–4:30; Fri 7:30–12:30), permit FAQs.
- **Requires account:** record-level search/status (OpenGov login rule; secondary). Direct inspection blocked: tewksburyma.viewpointcloud.com returned HTTP 403.
- **Operational friction (primary):** "All inspections **must be called in**. Do not use email and do not leave an inspection message on the answering machine." — inspection scheduling is phone-only.
- **Status fields/history/timestamp:** UNKNOWN.
- **Alerts/export/API:** none documented publicly.
- **Automation classification:** NOT ESTABLISHED.
- **Barriers:** 403 bot-mitigation; phone-only inspection scheduling means a key workflow event is invisible to any portal-based monitor.

## 5. BILLERICA — PeopleGIS Simplicity (MapsOnline)
- **Official landing:** Building Department via www.billerica.gov (town moved from town.billerica.ma.us).
- **Vendor:** PeopleGIS Simplicity. permits.llc (verified 2026-09-16 vs billerica.gov): "Building permits in Billerica are filed through PeopleGIS Simplicity... the online permit portal," portal at www.mapsonline.net → https://www.mapsonline.net/simplicity/building_permits.php?client=billericama&use_react=yes.
- **Public (no login):** a public building-permits page exists at the mapsonline.net URL; secondary sources (permits.llc guide) state MapsOnline permit views need no account and support address search. Direct inspection blocked: HTTP 403 on text fetch.
- **Requires account:** applying (contractor registration is required in PeopleGIS towns per Belmont's page — secondary, may not be Billerica-specific); Belmont notes inspection records/permit history in-person only (secondary, Belmont-specific).
- **Status fields/history/timestamp:** UNKNOWN (not observable).
- **Alerts/export/API:** none documented publicly.
- **Automation classification:** NOT ESTABLISHED (no PeopleGIS/MapsOnline terms located).
- **Barriers:** 403 on text fetch; town site migration (town.billerica.ma.us → billerica.gov) may strand old links.

## Source list

| Source URL | Access method | Observation | Claim | Tier | Limitation | Verification |
|---|---|---|---|---|---|---|
| https://www.lowellma.gov/1631/Online-Permitting | text fetch 2026-10-19 | Online permit types; new construction/remodel in-person only; CID required; Record Search tip exists | Portal scope, account gate | Primary | Record-search contents not retrievable (docs host down) | Matches lowellma.gov permit checklists |
| https://cityoflowellma.munisselfservice.com/css/default.aspx | text fetch 2026-10-19 | Cookie interstitial only | Portal requires cookies/JS; unauthenticated text retrieval blocked | Primary (observation) | Could not inspect any status UI | Vendor ID from lowellma.gov link target + Tyler docs |
| https://www.lowellma.gov/2146/Tent-Commercial-Residential-BLDG-B122--- | text fetch 2026-10-19 | donotreply@lowellma.gov update emails; delay causes (missing CID link, missing docs) | Applicant email notifications exist; known application failure modes | Primary | — | Direct quote from page |
| https://www.chelmsfordma.gov/664/Online-Permits | text fetch 2026-10-19 | Full online permit-type list; login link to permiteyes.us | Permit types, portal entry point | Primary | Building-permit public view not linked | Direct quote from page |
| https://permiteyes.us/chelmsford/loginuser.php | text fetch 2026-10-19 | Applicant login; "© Full Circle Technologies, Inc." | Vendor ID; login-gated applicant flow | Primary | Only entry page inspected | Direct observation |
| https://permiteyes.us/chelmsford/publichome.php | text fetch 2026-10-19 | Public dog-license renewal search, no login | PermitEyes serves public pages without account | Primary | Building-permit public view not observed | Direct observation |
| https://www.schneidergis.com/fct-privacy-policy | search snippet 2026-10-19 | Privacy policy covers PermitEyes user-submitted data | Vendor lineage (Schneider Geospatial / Full Circle) | Secondary | Privacy only, no automation terms | Not full-page verified |
| https://www.dracutma.gov/186/Building-Department | text fetch 2026-10-19 | Dept responsibilities; no prominent portal link | Portal discoverability is poor | Primary | — | Direct observation |
| https://www.dracutma.gov/578/Frequently-Asked-Questions | text fetch 2026-10-19 | "online permitting system (Viewpoint)" → dracutma.viewpointcloud.com | Current official portal URL | Primary | — | Direct observation of link target |
| https://dracutma.portal.opengov.com/ | text fetch 2026-10-19 | "An OpenGov portal does not exist for a community named 'dracutma'" | Third-party portal URL is stale/dead | Primary (observation) | — | Direct observation; conflicts with permits.llc "verified 2026-09-16" |
| https://dracutma.viewpointcloud.com/categories/1078/record-types/1006389 | text fetch 2026-10-19 | HTTP 403 access denied | Unauthenticated text retrieval blocked (bot mitigation) | Primary (observation) | Live browser might render; not tested (out of scope) | Error is the finding |
| https://www.tewksbury-ma.gov/Directory.aspx?did=9 | text fetch 2026-10-19 | Staff directory; "All inspections must be called in" | Phone-only inspection scheduling | Primary | — | Direct quote |
| https://tewksbury-ma.gov/AgendaCenter/ViewFile/Minutes/_10202022-2249 | search snippet 2026-10-19 | Transition to OpenGov; applicants "will be able to see the process" | Vendor + applicant visibility intent | Primary | 2022 minutes; transition since completed | Snippet only, not full-page verified |
| https://tewksburyma.viewpointcloud.com/ | text fetch 2026-10-19 | HTTP 403 access denied | Unauthenticated text retrieval blocked | Primary (observation) | — | Error is the finding |
| https://www.mapsonline.net/simplicity/building_permits.php?client=billericama&use_react=yes | text fetch 2026-10-19 | HTTP 403 access denied | Public permit page exists; text retrieval blocked | Primary (observation) | Page contents unverified | URL from permits.llc outlink |
| https://permits.llc/guide/massachusetts-building-permits-public-record-lookup (pub. 2026-09-20) | text fetch 2026-10-19 | Vendor→town mapping; "PermitEyes, PermitLink and MapsOnline through a public view that needs no account, OpenGov after logging in" | Vendor access-pattern classification | Secondary | Marketing-adjacent site; one portal URL already proven stale | Cross-checked vendors against official town pages |
| https://permits.llc/ma/towns/{chelmsford,dracut,tewksbury,billerica,lowell} | text fetch 2026-10-19 | Per-town portal links; verification dates; permit volume tables (e.g., Billerica 10,274 permits/22 mo) | Portal URLs, filing volumes | Secondary | Same site sells "permit alert" data plans — potential competitor; Dracut URL stale | Vendor claims verified against town sites; volumes unverified |
| https://www.belmont-ma.gov/349/Online-Permitting | search snippet 2026-10-19 | PeopleGIS: contractor registration required; inspection records/history in-person | PeopleGIS platform characteristics | Secondary (other town) | Belmont-specific; may not apply to Billerica | Snippet only |
| https://opengov.com/termsofservice | text fetch 2026-10-19 | HTTP 403 access denied | OpenGov terms not retrievable by unauthenticated fetch | Primary (observation) | URL cited in a municipal order form; page exists | Error is the finding |

## Key cross-cutting findings for Phase 5

1. **Automation permission is NOT ESTABLISHED for all five portals.** No portal published an explicit automation/API grant; no explicit anti-scraping clause was retrieved either. OpenGov's own terms page 403'd. PermitEyes's inspected pages carry only a privacy policy link. Public visibility ≠ automation permission everywhere.
2. **Technical access is unevenly gated.** OpenGov portals (Dracut, Tewksbury) and Billerica's MapsOnline page actively deny unauthenticated text fetches (403); Lowell's Munis portal requires cookies/JS. Only PermitEyes demonstrably served public pages to an unauthenticated fetch.
3. **Status fields, history, and timestamps are UNKNOWN for all five** — none were observable without an account in this inspection. The single documented proactive notification channel is Lowell's donotreply@lowellma.gov applicant emails (an existing substitute).
4. **Coverage gaps that break monitoring:** Lowell's new-construction and remodel/alteration permits are in-person only (never enter the online portal); Tewksbury inspection scheduling is phone-only (key workflow events invisible to any portal monitor).
5. **Concrete staleness example:** permits.llc's "verified 2026-09-16" Dracut portal URL is dead — a caution for any plan that relies on third-party portal directories, and evidence of false-negative risk.
6. **Competitor/substitute sighting:** permits.llc itself sells daily permit-data alert plans with contractor name/valuation/house number (lead generation, not status monitoring — distinct job).
