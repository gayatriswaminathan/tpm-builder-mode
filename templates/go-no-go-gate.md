# Go/No-Go Gate — <program / launch> — <YYYY-MM-DD>

> Pattern **#1 forced verdicts**: the verdict is a closed set with one accountable owner. No soft-green.
> Verdict ∈ { **GO** · **NO-GO** · **GO-WITH-CONDITIONS** }. "GO-WITH-CONDITIONS" requires the conditions written below with owners and dates — it is not a soft yes.

## Decision owner
<single name — the person accountable for the call>

## Readiness criteria

| # | Criterion | Status | Confidence | Evidence |
|---|---|---|---|---|
| 1 | <e.g. security review complete> | ✅ / 🟡 / 🔴 | ✅ / ⏳ | <link> |
| 2 | <e.g. rollback tested> | | | |
| 3 | <e.g. success metric + monitoring wired> | | | |
| 4 | <e.g. support/comms ready> | | | |

## Open risks (link the anti-pattern register, #4)
- <risk> — likelihood / impact — mitigation — owner

## Verdict
**< GO / NO-GO / GO-WITH-CONDITIONS >**

### Conditions (only if GO-WITH-CONDITIONS)
| Condition | Owner | Met-by date |
|---|---|---|
| <must be true before/at launch> | <name> | <date> |

## What could make this the wrong call
<one paragraph — pattern #11.>

## Logged
- This gate is recorded in `registers/decision-log.md` with evidence cited (pattern #13).
