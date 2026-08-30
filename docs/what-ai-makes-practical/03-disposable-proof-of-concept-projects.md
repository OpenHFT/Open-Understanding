# Disposable Proof-of-Concept Projects

> **Publication lifecycle:** public-preview advisory candidate; current changes
> require human review before acceptance.
> **Authority:** advisory; the high-level statement and production boundary in
> [`README.adoc`](../../README.adoc) remain canonical.
> **Maintenance state:** active candidate with no assigned human maintainer.
> **Human owner:** unassigned.
> **Last human review:** not reviewed.
> **Review triggers:** a canonical workflow or production-boundary change, new
> prototyping evidence, a material platform-safety change, or a reported
> semantic or navigation defect.

## The practical change

AI can lower the cost of turning a question into an executable experiment. It
can generate alternatives, fixtures, harnesses, traces, documentation, and
analysis quickly. This makes it practical to test more uncertain ideas before
investing in production quality.

PoCs keep attention on the target requirement and counter the tendency of AI
and humans to generalise beyond the limited functionality needed. A working,
even badly written, demonstration grounds the discussion and helps clarify the
behaviour that is actually required.

The result is still scoped evidence. A successful demonstration can expose
integration problems, mistaken assumptions, usability problems, and
considerable low-hanging fruit. It is materially useful, not merely better than
nothing. It does not automatically establish security, scalability,
operability, maintainability, user value, or general production fitness.

Production systems and release code must meet the highest applicable standard.
An experiment, mock, unit test, demonstration, or design-conversation artefact
needs a standard appropriate to its declared purpose. Stopping early does not
make it production-ready. Before it becomes production code, externally relied
upon, connected to production authority, or part of critical assurance, it
must meet the applicable production standard and human-ownership gate.

## Use lifecycle names deliberately

| Artefact | Primary question | Typical lifecycle | Success does not imply |
|---|---|---|---|
| Proof of concept | Does a concept or risky integration appear feasible under stated conditions? | Normally discard implementation and retain evidence | Whole-system fitness or production maturity |
| Spike | What can be learned about one uncertain question within a time box? | Discard or convert learning into notes and tests | A reusable feature |
| Prototype | What can evaluators learn from a proposed experience or structure at chosen fidelity? | Throwaway or evolutionary, declared explicitly | Technical feasibility or production quality unless tested |
| Walking skeleton | Can a thin end-to-end path cross important real boundaries? | Often evolutionary with controls appropriate to that intent | Broad feature or quality coverage |
| Tracer bullet | Can a narrow real path reach the target through the intended system? | Evolutionary real code | Permission for prototype-quality shortcuts |
| Demonstration | Can an observer reproduce a declared result in selected scenarios? | Retained evidence; target code may remain or be discarded | Every requirement or production condition |
| Pilot | What happens with a limited real population under safeguards? | Live, monitored, reversible, and governed | A safe place for uncontained throwaway code |
| Production increment | Is this an integrated, verified slice an owner will support? | Retained production lineage | An experiment merely because it is small |

A sacrificial architecture is a production system deliberately expected to be
replaced. It still requires production quality, ownership, operations, and
credible replacement seams.

Choose the lifecycle before building. If the intention changes, stop and
reclassify through an explicit human decision. Polish and sunk effort must not
promote an experiment by inertia.

## State a bounded claim

A defensible result has this shape:

> In environment `E`, with versions `V`, workload or data `W`, configuration
> `C`, method `M`, oracle `O`, and implementation `I`, criterion `K` was met or
> missed on date `D`.

Prefer "the parser accepts at least 99.5% of the approved corpus and reports
every rejected record without mutation" to "prove the parser works". Define
units, tolerances, sample construction, and error handling before seeing the
result.

Implementation feasibility is not requirement authority. A generated system
can make an inferred feature work without showing that anyone asked for it or
should retain it. Every known material requirement must remain retained with
appropriate evidence, explicitly deferred, explicitly rejected with a reason,
or recorded as unresolved.

## Charter the experiment first

Record:

1. **Decision and owner:** what action can change and who decides.
2. **Primary claim:** one falsifiable statement, with secondary observations
   clearly subordinate.
3. **Criteria and limits:** success, failure, stop, time, compute, API, and cost
   boundaries.
4. **Excluded claims:** normally production fitness, security, scale,
   operations, maintainability, and user value unless directly investigated.
5. **Fixtures:** representative and adversarial data with lawful provenance.
6. **Oracle:** how the result is judged and how shared assumptions are exposed.
7. **Environment:** versions, configuration, topology, resources, and known
   differences from intended use.
8. **Safety boundary:** permitted identities, data, tools, networks, side
   effects, and irreversible actions.
9. **Lifecycle:** disposable, evolutionary, or unresolved, without assuming
   later approval.
10. **Evidence and teardown:** what is retained, deleted, and verified removed.

Choose the cheapest faithful experiment: a written example, paper interface,
simulation, stub, spike, coded prototype, thin end-to-end path, or governed
pilot. Fidelity should be high only in dimensions that affect the claim.

## Contain expendable code

Maintainability and technical debt are not goals for a deliberately isolated
disposable experiment. Safety boundaries are still mandatory.

- Use a marked, access-controlled sandbox with no production deployment or
  package-publication path.
- Use least-privilege, short-lived identities and resources.
- Prefer synthetic, minimised, redacted, or specifically approved data.
- Allow only named tools, networks, recipients, and side effects.
- Put hard limits on time, concurrency, tokens, API calls, spend, and storage.
- Provide an effective stop mechanism.
- Make teardown repeatable and verify removal of credentials, data copies,
  queues, resources, and callbacks.
- Record dependencies, licences, provenance, and supply-chain concerns before
  considering retention.
- Require human confirmation of the exact target and effect of high-impact
  actions.

`EXPERIMENT - NOT FOR RELEASE` is useful status, but it is not containment.
Permissions, credentials, workflows, registries, and branch policy must enforce
the boundary.

## Use layered evidence

A realistic demonstration may concentrate on the happy path and intended user
or business value. It can expose problems isolated tests miss. It remains
scoped evidence.

Targeted tests should cover crash recovery, boundaries, invariants, unusual
states, and failure paths that are difficult to express in the principal
demonstration. Important complex concerns should, where practical, also receive
a realistic demonstration built on those tests. A happy-path demonstration
that omits crash recovery is not a reason to drop crash recovery.

Match broader fitness claims to additional evidence:

| Claim | Additional evidence |
|---|---|
| Behaviour for real consumers | Acceptance harness using public interfaces, representative data, negative cases, tolerances, and an independent oracle |
| Security and lawful handling | Threat model, data and licence decisions, dependency and secrets review, adversarial testing, and appropriate independent review |
| Performance and scale | Representative topology, workload, duration, contention, failure conditions, tail distributions, capacity, and cost |
| Reliability and operation | Owned deployment, observability, recovery exercise, rollback, and support responsibility |
| Maintainability and ownership | Human explanation, deep review or rewrite, understandable tests and decisions, and a realistic change exercise |
| User and organisational value | Accessibility and usability evidence followed, where useful, by a governed later observation loop |

## Preserve learning without promoting source

Record raw observations, anomalies, negative results, retries, and deviations.
Do not silently regenerate until the preferred answer appears. Stop at the
agreed information, cost, or safety limit.

Retain the evidence needed to understand the decision: charter, criteria,
versions, fixtures or generators, independent tests and oracles, measurements,
relevant traces, dependency and licence findings, rejected approaches,
unresolved uncertainty, decision, disposition, and teardown confirmation.

Keep reusable evidence outside disposable implementation lineage. If audit or
reproduction justifies source retention, store a sanitised, access-controlled
snapshot with an expiry. Otherwise delete it. Disposable means that unsafe
source does not enter release lineage; it does not mean destroying useful
evidence.

If work continues towards production, Phase 2 removes exploratory history and
Phase 4 establishes human ownership through a rewrite, deep review, or both.
The owner must regard the retained release code as theirs rather than the AI's
and be able to explain, change, diagnose, and support it.

## Review checklist

- [ ] Decision, owner, claim, criteria, exclusions, and stop rules predate code.
- [ ] The chosen medium is the cheapest one faithful to the question.
- [ ] Environment, versions, fixtures, oracle, and representation gaps are recorded.
- [ ] Data, credentials, tools, networks, effects, cost, and teardown are bounded.
- [ ] No accidental production deployment or publication route exists.
- [ ] Raw observations, anomalies, failures, and deviations are preserved.
- [ ] Success and failure conclusions remain within tested conditions.
- [ ] Demonstrations and targeted tests support their distinct claims.
- [ ] Security, scale, operation, maintainability, and value are evidenced or excluded.
- [ ] Evidence is curated outside the disposable implementation where appropriate.
- [ ] A human records abandon, retain for limited use, retest, or progress.

## Evidence and limits

Established prototyping guidance supports early experiments and warns against
copying prototype code into production. Research also reports learning benefits,
fixation, premature expectations, and several legitimate prototype lifecycles.
No strong comparative evidence establishes that full rewrite or selective
continuation always produces lower total risk for AI-generated software.

Useful public sources include:

- GOV.UK, [Making prototypes](https://www.gov.uk/service-manual/design/making-prototypes);
- Martin Fowler, [Sacrificial Architecture](https://martinfowler.com/bliki/SacrificialArchitecture.html);
- Hunt and Thomas, [Tracer Bullets and Prototypes](https://www.artima.com/articles/tracer-bullets-and-prototypes);
- NIST, [Reference Implementation](https://csrc.nist.gov/glossary/term/reference_implementation)
  and [Secure Software Development Framework](https://doi.org/10.6028/NIST.SP.800-218);
- [An empirically based model of software prototyping](https://doi.org/10.1007/s10664-023-10331-w);
  and
- NASA, [Technology Readiness Levels](https://www.nasa.gov/directorates/somd/space-communications-navigation-program/technology-readiness-levels/).

## Related public guidance

- [Phase 1 exploration](../workflow/README.md#phase-1-working-requirements-and-first-proof-of-concept)
- [Phase 2 consolidation](../workflow/README.md#phase-2-rewrite-and-consolidate)
- [Phase 4 ownership](../workflow/README.md#phase-4-take-ownership-of-release-code)
- [Fitness evidence](../principles/README.md#passing-tests-does-not-establish-fitness-for-purpose)
- [Risk-calibrated adoption](../guides/README.md#calibrate-the-workflow-to-risk)
