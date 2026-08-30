# Chains of Pull Requests

> **Publication lifecycle:** public-preview advisory candidate; current changes
> require human review before acceptance.
> **Authority:** advisory; the high-level statement in
> [`README.adoc`](../../README.adoc) remains canonical.
> **Maintenance state:** active candidate with no assigned human maintainer.
> **Human owner:** unassigned.
> **Last human review:** not reviewed.
> **Review triggers:** a canonical policy change, material Git or hosting
> capability change, new review-outcome evidence, or a reported semantic or
> navigation defect.

## The practical change

AI can make it cheaper to propose decompositions, draft review maps, update
descriptions, restack branches, run checks, and collect evidence. Git and the
hosting platform can establish topology and check state. Neither decides
whether a layer is a coherent human review decision or whether the cumulative
change is safe and worth releasing.

The author's subjective experience is that AI assistance makes longer chains
practical: approximately `90%` effective maintenance with AI assistance,
compared with approximately `20%` for unaided human maintenance over comparable
periods. These are workflow-specific ballpark figures; an individual chain may
be higher or lower. They are not measured reliability, formal benchmarks, or
claims that every layer remains correct.

AI materially changes the practical balance, but Git topology, cumulative
diffs, exact revisions, tests, CI, and merge state remain authoritative.

Use a chain only when every layer expresses a bounded decision, every intended
landing prefix is coherent and verifiable, and focused review is worth the
added synchronisation, re-review, CI, and merge cost.

## Choose the change shape first

| Situation | Usually prefer | Reason |
|---|---|---|
| One concept that cannot be made safe or meaningful in parts | One integrated PR | Artificial layers distribute one decision and create misleading intermediate states |
| Coherent steps genuinely depend on earlier work and every prefix is safe | A short chain | Review can start early while order and interruption states remain explicit |
| Changes are conceptually independent | Parallel ordinary PRs | A chain invents serialisation and base-drift costs |
| Compatibility seams let groundwork land and wait safely | Sequential ordinary PRs | Stable lower layers shorten descendant drift |
| A migration spans repositories | Compatibility-first changes plus a combined integration gate | Links and separate CI cannot establish one compatible state |
| A broad mechanical change follows one verified rule | One mechanically reviewable PR, possibly divided by ownership | Many dependent PRs may multiply review without reducing the decision |

Decompose by behaviour, contract, migration stage, or reversible decision, not
by directory or whatever grouping an agent finds easiest.

## Use precise vocabulary

| Term | Meaning here |
|---|---|
| Chain or stack | Ordered review changes in which a later change depends on an earlier one |
| Layer | One PR and its focused diff against the layer immediately below it |
| Prefix | The cumulative state after applying the first one or more layers |
| Restack | Re-establishing the declared order after a lower layer or trunk changes |
| Independent reviewability | A reviewer can understand a layer's decision, evidence, and cumulative effect |
| Independent mergeability | A layer can land safely without an unmerged descendant |
| Green prefix | The exact cumulative revision passed the checks required for that prefix |
| Merge group | A temporary combined state created for queue validation |

A green prefix is not automatically approved, releasable, fit for purpose, or
valuable. Reviewability is weaker than mergeability. Parallel changes do not
become a chain merely because a document lists them in order.

## Keep authority divided correctly

| Concern | AI may help | What establishes or owns it |
|---|---|---|
| Candidate boundaries | Inventory effects and propose shapes | Human owner accepts conceptual coherence |
| Branch operation | Rebase and propose conflict resolutions | Git refs and ancestry establish topology; humans resolve meaning |
| Test selection | Suggest and run affected suites | CI records results for exact revisions; humans judge sufficiency |
| Restack comparison | Summarise patch-series changes | Human inspection and rerun evidence establish acceptability |
| Review explanation | Draft per-layer and cumulative maps | Independent human understanding and accountable approval |
| Merge and release | Prepare status and rollback information | Protected operations and authorised humans own timing and consequences |

AI must not silently force-push a shared branch, dismiss a review concern,
change the declared chain shape, bypass checks, or merge merely to restore a
green state.

## Define one chain contract

Before opening a deep tail, record and link from every layer:

1. cumulative purpose, non-goals, accountable owner, trunk, and reviewers;
2. exact PR order, bases, head revisions, dependencies, and current status;
3. the one decision and cumulative behaviour represented by each layer;
4. APIs, schemas, compatibility, data movement, flags, and landing order;
5. invariants that must hold after every possible landing prefix;
6. checks, tested revision, environment, result, omissions, and invalidation;
7. deferred work, owner, justification, and removal trigger;
8. stop, rollback, disable, and recovery behaviour at every prefix; and
9. WIP, review-capacity, chain-age, and CI-budget stop conditions.

The overview is an aid, not authority for the graph. Read the actual refs and
platform state back before relying on it.

## Require coherent prefixes

For every state that may land, ask:

- Does it build and pass the checks required for its own claims?
- Is external behaviour compatible, gated, or deliberately versioned?
- Are behaviour and supporting tests together?
- Can it deploy safely even if later layers never land?
- Can a reviewer explain what is true now and deliberately not true yet?
- Can the team stop or roll back here without a hidden descendant dependency?

Prefer compatibility-first patterns: add before remove; read old and new before
writing only new; deploy behind a disabled flag; make backfills resumable; keep
producers compatible while consumers migrate; and remove compatibility only
after the declared evidence exists.

A temporary red state can help local construction, but it is not an
independently mergeable layer. Keep it local or explicitly draft and prohibit
merge until a coherent prefix is restored.

## Treat restacking as a state transition

When a base changes:

1. capture the old base and head revisions;
2. decide whether the change is semantic, mechanical, or both;
3. replay descendants in the declared order;
4. stop on conflicts whose intended behaviour is unclear;
5. compare old and new patch series and identify semantic changes;
6. refresh descriptions, compatibility information, and deferred work;
7. rerun checks for every invalidated prefix and merge-group state;
8. invalidate or explicitly reconfirm affected approvals; and
9. update shared refs only through protected operations or an exact expected
   remote revision.

An AI can perform and summarise these steps. Ref read-back, patch comparison,
CI results, and platform state are the evidence that they occurred. AI
assistance does not make a force update harmless or prove conflict resolutions
correct.

## Budget the complete chain

```text
chain review cost = layer reviews
                  + context switching
                  + whole-chain synthesis
                  + invalidated re-review
```

Avoid a universal maximum chain length. Reshape, shorten, land stable
groundwork, or stop when reviewers cannot state cumulative behaviour, the base
remains unsettled, restacking exceeds new learning, checks exceed the agreed
budget, a layer has no independent decision, or ownership and rollback are
unclear.

Cheap administration is not a reason to preserve a chain whose boundaries no
longer help human review.

## Review checklist

- [ ] One human owns the cumulative outcome, risk, and release decision.
- [ ] Integrated, parallel, sequential, and chained shapes were considered.
- [ ] Every layer expresses one decision and every landing prefix is safe.
- [ ] Exact refs, dependencies, compatibility, and stop rules are current.
- [ ] Behaviour and its supporting evidence land together.
- [ ] Restacks compare patch series and rerun invalidated checks.
- [ ] Evidence names the exact prefix or merge-group revision and environment.
- [ ] Material base changes invalidate affected evidence and approvals.
- [ ] Reviewer capacity, WIP, chain age, and CI cost remain acceptable.
- [ ] Cross-repository compatibility has a combined gate and landing plan.
- [ ] An authorised human accepts ownership and the exact final merge state.

## Evidence and limits

Coherent small changes and current stack mechanisms have strong practitioner
support. Empirical results are narrower and do not establish that stacked or
smaller PRs universally improve latency, defect detection, or understanding.
Tool and hosting capabilities are date-sensitive and should be rechecked before
depending on exact behaviour.

Useful public sources include:

- Google, [Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html)
  and [CL descriptions](https://google.github.io/eng-practices/review/developer/cl-descriptions.html);
- GitHub, [About stacked pull requests](https://docs.github.com/en/pull-requests/get-started/about-stacked-prs)
  and [Managing a merge queue](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue);
- Git, [range-diff](https://git-scm.com/docs/git-range-diff) and
  [merge-base](https://git-scm.com/docs/git-merge-base);
- [The Effects of Change Decomposition on Code Review](https://doi.org/10.7717/peerj-cs.193);
- [Do Small Code Changes Merge Faster?](https://doi.org/10.1145/3524842.3528448);
  and
- [Expectations, Outcomes, and Challenges of Modern Code Review](https://doi.org/10.1109/ICSE.2013.6606617).

## Related public guidance

- [Conceptual load](../principles/README.md#size-changes-by-conceptual-load)
- [Review for understanding](../principles/README.md#review-for-understanding-and-ownership)
- [Independent review and merge](../workflow/README.md#phase-5-independent-review-human-acceptance-and-merge)
