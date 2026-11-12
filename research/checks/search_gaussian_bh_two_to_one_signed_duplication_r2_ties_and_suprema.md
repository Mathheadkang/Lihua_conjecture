---
type: search_round
title: Signed-duplication search on ties and worst-case suprema
target_asset: gaussian_bh_two_to_one_signed_duplication
mode: refute
round: 2
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 987e0b4167580298c08435b5d415d205e1f3153780e8613a7e16afb82038f6a6
performed_by: unknown
created_at: '2026-11-07T02:41:43.491Z'
extension_version: 0.0.4
---

## Obstructions

- Threshold ties cannot increase a BH rejection set beyond its largest qualifying rank: an additional p-value at or below that rank's threshold would itself produce a larger qualifying rank. This rules out a discrepancy caused solely by multiplicities in the signed and original orderings.
- Exact rational small-case checks reported for 14,040 configurations with N from 1 to 4 found no discrepancy in the largest qualifying rank, rejection set, multiplicity, or zero-rejection convention. These checks rule out only the tested finite configurations.
- A proposed boundary mechanism at q=1/2 and t=0 fails the strict hypothesis q<1/2. Within the stated interval, no complementary signed p-value of at least one half can pass a BH threshold.
- Dependence assumptions and monotonicity in negative null means are unnecessary for comparing expectations of a valid pathwise inequality: the duplicated Gaussian law is the pushforward of the original law. Thus their absence does not itself provide a counterexample.
- Allowing dimension and means to vary arbitrarily with q, or a worst-case supremum to be unattained, does not obstruct a pointwise finite-model reduction: each finite original model maps to an admissible even-dimensional one-sided model already included in the unrestricted one-sided supremum.

## Limitations

No concrete candidate was produced in this round. The finite rational checks are computational probes, not a proof of the arbitrary-dimensional statement. A complete proof must still establish the exact finite ordering and rejection-set correspondence for every realization, including all ties, zero statistics, and zero rejections, and then justify null-count domination and the supremum comparison. The searches neither establish nor test a uniform finite-constant order bound for either main FDR target. The elementary rank-separation approach is already recorded from the first round; no duplicate approach node is added here.
