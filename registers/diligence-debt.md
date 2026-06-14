# Diligence Debt Register

> Pattern **#7**: skipping a gate (security review, load test, accessibility pass, validation) is allowed under pressure — but **never silently**. Each skip becomes a tracked debt item with an owner and a pay-back-by date. Visible cuts get paid back; silent ones don't.

| ID | Date | Program | Gate skipped | Why skipped | Owner | Pay-back by | Status |
|---|---|---|---|---|---|---|---|
| DD-001 | <YYYY-MM-DD> | <program> | <e.g. load test> | <deadline pressure> | <name> | <date> | open / paid / accepted-risk |

**Rule:** work may ship past a skipped gate, but it does not get waved through — it gets a row here first. Review open debt at every phase-gate and portfolio review.
