# Evidence and provenance

This folder holds **future** redacted first-party verification. Historical public-source ledgers stay in `research/`.

## Levels
`L0 claim` (unverified) → `L1 inspected source` → `L2 independently cross-checked` → `L3 written counterparty agreement/permission` → `L4 documented performance or buyer outcome` → `L5 reconciled settled payment`.

Levels describe **what was verified**, not whether a business is good. A public request can be L1 for existence and L0 for willingness to pay. Mark each claim separately.

## Minimum record
`evidence_id | track_id | claim | source_url_or_private_ref | observed_at | event_at | access_method | level | corroboration | counterevidence | uncertainty | redaction_status | reviewer`

For source-publication advantage, separately track document date, last successful absence, first confirmed presence, incumbent channel first alert, eligibility deadline. Failed fetches are unknown, not absence.

For transactions, separately track buyer payment, provider settlement, operator invoice, operator **settled** cash receipt, refunds, all costs and all hours. Do not store financial documents or personal contact information in this public repo; use access-controlled storage and record opaque references or salted/non-reversible digests where appropriate.

## Review protocol
- Resolve URLs and capture page/document section and access limitations.
- De-duplicate cross-posted requests and serial-number reissues.
- Record selection biases and what wasn't observable.
- Keep negative and excluded observations.
- Never treat historical cases as current leads.
