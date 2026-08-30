# Useful, Maintained Documentation

> **Publication lifecycle:** public-preview advisory candidate; current changes
> require human review before acceptance.
> **Authority:** advisory; the high-level statement in
> [`README.adoc`](../../README.adoc) remains canonical.
> **Maintenance state:** active candidate with no assigned human maintainer.
> **Human owner:** unassigned.
> **Last human review:** not reviewed.
> **Review triggers:** a canonical policy change, a material change in AI
> retrieval or editing capability, new documentation-outcome evidence, or a
> reported semantic or navigation defect.

## The practical change

AI can make first drafts, transformations, candidate updates, repository
searches, and constrained consistency checks cheaper. That is enough to make
some previously neglected documentation work practical. It does not establish
that the resulting document helps a reader, remains aligned with the product,
or costs less over its whole life.

In the author's workflow-specific experience, AI draws on or proposes updates
to available documentation about `80%` of the time, while humans consistently
draw on the written material much less than `20%` of the time. These are
subjective, illustrative ballpark figures. A particular case may be higher or
lower. They are not measured probabilities, reliability statistics,
benchmarks, or guarantees.

AI may retrieve the wrong page, miss a dependency, misunderstand a claim, or
make an incorrect update. Deterministic checks, executable examples, explicit
change triggers, and human verification remain useful precisely because cheap
proposals do not establish synchronisation.

The objective is not more documentation. It is a reliable route from a
reader's question to an owned answer.

## Define the reader outcome

Documentation is useful when an intended reader can complete an intended task,
understand a concept, obtain a reliable reference answer, or make a decision
with acceptable effort and risk. Correctness, completeness, readability, and
traffic may contribute, but none substitutes for the reader outcome.

Before generating a page, name:

1. the reader and task;
2. the consequence of a wrong or missing answer;
3. the supported version and environment;
4. the authority of the proposed material;
5. the source for each material claim;
6. the event that could make it stale;
7. the owner who can resolve disagreement; and
8. the condition for correction, replacement, or removal.

Sometimes the best documentation change is a better link, an executable
example, generated reference, or deletion of a conflicting page rather than a
new explanation.

## Make authority and lifecycle visible

Authorship does not determine authority. A generated API reference can be the
authoritative rendering of an accepted schema. Human prose can remain an
unreviewed opinion.

Useful lifecycle classes include:

| Class | Role | Minimum visible signal |
|---|---|---|
| Authoritative documentation | Behaviour, decisions, procedures, or policy readers may rely on | Owner, scope, review route, and history |
| Source-derived reference | Reproducible rendering of a reviewed interface or schema | Generated status, named source and version, and reproduction method |
| AI-generated candidate | Proposed prose, example, classification, or update | Candidate status, bounded sources, and required reviewer |
| Working note | Temporary observation or unresolved thinking | Non-authoritative status, owner, and promotion or removal trigger |

A page is maintained when a named role owns its continuing validity, relevant
changes trigger review, important claims are checked against suitable sources,
and superseded material is corrected, redirected, archived, or removed. A
recent edit alone is not evidence of maintenance; an automated rewrite can
freshly express a stale assumption.

## Match claims to controls

One generic documentation check cannot cover every kind of claim.

| Content | Useful control | What still needs judgement |
|---|---|---|
| API shape and schema | Generate from the reviewed interface and reproduce the output | Meaning, omissions, stability promises, and audience fit |
| Command or code example | Execute against declared supported versions and assert meaningful output | Whether it teaches a safe and useful path |
| Internal navigation | Check links and anchors deterministically | Whether the destination is authoritative and answers the question |
| Behaviour or compatibility promise | Link a contract or acceptance test where practical | Whether the promise is desirable and covers the real risk |
| Architecture or rationale | Decision record, owner, evidence links, and review triggers | Intent, rejected alternatives, and continuing validity |
| Procedure or runbook | Rehearse in a declared environment | Safety, operational judgement, and recovery |

Generated reference moves the source-of-truth problem; it does not eliminate
it. Executable examples prove only the path and assertions they encode.

## Use a controlled workflow

1. **Select.** State reader, task, authority, supported scope, and evidence
   sources.
2. **Constrain.** Give AI a bounded objective and source set. Require explicit
   unknowns and preservation of accepted decisions.
3. **Generate a candidate.** Keep it visibly non-authoritative until the normal
   acceptance route promotes it.
4. **Establish facts.** Render the documentation, execute examples, validate
   schemas, regenerate reference, and check links and declared versions.
5. **Review claims and outcomes.** A domain owner checks truth and omissions; a
   representative reader checks navigation and task completion.
6. **Promote explicitly.** Remove the candidate label only through the same
   authority path used for equivalent human-authored material.
7. **Observe.** Look for failed tasks, repeated questions, search dead ends,
   support demand, defects, and maintenance cost.
8. **Retire.** Delete, redirect, or archive content whose expected value no
   longer justifies its review and retrieval cost.

Agent access to a page is not evidence that the agent retrieved the relevant
version, understood it, or followed it. Test agent-facing documentation with
representative tasks and inspect which source was actually used.

## Review checklist

- [ ] Reader, task, consequence, supported version, and authority are explicit.
- [ ] Each material claim has a suitable source or is marked unknown.
- [ ] Owner, change triggers, verification, and retirement conditions exist.
- [ ] AI output remains a candidate until the normal authority path accepts it.
- [ ] Deterministic checks support named claims rather than blanket approval.
- [ ] Domain review covers truth and omissions; reader review covers use.
- [ ] Replaced material is removed, redirected, or visibly archived.
- [ ] Search and agent routes no longer present retired content as current.
- [ ] Drafting, review, triage, and maintenance costs are considered together.

## Evidence and limits

Documentation-as-code, generated reference, executable examples, decision
records, and task-based information architecture are established practices.
Evidence also shows that misleading documentation can harm model performance
and that retrieval systems can produce unsupported answers. This supports
bounded generation and verification, not a claim that AI-maintained
documentation is universally cheaper or more reliable.

Useful public sources include:

- [Diataxis](https://diataxis.fr/), for separating tutorial, how-to, reference,
  and explanation needs;
- [Write the Docs: Docs as Code](https://www.writethedocs.org/guide/docs-as-code/),
  for reviewable documentation workflow;
- [Python doctest](https://docs.python.org/3/library/doctest.html), for
  executable examples;
- [OpenAPI best practices](https://learn.openapis.org/best-practices.html), for
  source-derived reference;
- Macke and Doyle,
  [Testing the Effect of Code Documentation on LLM Code Understanding](https://doi.org/10.18653/v1/2024.findings-naacl.66),
  for evidence that misleading documentation can harm model performance;
- [Lost in the Middle](https://doi.org/10.1162/tacl_a_00638), for limits of
  long-context use; and
- [RAGTruth](https://doi.org/10.18653/v1/2024.acl-long.585), for unsupported
  claims in retrieval-augmented generation.

## Related public guidance

- [Editorial judgement](../principles/README.md#apply-editorial-judgement-to-ai-assisted-writing)
- [Artefact status and ownership](../principles/README.md#make-artefact-status-provenance-and-ownership-visible)
- [Human accountability](../guides/README.md#keep-roles-and-accountability-clear)
- [Independent review and merge](../workflow/README.md#phase-5-independent-review-human-acceptance-and-merge)
