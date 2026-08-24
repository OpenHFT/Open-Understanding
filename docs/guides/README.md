# Practical adoption guide

Open Understanding can be adopted without introducing a large process. Begin
with one bounded change, make the intended outcome explicit, and ask for enough
evidence that another person can understand and challenge the result.

This guide summarises the initial public recommendations. The
[principles](../principles/README.md) explain the reasoning and the
[workflow](../workflow/README.md) describes the six phases.

## Start with an outcome

Before asking an AI or developer to produce a solution, record:

- the user, operational, or business outcome sought;
- what observable behaviour should change;
- what deliberately remains unchanged;
- important constraints and unacceptable outcomes;
- how the result could be shown to be useful or wrong.

Keep this statement short enough to remain visible throughout the work. Revise
it explicitly when evidence changes the intent.

## Keep roles and accountability clear

AI can research, draft, implement, generate tests, compare alternatives, and
review artefacts. It cannot accept organisational responsibility, carry an
operational obligation, resolve value conflicts, or authorise consequential
actions.

For maintained work, name people responsible for:

- deciding the intended outcome and acceptable risk;
- verifying important evidence and sources;
- understanding and supporting retained behaviour;
- independently reviewing the change;
- authorising release and responding to failure.

Human ownership does not require manual typing. It requires sufficient
understanding, authority, capability, and willingness to act on the
consequences.

## Calibrate the workflow to risk

Assess risk before choosing controls. Consider:

- impact on people, money, data, operations, and reputation;
- reversibility and the time available to detect and correct failure;
- uncertainty in requirements, environment, and evidence;
- security, privacy, licensing, contractual, and regulatory obligations;
- how long the result will be maintained and by whom.

Disposable exploration may need little ceremony beyond isolation and clear
status. Reversible maintained work needs repeatable checks and ownership.
Critical or difficult-to-reverse behaviour needs stronger specifications,
independent evidence, operational rehearsal, and explicit release authority.

## Ask for evidence rather than confidence

An AI's confidence or completion statement is not execution evidence. For each
material claim, retain the smallest useful evidence bundle:

- the intended claim and its limit;
- the exact command, test, observation, or source used;
- the result and relevant environment;
- known gaps, assumptions, and remaining gates;
- the human decision made from that evidence.

Prefer evidence that can discriminate between a correct result and a plausible
but wrong one. A test that would pass for both provides little assurance.

## Make artefact status obvious

Separate exploratory notes from accepted guidance. A lightweight status model
is often enough:

- **exploratory:** disposable material used to learn;
- **proposed:** a candidate awaiting review or decision;
- **accepted:** maintained material with a named owner;
- **generated:** derived material with a stated regeneration method where
  reproducibility matters;
- **superseded or archived:** retained for history but not current authority.

Directories and file formats can make status visible at a glance, but ownership
and review records are the stronger source of truth.

## Use several agents deliberately

More agents do not automatically provide independent review. Independence can
come from different evidence, a different definition of correct behaviour, a
different reviewer perspective, or materially different findings.

When several agents work together:

- give each one a bounded question and clear artefact ownership;
- isolate simultaneous edits where conflicts would obscure responsibility;
- ask for disagreement, counterexamples, and failing demonstrations;
- reconcile findings through explicit rulings;
- re-check advice against the current change before applying it;
- leave one coherent result rather than a pile of unreconciled reports.

## Review for teach-back

Before release, ask someone other than the author to explain in their own words:

- the intended outcome;
- the behaviour that changes;
- what remains unchanged;
- the principal risks and evidence;
- how failure will be detected and handled;
- who owns the result.

Difficulty explaining the change is useful evidence that the change, its
documentation, or its conceptual boundaries need more work.

## A minimal first adoption

For one bounded change:

1. Write the outcome and non-goals in a short paragraph.
2. Record consequence, reversibility, and important obligations.
3. Let AI broaden alternatives and help build an inexpensive demonstration.
4. Consolidate what was learned into a smaller specification and change.
5. Retain executed evidence with explicit limits.
6. Have another person teach the result back.
7. Release within authorised boundaries and observe the outcome.
8. Keep, revise, or remove the result according to what was learned.

Add more structure only when it improves a decision, reduces material risk, or
makes ownership clearer.
