---
type: search_round
title: 'Round 5: diffuse zero-mean directions admit polygon approximation'
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_quadratic_penalized_population_maximizers_r5_s1_diffuse_zero_circle
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:58:53.599Z'
extension_version: 0.0.4
---

## Obstructions

- Diffuse zero-mean mass on a circle of unit directions cannot obstruct finite directional approximation. Partition the circle into finitely many arcs and send each direction to a nearest polygon vertex, retaining its mean and tag. The maximum angular distance, and hence Euclidean directional displacement, tends to zero as the polygon mesh shrinks. The induced coupling has vanishing Wasserstein cost, and the second mean moment remains exactly zero. The round-5 candidate reports full largest-crossing FDR convergence, consistently with the approved fixed-loading continuity theorem. Thus diffuseness of this directional family fails the counterexample check NOT. Rationalization and any repair of alternative-tagged zero means must additionally respect the tag boundary, as in the earlier board obstruction; a positive repair has a vanishing, rather than identically zero, second mean moment.

## Limitations

- This round contains one failed boundary-degenerate candidate, involving diffuse zero-mean circular directions. It does not cover arbitrary joint distributions of means, directions and tags, unbounded means, or every finite ambient dimension.
- The reported directional quantization and moment preservation do not by themselves establish the full canonical rational approximation theorem with controlled weight errors and tag repairs for arbitrary finite-second-moment laws.
- No general proof of compactness, lower semicontinuity, penalized attainment, or applicability of FDR continuity along arbitrary maximizing sequences is supplied by this round. Nor does it establish vanishing-penalty limits, signed deterministic transport comparisons, or simultaneous finite endpoint recovery with errors of order o(epsilon).
- Failure to find a counterexample is not verification of the target. No conclusion is drawn about varying dimension, unpenalized attainment, convergence of maximizing laws, finite-model derivatives, or unrestricted Gaussian BH order bounds.
