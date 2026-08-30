# Open Understanding workflow

> **Publication lifecycle:** public-preview advisory candidate; current changes
> require human review before acceptance.
> **Authority:** advisory; [`README.adoc`](../../README.adoc) contains the
> canonical phase definitions for this edition.
> **Maintenance state:** active candidate with no assigned human maintainer.
> **Human owner:** unassigned.
> **Last human review:** not reviewed.
> **Review triggers:** a canonical phase change, a public contribution, a
> material contradiction, or a reported application problem.

The workflow moves from broad, inexpensive exploration towards selected,
reviewable, supportable behaviour. Its six phases are a thinking aid rather
than a mandatory delivery model. Small, reversible work may abbreviate phases;
consequential or difficult-to-reverse work needs stronger evidence and
independence. Production systems and release code must meet the highest
applicable standard. Limited-purpose experiments, mocks, tests, demonstrations,
and design-conversation material need only meet the standard appropriate to
their declared purpose. This does not require every artefact to complete every
phase.

The overall direction is largely top-down, but implementation produces
bottom-up learning. Before starting each of Phases 1 to 4, consider which
concrete design changes, fixes, or implementation work are worth completing
first. Resolving them can simplify the next phase and focus it on what remains
to be added.

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

For every load-bearing claim, record the exact public source, its date, what it
supports, and its limitations. Distinguish direct evidence, inference, and
author observation. Open and verify decisive sources rather than relying on a
generated summary or search snippet.

Exit question: **Is there enough evidence to justify an experiment, and is the
experiment bounded enough to run safely?**

## Phase 1: working requirements and first proof of concept

Work broadly, quickly, and messily to cast a wide net over ideas, requirements,
and behaviours; try rapidly evolving implementations; discover functionality;
reject weak ideas; and identify what may be worth retaining. An almost-complete
implementation can expose the shape of the problem, but neither completeness
nor polish is required. Maintainability and technical-debt reduction are not
Phase 1 goals.

Keep the environment safe: use synthetic or sanitised data, constrained
credentials, cost limits, and no accidental route to production deployment.
Clean stale or contradictory exploratory material only when it blocks learning,
creates a safety problem, or makes the experiment misleading. Phase 2 is the
principal boundary for removing this historical debris.

Exit at the plateau where further iteration no longer appears to produce
meaningful implementation progress or discover, refine, or reject material
requirements. Generated volume and apparent completeness are not success
measures. Then abandon the work, retain it for its declared limited purpose, or
progress to Phase 2.

## Phase 2: rewrite and consolidate

After most broad discovery, coherently rewrite and consolidate the behaviours,
requirements, evidence, and lessons worth retaining. Further discovery remains
legitimate, and Phase 1 need not have produced a complete specification. Remove
speculative breadth, duplicate rules, accidental prototype structure, and the
historical complexity accumulated during exploration.

Preserve discovered behaviour deliberately through examples, tests, decision
records, and traceable evidence. Do not preserve prototype structure merely
because it already exists.

Retained requirements preserve their provenance. Implementation and execution
coverage inform requirements but do not become authority. Every known material
requirement must be retained with appropriate evidence, explicitly deferred,
explicitly rejected with a reason, or recorded as an unresolved gap. A
happy-path demonstration that omits crash recovery is not a reason to remove
crash recovery.

Rework within Phase 2 while it remains productive. Output reduction is an
observed consequence in some projects, not the objective or a numeric gate.
Broad generation is useful while it creates learning, but becomes
counterproductive when it overwhelms selection, understanding, and ownership.

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

Exit question: **Has the responsible developer read the complete candidate
release surface, and can they describe its architecture, critical behaviour,
hidden coupling, and remaining gap to a supportable design?**

## Phase 4: take ownership of release code

By the end of this phase, the responsible human should feel that the release
code is theirs rather than the AI's. A rewrite, a deep review, or a combination
may create that ownership. The owner must understand the retained behaviour and
be prepared to explain, defend, change, diagnose, and support it. This is not
ritual line-by-line retyping or a percentage of human keystrokes. Mechanical or
already-proven material may remain where it does not undermine ownership. A
shallow review is not an equivalent transfer of ownership.

The author's practical test is to return a day later: if the owner cannot
confidently distinguish what they wrote from what AI wrote, that is a useful
sign that the code has their tone, approach, and quality. It is a practitioner
heuristic, not proof of understanding or fitness.

Exit question: **Would the named owners be willing and able to diagnose,
change, and support every retained part?**

## Phase 5: independent review, human acceptance, and merge

Before merge, an independent reviewer explains in their own words the intended
business or user outcome, the observed behaviour that changes, what deliberately
remains unchanged, and how this will be communicated to affected users. Review
the relevant demonstrations and tests, important risks and evidence limits,
support, and ownership. A human must understand the change sufficiently to
accept responsibility for it, then accept and merge it.

Earlier phases demonstrate credible value and Phase 4 establishes ownership.
Phase 5 does not claim validated production value. Post-deployment commercial
or operational measurement may be useful and may feed a later iteration, but it
is outside Phase 5.

Exit question: **Does an independent human understand the change and its
evidence sufficiently to accept responsibility, and has a human accepted and
merged it?**

## Cross-phase rules

### Stop when the evidence says to stop

The workflow may end because the idea is not valuable, the risk is
disproportionate, the result is sufficient for a restricted non-production
purpose, or the evidence does not support continuing. Stopping is a valid
result of discovery but does not make an early-phase result production-ready.
Before an artefact becomes production code, externally relied upon, connected
to production authority, or part of a critical assurance mechanism, it must
meet the applicable production standard.

### Give foundational work its own loop

When a substantial foundation is discovered during another project, consider
running that foundation through its own research, implementation, and review
loop instead of allowing the parent project to grow without limit.

### Read volume as a trajectory, not a score

Exploration may expand the number of artefacts; consolidation and ownership
should usually reduce them. Neither expansion nor contraction proves value on
its own. Rework inside a phase while it remains productive. Use the Phase 1 to
Phase 2 rewrite as the principal break from exploratory history, and Phase 4 as
the principal ownership boundary through a rewrite, deep review, or both, when
work continues towards production.

### Increase assurance with consequence

The depth of review, provenance, testing, and operational rehearsal should
reflect impact, reversibility, uncertainty, and applicable obligations - not
enthusiasm for a tool or process.
