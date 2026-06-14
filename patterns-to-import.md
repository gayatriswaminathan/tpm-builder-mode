# TPM Governance Patterns

Fourteen governance mechanics for running programs with discipline. Each one: the **principle**, the **TPM translation**, and a **concrete rollout** you can copy this quarter. The through-line: *make the implicit explicit, force a verdict, and re-check whether each rule still earns its keep.*

---

## 1. Forced-verdict gates (no "it depends")

**The principle.** Every decision point returns one of a fixed, small set of verdicts and refuses to hedge. A launch gate returns GO / NO-GO / GO-WITH-CONDITIONS. A scope decision returns BUILD / DEFER / KILL. A portfolio call returns DOUBLE-DOWN / MAINTAIN / MINIMAL / SUNSET. "It depends" is not an allowed answer.

**TPM translation.** Most program gates are soft — a yellow status, a "mostly ready," a launch review that ends in vibes. The discipline is a *closed verdict set + a named owner of the call*. It removes the ambiguity that lets risky work slip through a green-ish gate.

**Rollout.** Pick your two highest-stakes gates (e.g. launch-readiness, go/no-go). Replace the status field with a forced enum and a single accountable owner. "GO-WITH-CONDITIONS" must list the conditions inline with owners and dates, so it can't become a soft yes.

---

## 2. The honest badging ledger (proven vs. aspirational)

**The principle.** Every claim carries a badge: ✅ proven (validated by a real, named result), 🟡 partially proven, or ⏳ research-baked (borrowed from a credible source, but not yet battle-tested here). Nothing earns ✅ by opinion.

**TPM translation.** The single most stealable idea for status reporting. Program status almost never separates *what we've actually validated* from *what we believe will work*. A badge that distinguishes the two kills the most common reporting failure: confident-sounding claims that are really assumptions.

**Rollout.** Add a confidence badge to every claim in your status docs and risk register. ✅ verified (with the evidence/link), 🟡 partial, ⏳ assumed. Apply it to launch criteria, dependency commitments, and "on track" calls. The first time a green dependency is actually a ⏳, you've earned the practice back.

---

## 3. The scored learning-loop (retros that compound and self-correct)

**The principle.** Raw lessons accumulate continuously. At defined boundaries, each candidate is scored on a few weighted axes — Impact (doubled), Recurrence, Generalizability, Confidence — into a composite. Only the highest composites are eligible, and **at most the top ~3 per cycle** get promoted into a load-bearing guardrail. A low-confidence lesson can never promote (verify it first). Every promotion records a **predicted gain** and a **feedback-check date**; if it didn't deliver by then, it's sunset.

**TPM translation.** Retros usually generate a pile of action items nobody revisits. This is a retro engine with three things most lack: (1) a *forcing function* that promotes only a few high-leverage lessons, (2) a written prediction of the gain, and (3) a *scheduled re-check that retires the change if it didn't pay off*. It turns "we wrote it down" into "the process got measurably harder to break."

**Rollout.** After each major milestone, score candidate process changes on a cut-down rubric (Impact ×2, Recurrence, Confidence). Promote ≤3. For each, write the predicted improvement and a date to re-check it. At the next milestone, kill the ones that didn't deliver. This alone prevents the process-bloat that accretes in long programs.

---

## 4. Anti-patterns lead, and they're dated wounds

**The principle.** Keep a library that *opens* with anti-patterns, each tied to a specific dated incident. Each entry names the wound, the root cause, and the guard that prevents recurrence — and is re-read before similar work, not filed and forgotten.

**TPM translation.** A living "things that have bitten us" library, surfaced *before* the work that could repeat them — a pre-mortem fed by real postmortems. The key move is *re-read before related work*, not "file and forget."

**Rollout.** Start an anti-pattern register keyed by work-type (deploys, migrations, vendor cutovers). Each entry: dated incident → why it happened → the guard that prevents recurrence. Add a line to your launch/change checklist: "read the anti-patterns for this work-type." Cheap; compounds.

---

## 5. Scope as a "deliberately does NOT do" contract

**The principle.** Every scope doc lists **three things it deliberately does NOT do**, plus **anti-features** ("no, even if widely requested"). Scope amends *only* with documented evidence (e.g. ≥3 real-user needs or a named customer commitment), and the amendment is logged with the evidence cited. A parking lot holds deferred items with an explicit "**reconsider when**" trigger.

**TPM translation.** Change control with teeth. The "does NOT do" list is the part most scope docs omit — and it's the part that actually prevents creep. The evidence bar converts scope debates from loudest-voice to show-the-data.

**Rollout.** Add a "Non-goals (deliberate)" and "Anti-features" section to every PRD/charter. Define the bar to change scope and require it logged. Move "maybe later" asks to a parking lot with a *trigger condition*, not a vague backlog.

---

## 6. Measurement — and false-positives — defined *before* launch

**The principle.** Set the success framework pre-launch so you can't cherry-pick metrics that flatter early traction. Define the primary metric, the activation criterion, retention/health targets, the success threshold — and, crucially, the **false-positive shapes**: the patterns that would *look* like success and aren't (a launch spike that decays, insider signups, high-signup/low-activation).

**TPM translation.** Two imports. First, lock the success metric *before* ship so it can't be redefined to fit the result. Second — the rare one — pre-register **"what would fool us."** Naming the false-positive shapes upfront stops a vanity spike from being read as a win.

**Rollout.** In the launch plan, fill a one-pager: primary success metric + target, the leading indicator, and a "False positives" list — 3 ways the metric could look good while the launch actually failed, and the evidence that tells real from fake. Review it at the post-launch readout.

---

## 7. Validation debt — skip if you must, but never silently

**The principle.** Building before a diligence step is allowed, but the hard rule is: never skip it *silently*. The skip is recorded as an explicit, tracked debt.

**TPM translation.** Teams cut diligence under deadline pressure constantly; the failure is that the cut is invisible until it bites. Making the skip an explicit, tracked debt item — not a quiet omission — is the entire move.

**Rollout.** Create a "diligence debt" lane in your tracker. When a team ships past a skipped gate (security review, load test, accessibility pass), it doesn't get waved through — it gets a logged debt ticket with an owner and a pay-back-by date. Visible cuts get paid back; silent ones don't.

---

## 8. Routing/intake: load context first, flag phase jumps, don't guess

**The principle.** A strict intake protocol: identify program → phase → intent, **always load the relevant context docs before acting**, and if the request doesn't match the phase (e.g. "run the big launch" on something not yet validated) **flag the mismatch** rather than complying silently. If ambiguous, ask instead of guessing.

**TPM translation.** Intake triage plus a phase-gate guard. The two transferable rules: (1) no work starts until the relevant context (charter, scope, last few decisions) is loaded, and (2) when an ask jumps a phase, that gets surfaced as a risk, not quietly absorbed.

**Rollout.** Add to your intake template a required "context loaded" check (charter, current phase, open decisions) and a "phase-fit" flag: does this request match where the program actually is? If not, route it to a risk/decision, not straight to execution.

---

## 9. Stage-gated lifecycle with explicit boundary triggers

**The principle.** Work runs through defined phases, and the boundaries are **events**, not calendar dates: a program crosses a gate, ships, is sunset, has a notable incident or win, or the process itself changes. Reviews attach to those events.

**TPM translation.** A clean phase-gate model where the gates are *defined trigger events* rather than fuzzy "end of quarter." It also pins your review cadence to real signals (a ship, an incident) instead of arbitrary recurring meetings.

**Rollout.** Write down your program's phase boundaries as explicit events. Attach the rituals (retro, metric review, risk re-score) to those events. Keep calendar reviews, but let event-triggered reviews carry the real weight.

---

## 10. Portfolio cadence: "if you had 4 hours" + forced reallocation

**The principle.** A single table across everything — the top-3 priorities, what's on fire, what not to touch — framed as "if you had 4 hours, spend them here." On a cadence, force a reallocation verdict per program, and for anything killed, run a full **sunset plan** (notify → freeze → export → shut down → archive → postmortem).

**TPM translation.** Across a portfolio of programs, this is ruthless prioritization plus a *standardized wind-down runbook*. The "4 hours" framing forces concentration; the sunset plan means killing a workstream is a clean process, not a slow fade.

**Rollout.** Build a one-table portfolio view (program × phase × health × trend × owner-hours × verdict). Run it on a cadence; force a verdict per program. Keep a reusable sunset runbook so deprecating a program is a checklist, not an improvisation.

---

## 11. "Where this could be wrong" — bias check inside the decision

**The principle.** Major review templates end with a mandatory self-check: *where am I likely being too optimistic or too pessimistic?* Built into the artifact, not optional.

**TPM translation.** A structural pre-mortem embedded in every major decision doc. Forcing the author to name their own likely bias surfaces blind spots before they ship.

**Rollout.** Add a required "Where this call could be wrong" section to decision memos and go/no-go docs. One paragraph. It costs nothing and catches the optimism that hides in confident recommendations.

---

## 12. Govern your own process — prune the guardrails

**The principle.** Treat your process as a product with users (your teams). It accretes bloat and needs pruning — so a guardrail must keep *earning its place*, or it gets sunset. "A rule that costs friction without paying for it is bloat."

**TPM translation.** Apply your program-governance to your own program-governance. The sunset mechanic is what stops "best practices" from becoming dead ritual.

**Rollout.** Once a quarter, audit your own rituals and required artifacts: which gate/meeting/template demonstrably prevented a problem this quarter? Sunset the ones that only generated overhead. Treat each ceremony as something that must re-justify itself.

---

## 13. Decision log with evidence cited (ADR-style)

**The principle.** Every program keeps a decisions register; every major call is logged with the **evidence cited**, and the last few entries are read back at the start of new work.

**TPM translation.** A lightweight ADR/decision register that's actually *read back*. The "cite the evidence" requirement is what separates a real decision log from a list of opinions.

**Rollout.** Keep a dated decision register per program: decision, the evidence behind it, who owned it. Make "read the last N decisions" a step in any new-work kickoff so context travels forward instead of being re-litigated.

---

## 14. Honest-copy principle for outbound comms

**The principle.** Every outward-facing word is true and verifiable when it ships; aspiration is labelled, never written in present tense.

**TPM translation.** Status integrity. The rule "aspiration is never written in present tense" is a clean test for status updates, launch announcements, and exec reporting — it forbids the "we have X" that's really "we're building X."

**Rollout.** Adopt the present-tense test for stakeholder comms: anything not yet true gets future/conditional framing or a ⏳ badge (pattern #2). Pairs naturally with the badging ledger.

---

## Where to start (highest payoff, lowest effort)

1. **#2 Confidence badges** on your next status report — one column, immediate signal-to-noise win.
2. **#1 Forced verdicts** on your launch/go-no-go gate — kills soft-green ambiguity.
3. **#6 False-positive pre-registration** on your next launch — catches vanity wins.
4. **#3 Scored learning-loop** after your next milestone — makes retros compound instead of evaporate.

The rest layer in over a quarter.
