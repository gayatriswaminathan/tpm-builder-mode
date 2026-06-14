# Phase Gates & Boundary Events

> Patterns **#9** (stage-gated lifecycle with explicit *event* triggers) and **#1** (forced verdicts at each gate).

## The phases
`Ideate → Build → Launch → Scale → Sunset`

Adapt names to your program. The point isn't the labels — it's that **each gate has a forced verdict and a defined trigger event.**

## Boundary events (what triggers a gate review)
A review is triggered by an **event**, not a calendar date:
- a program crosses a phase boundary,
- it ships or is sunset,
- a notable incident or notable win,
- the process itself changes.

Keep calendar reviews if you like, but let event-triggered reviews carry the real weight.

## What happens at every gate
1. **Load context** (pattern #8): charter, `scope-and-non-goals.md`, last 3 entries in `decision-log.md`, open `diligence-debt.md`.
2. **Check readiness** against the gate's criteria (`templates/go-no-go-gate.md`).
3. **Force a verdict** — closed set, one owner. No soft-green.
4. **Log it** in `decision-log.md` with evidence cited.
5. **Run the retro** if the gate is also a boundary event (`templates/retro-learning-loop.md`).

## Gate criteria by phase (starter set — customize)

| Phase gate | Must be true to pass |
|---|---|
| Ideate → Build | Problem validated with evidence; scope + non-goals written; success metric drafted |
| Build → Launch | Go/no-go criteria met; security/quality reviews done or debt logged; false-positives pre-registered |
| Launch → Scale | Primary metric hit *and real* (not a false positive); guardrails stable |
| any → Sunset | Forced verdict from portfolio review; sunset runbook started |
