---
type: search_round
title: Round 2 boundary-scope summary for the baseline-subtracted pivotal core
target_asset: gaussian_bh_baseline_subtracted_pivotal_core
mode: refute
round: 2
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 182210875024e41e07afd86320271d77d4c3101bb674953cf99e16eee40678ba
performed_by: unknown
created_at: '2026-11-06T20:55:40.504Z'
extension_version: 0.0.4
---

## Obstructions

- Endpoint-level examples with $q=0$ or $q=1$ fail the hypothesis $q\in(0,1)$.
- Zero-dimensional and infinite-dimensional examples fail the finite positive-dimensional Gaussian testing model hypothesis.
- Examples with a zero-variance null coordinate fail the standardized Gaussian marginal hypothesis used to obtain the uniform null p-value.

## Limitations

- All five round-2 workers reported no distinct admissible candidate and wrote no candidate files; there is no survivor to verify.
- This round supplied no new numerical experiment, exhaustive search, or computational certification.
- No counterexample was found; formal proof execution and independent verification of the target remain outstanding. This summary establishes no stronger crossing bound or unrestricted Gaussian BH result.
