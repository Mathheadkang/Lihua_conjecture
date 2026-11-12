---
type: falsification_check
title: 'Falsification check: gaussian_frozen_ray_two_level_tree'
target_asset: gaussian_frozen_ray_two_level_tree
outcome: no_counterexample_found
statement_digest: 2b5422491f69603ba61bab7fad6c2642d6e692d0f1b1b9e16e8ff8d5ec9e825b
performed_by: unknown
created_at: '2026-11-11T01:10:40.646Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, small_cases: cand_gaussian_frozen_ray_two_level_tree_r1_s2_scalar_endpoint failed — NOT fails: the scalar family satisfies both assertions with $C_{\mathrm{sh}}=1$ and $C_{\mathrm{tail}}=1/(2\sqrt\pi)$.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: Every completely collapsed scalar realization, with all leaves equal to one standard normal variable, fails NOT: the reported candidate satisfies both target assertions with constants $C_{\mathrm{sh}}=1$ and $C_{\mathrm{tail}}=1/(2\sqrt\pi)$. Thus duplicating that scalar variable cannot produce a counterexample. This obstruction concerns the scalar family; it does not assert that every endpoint configuration is scalar.
- Obstruction: No new family-level obstruction was established this round. The round supplied no candidate and no quantified argument excluding a family; the existing scalar obstruction and endpoint-reduction observation remain earlier evidence.
- Obstruction: No new family-level obstruction was established in round 3: the round produced no candidates and no quantified exclusion argument. The earlier obstruction for completely collapsed scalar realizations remains prior evidence only; it does not exclude general endpoint or interior configurations.
- Obstruction: No new family-level obstruction was established in round 4. The supplied round record contains no candidates and no quantified exclusion argument. The earlier obstruction for completely collapsed scalar realizations remains prior evidence only; neither that obstruction nor the endpoint-reduction observation excludes the general interior two-level family.
- Obstruction: No new family-level obstruction was established in round 5: the supplied round contains no candidates and no quantified family-exclusion argument. The earlier obstruction for completely collapsed scalar realizations remains prior evidence only; it does not exclude the general interior two-level family.

## Limitations

- No candidates were supplied this round, so there is no new object, hypothesis-by-hypothesis verification, or failed NOT check to summarize. The search report's finite-size checks and endpoint reductions supply no new quantified exclusion.
- Uniform control of parent and child peaks at the same SNR remains unresolved. Independently maximizing the parent and child factors does not establish the required common-SNR bound.
- Joint variation of both branching sizes, the loading, and the thresholds remains uncovered, including endpoint neighborhoods and possible secondary or merging transitions. Exact endpoint reductions and freezing or saddle-point heuristics do not settle these regimes.
- Neither the exact truncated-moment coefficient with a parameter-independent additive constant nor the uniform maximal-tail scale has been established for the full family in this round. No counterexample was found; this does not prove either assertion.

Object search: 1 candidate(s) in 5 round(s).
