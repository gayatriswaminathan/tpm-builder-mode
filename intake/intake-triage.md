# Intake Triage

> Pattern **#8**: identify program → phase → intent, **load context before acting**, and **flag phase-jumps** instead of absorbing them silently. If ambiguous, ask — don't guess.

## For every incoming request

**1. Identify the program.** Match against known programs. If ambiguous, ask which — don't guess.

**2. Identify the phase.** Where is that program actually (`phase-gates.md`)?

**3. Identify the intent.** What's really being asked for?

**4. Context loaded? (required before routing to execution)**
- [ ] Charter / goal read
- [ ] `scope-and-non-goals.md` read
- [ ] Last 3 `decision-log.md` entries read
- [ ] Open `diligence-debt.md` checked

**5. Phase-fit check.** Does this request match where the program is?
- ✅ Fits → route to execution.
- ⚠️ Jumps a phase (e.g. "let's run the big launch" on something not yet validated) → **do not silently comply.** Surface it as a risk/decision: route to `templates/decision-record.md`, name the skipped gate, and let the owner make the call.

## Routing table (customize)
| Intent | Route to |
|---|---|
| New scope ask | `templates/scope-and-non-goals.md` bar → decision record |
| Launch readiness | `templates/go-no-go-gate.md` |
| "What should we focus on?" | `playbooks/portfolio-review.md` |
| Post-milestone lessons | `templates/retro-learning-loop.md` |
| Something broke | `registers/anti-patterns.md` (+ retro if it's a boundary event) |
