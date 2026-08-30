# What AI Makes Practical

> **Publication lifecycle:** public-preview advisory candidate; current changes
> require human review before acceptance.
> **Authority:** advisory; [`README.adoc`](../../README.adoc) is the canonical
> policy for this edition.
> **Maintenance state:** active candidate with no assigned human maintainer.
> **Human owner:** unassigned.
> **Last human review:** not reviewed.
> **Review triggers:** a canonical policy change, a material change in AI or
> hosting capability, new outcome evidence, a public contribution, or a
> reported semantic or navigation defect.

AI does not make established engineering disciplines obsolete. It changes the
economics of some activities: producing a candidate, exploring an alternative,
or applying a repetitive transformation may become cheap enough to do
routinely. That transfers effort rather than eliminating it. Selection,
verification, authority, reviewer attention, lifecycle control, and deletion
become the scarce parts of the work.

This guidance covers three practices whose balance can change materially:

| Practice | Opportunity | Governing question | Guidance |
|---|---|---|---|
| Maintained documentation | Draft, transform, search, and check bounded material more cheaply | Can an intended reader rely on this material for a named task, and what keeps that claim true? | [Useful, maintained documentation](01-useful-maintained-documentation.md) |
| Chains of pull requests | Administer coherent dependent changes with less clerical effort | Does each layer express a decision, and does each possible landing state have current evidence? | [Chains of pull requests](02-chains-of-pull-requests.md) |
| Disposable proof-of-concept projects | Turn more decision-blocking questions into executable experiments | What did the experiment establish, under which conditions, and what must be discarded or reclassified? | [Disposable proof-of-concept projects](03-disposable-proof-of-concept-projects.md) |

The canonical [`README.adoc`](../../README.adoc) supplies the shared value model,
percentage qualifications, production boundary, and human-ownership requirements.
These chapters are advisory expansions: they do not prove universal benefit or
approve an implementation for production or publication. Recheck date-sensitive
capabilities and read practitioner estimates as subjective ballparks whose results
may be higher or lower in a particular case.

## Related public guidance

- [Principles](../principles/README.md)
- [Workflow](../workflow/README.md)
- [Practical guides](../guides/README.md)
- [Documentation map](../README.md)
