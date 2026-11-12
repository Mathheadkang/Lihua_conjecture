---
type: search_round
title: 'Compression round 1: exact tied-score ranks and tag averaging'
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r1_s1_mixed_zero_tied_atom
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r1_s1_singleton_exact_replication
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r1_s2_singleton_exact_copy
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r1_s2_two_tied_opposite_tags
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r1_s3_tied_zero_opposite_tags
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:15:23.787Z'
extension_version: 0.0.4
---

## Obstructions

- Exact copies of one score cannot produce a rank discrepancy, at any sample size or tie multiplicity. If every original score equals a random value T and p = S(T), ordinary BH has actual normalized largest rank 1 on {p <= q} and 0 otherwise, for both the population and its sampled multiset. This includes the non-strict boundary p = q. A singleton is the special case in which the FDP is also preserved identically.
- Opposite tags on a common zero-mean score cannot produce a nonvanishing FDP discrepancy. Writing pi for the original true-tag proportion and pi_m for its sampled proportion, the two FDPs are pi 1{p <= q} and pi_m 1{p <= q}. Independently of the shared Gaussian score, m pi_m is Binomial(m, pi), so E|pi_m - pi| <= sqrt(pi(1-pi)/m) <= 1/(2 sqrt(m)). For the admissible zero-mean, common-direction score, p is uniform and hence the expected FDP discrepancy is at most q/(2 sqrt(m)). All mixed-tag tied-zero candidates lie in this family; changing tag proportions or multiplicities does not evade the bound.

## Limitations

- All five reported failures reduce to a singleton or a single tied-score atom. This round did not cover distinct scores, multiple score atoms, competing BH crossings, threshold-near tangencies, or growing residual rank and dimension.
- No candidate tested microscopic positive normalized ranks, where division by the rank can amplify tag-tail errors. The fixed-common-loading microscopic-rank estimate and its locally uniform vanishing in q remain unchecked here.
- No general empirical-tail maximal estimate, common-Z trimmed-rank transfer, finite-grid identification, exact self-consistency argument for multiple score levels, or mixed-FDP comparison was established by these failures. The search supplies no proof of uniform compression and no confirmed counterexample.
