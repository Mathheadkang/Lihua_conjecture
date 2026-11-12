---
type: search_round
title: Directional entropy bound round 1 obstructions
target_asset: directional_entropy_one_sided_fdr_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates: []
statement_digest: d2f5f592be074963400a03298424a3e5e1df4050144f3e4fb2d8d8b6c4249a95
performed_by: unknown
created_at: '2026-11-04T07:38:44.871Z'
extension_version: 0.0.4
---

## Obstructions

- Degenerate loadings give no counterexample: empty null sets have zero FDR; zero null loadings give the bound $q\pi_0$; full null loading norms give the smaller bound $q(\pi_0+\mathcal E_0)$.
- Splitting a group of identical oriented null directions increases $\mathcal E_0$, hence only loosens the proposed bound; merge such groups for a stronger test. Antipodal directions remain separate under the stated grouping definition.
- The finite identical-null family obeys $q\pi_0\{1+\log(1/\pi_0)\}$, below the proposed right side. The known Lei families examined supplied no verified violation.

## Limitations

- Across the four search directions, no candidate file was produced. The 480 small singular-model floating-point interval checks, with maximum reported FDR-to-bound ratio $2/3$, are diagnostic and do not certify all hypotheses or the theorem.
- A general proof remains open, including justification of the groupwise weighted-cutoff bound and its uniform passage to the entropy-controlled asymptotic statement when dimension, test count, and grouping vary with $q$.
