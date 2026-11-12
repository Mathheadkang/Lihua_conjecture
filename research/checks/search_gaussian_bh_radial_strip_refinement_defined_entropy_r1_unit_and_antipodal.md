---
type: search_round
title: >-
  Round 1 unit-mass and antipodal checks for the defined-entropy radial strip
  refinement
target_asset: gaussian_bh_radial_strip_refinement_defined_entropy
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - >-
    cand_gaussian_bh_radial_strip_refinement_defined_entropy_r1_s1_single_unit_mass
  - >-
    cand_gaussian_bh_radial_strip_refinement_defined_entropy_r1_s2_antipodal_pair
statement_digest: 582355e827b2c8daf9f48064719117ca7fdba4dbdf5b11f0c912cc329dca2dad
performed_by: unknown
created_at: '2026-11-06T23:22:06.147Z'
extension_version: 0.0.4
---

## Obstructions

- The tested single unit-mass configuration does not refute the refinement: A(1,0)=0 and C_11=+infinity give zero strip cost under the stated minimum convention, while its exact reported FDR is q.
- The tested antipodal unit-loading pair does not refute the refinement: its reported exact FDR is q, and the finite bound, entropy comparisons, and applicable asymptotic corollary hold.

## Limitations

The two saved candidates in boundary_degenerate and small_cases passed H1 through H5 and failed NOT; no survivor was reported. This summary uses their supplied failure lines without independently reconstructing candidate bodies. These limited cases do not prove the general finite RS bound, extended-entropy comparisons, or the asymptotic corollary, and the search is nonexhaustive. In particular, this entropy-conditioned statement does not establish the researcher's revised universal nonsharp q sqrt(log(1/q)) order target for arbitrary covariance. This record closes only the supplied round and makes no goal or native-state change.
