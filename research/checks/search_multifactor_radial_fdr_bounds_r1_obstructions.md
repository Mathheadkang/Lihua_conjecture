---
type: search_round
title: Round 1 obstructions for finite-level radial Gaussian multifactor BH bounds
target_asset: multifactor_radial_fdr_bounds
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates:
  - cand_multifactor_radial_fdr_bounds_r1_s3_antialigned_positive_alternative
  - cand_multifactor_radial_fdr_bounds_r1_s3_excluded_one_sided_level
  - cand_multifactor_radial_fdr_bounds_r1_s3_independent_zero_loading
  - cand_multifactor_radial_fdr_bounds_r1_s3_one_sided_composite_antipodes
  - cand_multifactor_radial_fdr_bounds_r1_s3_two_sided_endpoint_full_loading
  - cand_multifactor_radial_fdr_bounds_r1_s4_antipodal_rank_one
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:41:59.792Z'
extension_version: 0.0.4
---

## Obstructions

- A family with FDR at most $q$ cannot violate the proposed bound: the displayed right-hand side is at least $q$ on the permitted level range. The supplied candidate summaries place the tested rank-one antipodal configurations, their tested composite-null variant, the independent zero-loading boundary, and the tested two-sided full-loading endpoint in this class. Thus singularity, norm-one loadings, or zero loadings alone do not produce a violation in these examples. This obstruction applies to the configurations covered by those summaries, not to arbitrary models sharing one of these features.
- Within the investigated two-test singular antialigned family, optimizing the unrestricted positive alternative mean gives FDR only $3q/4$. Varying that mean within this family therefore cannot violate a bound whose right-hand side is at least $q$.
- A testing level outside the asserted one-sided range fails the level hypothesis before the conclusion is tested. Such examples cannot refute this finite-level statement, regardless of their behavior outside its domain.

## Limitations

- Four directions ran: `boundary_degenerate`, `small_cases`, `drop_hypothesis`, and `known_counterexamples`. The first two wrote no candidate files; the six failed candidate files came from the latter two. No candidate satisfies all hypotheses and violates the conclusion. This is a search outcome, not a proof or certification of the target statement.
- The context pack's statement, board, and one-line candidate outcomes were used, together with the root worker's handoff identifying the four searched directions. Candidate calculations and their hypothesis checklists were not independently reconstructed; the obstructions above retain the scope of those reported outcomes.
- The supplied outcomes do not document systematic coverage of intermediate loading norms, genuinely multidirectional higher-dimensional factors, heterogeneous loading directions, larger numbers of tests, or interactions among multiple alternatives. They also do not verify the proposed radial tail-strip estimate or the claimed uniformity over these configurations.
- The earlier search report mentions one-factor inflation constructions within the bound, but gives no candidate calculations for them in this round. It supports no broader exclusion of inflation mechanisms here.
