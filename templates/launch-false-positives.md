# Launch Success & False-Positives — <program> — <YYYY-MM-DD>

> Pattern **#6**: lock the success metric *before* launch, and pre-register what would *look* like success but isn't.

## Primary success metric
- **Metric:** <a rate or composite tied to value, not a vanity count>
- **Target:** <number + by when>
- **Leading indicator:** <the early proxy you'll watch>

## Guardrail metrics (must not regress)
- <e.g. error rate, latency, support volume> — threshold: <x>

## False positives — "what would fool us"
| # | Looks like success because… | …but it's fake if | Evidence that tells real from fake |
|---|---|---|---|
| 1 | <e.g. launch-day spike> | <retention decays within 7 days> | <cohort retention curve> |
| 2 | <e.g. network/insider signups> | <signups skew to known contacts> | <referrer / domain breakdown> |
| 3 | <e.g. high signup, low use> | <activation rate is low> | <signup→activation funnel> |

## Readout checklist (post-launch)
- [ ] Did we hit the primary metric — and is it real (not a listed false positive)?
- [ ] Did any guardrail regress?
- [ ] Update `registers/decision-log.md` and feed lessons into `templates/retro-learning-loop.md`.
