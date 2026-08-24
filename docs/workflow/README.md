# Open Understanding workflow

The workflow moves from broad, inexpensive exploration towards selected,
reviewable, supportable behaviour. Its six phases are a thinking aid rather
than a mandatory delivery model. Small, reversible work may abbreviate phases;
consequential or difficult-to-reverse work needs stronger evidence and
independence.

See the [public README](../../README.adoc) for the authoritative high-level
phase definitions in this edition.

## Phase 0: research and evidence

Broaden and challenge the initial idea before formal requirements or substantial
implementation make one interpretation expensive to abandon.

Useful outputs include:

- a clear intended outcome and affected users;
- existing evidence and publicly supportable sources;
- plausible alternatives and counterarguments;
- assumptions, uncertainties, and important constraints;
- an initial view of consequence and reversibility.

Exit question: **Is there enough evidence to justify an experiment, and is the
experiment bounded enough to run safely?**

## Phase 1: working requirements and first proof of concept

Use a deliberately exploratory implementation to discover feasibility, hidden
constraints, important behaviour, and which candidate requirements deserve to
survive. The result is a learning instrument, not production code by default.

Keep the environment safe: use synthetic or sanitised data, constrained
credentials, cost limits, and no accidental route to production deployment.

Exit question: **What did implementation teach us, and which requirements are
now supported, rejected, or still uncertain?**

## Phase 2: rewrite and consolidate

Rewrite the requirements and reference implementation around what was learned.
Remove speculative breadth, duplicate rules, accidental prototype structure,
and requirements that cannot be made actionable.

Preserve discovered behaviour deliberately through examples, tests, decision
records, and traceable evidence. Do not preserve prototype structure merely
because it already exists.

Exit question: **Is there now one coherent account of the intended behaviour
and a reference result that demonstrates it?**

## Phase 3: refactor towards the intended design

Reduce the structural and conceptual distance between the reference result and
the intended production design while protecting observable behaviour. Improve
names, boundaries, dependencies, failure handling, and test shape in reviewable
steps.

Refactoring is not a substitute for resolving unclear intent. If behaviour must
change, make the semantic change explicit and return to the relevant earlier
question.

Exit question: **Can the responsible developer read the complete release
surface and describe the remaining gap to a supportable design?**

## Phase 4: take ownership of release material

Retain only behaviour the responsible people understand and are prepared to
support. For critical release code, reconstructing or rewriting from the
consolidated understanding can expose assumptions that editing generated code
would leave hidden.

A full rewrite is not always proportionate. Selective adoption can be valid
when the retained code is conventional, well evidenced, completely reviewed,
and genuinely owned. The test is ownership and fitness, not who typed each
line.

Exit question: **Would the named owners be willing and able to diagnose,
change, and support every retained part?**

## Phase 5: independent review, release, and outcome validation

Ask a reviewer to reconstruct the intended outcome, changed behaviour,
unchanged behaviour, risks, and evidence independently. Complete operational
readiness work, release within authorised boundaries, and observe whether the
intended outcome occurs.

Local tests do not establish remote integration, production behaviour, user
value, or operational readiness. Record the demonstrated scope and the
remaining human gates separately.

Exit question: **Can an independent reviewer explain why this is ready, and is
there a credible way to observe value and respond if the result is wrong?**

## Cross-phase rules

### Stop when the evidence says to stop

The workflow may end because the idea is not valuable, the risk is
disproportionate, or the evidence does not support continuing. Stopping is a
valid result of discovery.

### Give foundational work its own loop

When a substantial foundation is discovered during another project, consider
running that foundation through its own research, implementation, and review
loop instead of allowing the parent project to grow without limit.

### Read volume as a trajectory, not a score

Exploration may expand the number of artefacts; consolidation and ownership
should usually reduce them. Neither expansion nor contraction proves value on
its own.

### Increase assurance with consequence

The depth of review, provenance, testing, operational rehearsal, and outcome
validation should reflect impact, reversibility, uncertainty, and applicable
obligations—not enthusiasm for a tool or process.
