# Agent instructions — leadgen

## Mission
Discover whether permission-based, AI-assisted distribution creates incremental, independently verifiable revenue. This repository is research infrastructure until evidence warrants software.

## Source of truth
Read `README.md`, `experiments/HYPOTHESES.md`, and the relevant original in `research/` before making recommendations. Keep the **Pennsylvania procurement** and **Meta/Lowell** studies separate. Existing files under `research/` are historical inputs: preserve names, bytes and original conclusions unless explicitly asked to amend; add new dated analysis instead.

## Epistemic contract
Distinguish `claim`, `source observation`, `inference`, `test hypothesis`, `verified outcome`. Record canonical URL, observation date, access method, source limitations, and contradictory evidence. No fabricated quotes, payments, posting timestamps, permission, platform/API access, or legal conclusions. A source snippet is not a directly inspected page. A customer statement is not settlement proof. Never count duplicates as distinct demand.

## Execution boundaries
Default to **research-only**. Do not send DMs/emails, join groups, publish, buy, book, scrape authenticated content, access accounts, collect personal data, or spend money without a task-specific explicit instruction. Verify current platform terms and jurisdiction-specific obligations before any live fieldwork. Admin permission does not imply API/scraping permission. Do not retain unnecessary identifying data or secrets in Git.

## Working method
1. State decision question, scope, geography, measurable falsifier.
2. Inspect existing evidence and contradictions before searching.
3. Use official primary material and current developer documentation for platform/API assertions.
4. Report sampled data as sampled, never market prevalence.
5. Prefer a minimal, reversible test of willingness to pay and attribution; distinguish operator fee from underlying transaction value.
6. Log negative outcomes, costs, operator minutes, missingness and channel source.
7. Recommend automation only when repeated paid work exposes a measured bottleneck.

## Artifacts and review
Keep original research in `research/`. Put investigation decisions in `experiments/`. Put only **redacted** evidence or hashes/pointers in `evidence/`; no payment documents, names, address details or access codes in public Git. Prefer plain Markdown/CSV; no framework, database, cloud deployment or agent swarm without demonstrated need. Keep edits scoped. Verify links, CSV field consistency, `git diff --check`, and changed-file summaries. Do not push to GitHub unless explicitly asked.

## Output format
Decision first; what is observed, what is assumed, strongest counterargument, next falsifying test. Brevity; use Mermaid when it clarifies causality.

## Available skills
Use `.agents/skills/source-audit/SKILL.md` for evaluating evidence; `market-mechanism/SKILL.md` for ranking economic mechanisms; `experiment-design/SKILL.md` for preregistering tests. Read a skill only when its trigger applies.
