---
type: search_round
title: One-sided Gaussian BH round 2 growing-dimension screening
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - idea_27c06facb739
candidates: []
statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
performed_by: unknown
created_at: '2026-11-11T16:38:08.124Z'
extension_version: 0.0.4
---

## Obstructions

- A lower-bound construction attaining only a finite multiple of q sqrt(log(1/q)) does not refute an upper bound with an unspecified universal constant. The primary-source worker reports that Lei, arXiv:2607.14812v4, gives the one-sided lower bound q sqrt(log(1/q))/sqrt(pi) + q/2 + o(q), consistent with the proposed order; it does not supply an asymptotically unbounded ratio. The source leads are idea_4e6b9464da07 and idea_af05c3f05dab.
- The arbitrary-dependence harmonic bound FDR <= pi0 q H_N, where pi0=|I0|/N and H_N=sum_{k=1}^N 1/k, rules out an asymptotically unbounded normalized FDR for every model sequence with pi0 H_N=O(sqrt(log(1/q))). In particular, unbalanced sequences with pi0 H_N=o(sqrt(log(1/q))) have FDR/[q sqrt(log(1/q))] tending to zero, even when N grows. This is a restriction on such sequences and does not bound the unrestricted supremum over N and pi0.
- The specified nonnegatively equicorrelated Gaussian family in idea_27c06facb739 is admissible, but Gaussian positive regression dependence gives BH FDR <= pi0 q <= q. Its large rare-count variance therefore obstructs an independent-count approximation rather than the main FDR upper bound. Varying this family's count variance alone cannot turn that proxy failure into a main-theorem counterexample.

## Limitations

All three workers wrote no candidate files. No new admissible family with asymptotically unbounded FDR/[q sqrt(log(1/q))] was obtained. The source comparison, harmonic estimate, and equicorrelated-family control are limited search obstructions; they neither prove the main upper bound nor establish the absence of counterexamples.

The unrestricted regime still allows pi0 H_N/sqrt(log(1/q)) to grow without bound, together with arbitrary signed dependence, singular covariance, heterogeneous means, and increasing direction complexity. Neither the harmonic estimate nor the positive-dependence argument controls that regime. The quoted source lower bound was reported by the source worker; this summary does not provide a new independent verification of that source or a new upper-bound theorem. The conditional compound-p calibration and its source-verification requirement, the Gaussian averaged-envelope estimate, and the uniform singular-limit gate remain separate proof obligations not established by this round.
