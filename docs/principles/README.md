# Open Understanding principles

The [public README](../../README.adoc) contains the authoritative high-level
wording for this edition. This page groups the principles into a compact set of
questions that can be used during planning, implementation, and review.

## Decide what is worth building

### Understanding is the challenge

The limiting task is usually not expressing a known solution. It is discovering
what should change, why it should change, and what should remain unchanged. AI
can accelerate exploration and expression, but generated volume can hide weak
understanding just as easily as it can help develop it.

Ask:

- Can we explain the intended outcome without describing the chosen solution?
- Which assumptions have been tested, and which are still guesses?
- What have we deliberately decided not to build?

### Define intent and manage scope drift

Tie requirements and designs to a clear outcome. New evidence may justify
changing that outcome, but the change should be explicit. Substantial adjacent
work should be separated when combining it would make the original purpose hard
to review.

Ask:

- Does each retained capability contribute to the stated intent?
- Has the intent changed, or has the implementation merely expanded?
- Would a newly discovered foundation be clearer as its own project?

### Treat specifications as hypotheses

A specification is an explicit, reviewable claim about need and behaviour. It
is useful because it can be challenged, not because its format makes it true.
Implementation, experiments, and user evidence should simplify and correct it.

Ask:

- Is each requirement observable or otherwise actionable?
- What evidence could show that it is wrong or unnecessary?
- Has exploratory breadth been consolidated after learning?

## Preserve rationale and important intent

### Record rationale and decision history

Documentation often describes what a system does while omitting why. Record the
context, alternatives, decision, consequences, and conditions for
reconsideration when they will matter to future maintainers.

Ask:

- Could a maintainer distinguish a deliberate constraint from an accident?
- Are rejected alternatives recorded where repeating them would be costly?
- Is the decision linked to the evidence available at the time?

### State critical intent in complementary forms

Important behaviour becomes easier to inspect when expressed in prose,
examples, invariants, tests, or diagrams. These forms should challenge one
another. Do not duplicate facts mechanically when they require one authoritative
source.

Ask:

- Do examples and tests expose ambiguities in the prose?
- Are invariants stated independently of one implementation?
- Is there a clear authority when representations disagree?

### Let readers reconstruct the decision trail

Retain enough evidence, assumptions, alternatives, decisions, and consequences
for another competent person to understand and challenge the work. Exhaustive
transcripts and private chains of thought are neither necessary nor desirable.

Ask:

- Can a new maintainer see how the evidence led to the decision?
- Are important corrections and contrary findings preserved?
- Is sensitive or disposable working material kept out of authoritative docs?

## Build evidence, not reassurance

### Passing tests does not establish fitness for purpose

Tests show that encoded expectations hold for their exercised scope. Validation
also asks whether the expectations describe the right behaviour for the real
environment, users, operators, and constraints.

Ask:

- What does the test suite demonstrate, and what remains outside its scope?
- Has the result been exercised in a representative use case?
- Could the same evidence pass for an implementation that is still unsuitable?

### Prefer deterministic mechanisms for stable decisions

LLMs are useful where ambiguity and exploration matter. Stable, bounded,
repeated decisions may be cheaper and safer as explicit rules, parsers,
classifiers, or conventional software that can be reproduced and inspected.

Ask:

- Has the decision boundary become stable enough to encode directly?
- How will exceptions and drift be detected?
- Does replacing model judgement actually reduce risk and maintenance cost?

### Validate value separately from delivery activity

Generated files, commits, requirements, tests, and completed tasks measure
activity. They do not establish an improved outcome. Assess delivery flow
alongside quality, review cost, operational effects, user outcomes, and lifetime
ownership.

Ask:

- What observable outcome should improve?
- What support obligation is being created?
- Has faster production moved work into review, rework, or operation?

## Make work reviewable and supportable

### Review for understanding and ownership

Review should enable another person to explain the change, challenge its
assumptions, and help support it. AI can find defects and generate questions,
but it does not carry operational responsibility or own the consequences.

Ask:

- Can the reviewer teach the change back in their own words?
- Did the reviewer use an independent definition of correct behaviour?
- Is there a named person or team prepared to support the result?

### Size changes by conceptual load

Line count is a weak proxy for review difficulty. Conceptual load comes from new
behaviour, invariants, interfaces, risks, and interactions a reviewer must hold
together. A coherent large mechanical change may be easier than a tiny but
critical semantic change.

Ask:

- How many new ideas and interactions must be understood together?
- Can mixed concerns be separated without hiding an important dependency?
- Does the change tell one reviewable story?

### Make artefact status, provenance, and ownership visible

Exploratory notes, generated proposals, accepted guidance, and archived
decisions should not look equally authoritative. Directories, filenames, and
formats can signal status, but named ownership, review records, and reproducible
provenance provide stronger evidence.

Ask:

- Can a reader tell what is current and authoritative?
- Is generated material reproducible where that matters?
- Does accepted material have a responsible owner?

## Edit for the reader

### Apply editorial judgement to AI-assisted writing

AI can quickly generate conventional coverage, alternatives, and structure.
The editor must decide what this audience needs, remove generic repetition,
verify claims, preserve useful counterviews, and give prominence to the
project-specific argument.

Ask:

- What can this audience already be expected to know?
- Which statements are important enough to verify and retain?
- Has polished but low-value material displaced the actual point?

### Preserve salient detail at every elevation

Long documents often give equal space to each topic while omitting the few
facts that matter at a strategic, architectural, or implementation level. A
useful explanation gives readers the important detail at the elevation of their
decision and lets them move to supporting detail when needed.

Ask:

- Is the central decision visible before the supporting material?
- Are crucial low-level constraints easy to locate?
- Is document length being mistaken for coverage?

## Define success honestly

### Validate value and ownership together

Success is an observed improvement in a worthwhile outcome, considered against
human attention, risk, maintenance, and support. A technically complete result
can still fail if nobody needs it, understands it, or can operate it safely.

Ask:

- What changed for users, operators, or the organisation?
- What evidence supports attributing that change to this work?
- Is the retained result understood and supportable over its expected life?
