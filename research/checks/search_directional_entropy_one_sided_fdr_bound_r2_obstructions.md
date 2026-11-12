---
type: search_round
title: Directional entropy bound round 2 obstructions
target_asset: directional_entropy_one_sided_fdr_bound
mode: refute
round: 2
directions:
  - extremal
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: d2f5f592be074963400a03298424a3e5e1df4050144f3e4fb2d8d8b6c4249a95
performed_by: unknown
created_at: '2026-11-04T07:44:25.677Z'
extension_version: 0.0.4
---

## Obstructions

- For singleton null groups, $\mathcal E_0=\pi_0\log m$; the arbitrary-dependence harmonic bound $q\pi_0 H_m\leq q\pi_0(1+\log m)$ is already smaller than the proposed bound. Increasing the number of singleton directions therefore supplies no counterexample.
- The small-test families examined were excluded by the harmonic bound or, where its hypotheses hold, the nonnegative-correlation BH bound; these exclusions do not cover arbitrary correlated-alternative models.
- Merging opposite rays violates the oriented-group hypothesis. For finite $m$, every nonempty group has $\pi_h\geq1/m$ and there are at most $m_0$ such groups, so zero-mass or infinitely many positive-mass groups at fixed $m$ are inadmissible.

## Limitations

- All four directions produced no candidate file and no survivor. A stronger mixed-$r_i\in\{0,1\}$ bound $q\{(1+1/e)\pi_0+\mathcal E_0\}$ was reported, but was not independently certified in this summary.
- A general argument for shared interior-loading null groups with correlated alternatives remains required, together with the uniform entropy-controlled asymptotic passage; the tested families do not establish either step.
