---
type: search_round
title: Round 3 obstructions for the unrestricted two-sided Gaussian BH upper bound
target_asset: gaussian_bh_two_sided_sharp_upper
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates:
  - cand_gaussian_bh_two_sided_sharp_upper_r3_s1_cyclic_strong_sparse_boundary
  - cand_gaussian_bh_two_sided_sharp_upper_r3_s2_opposite_signal_ladders
  - cand_gaussian_bh_two_sided_sharp_upper_r3_s3_sparse_global_gate
  - cand_gaussian_bh_two_sided_sharp_upper_r3_s4_harmonic_normal_marginals
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:21:06.008Z'
extension_version: 0.0.4
---

## Obstructions

The following summarizes the four candidate failure reports in this round's context pack. It does not independently verify their calculations or proofs.

- The tested cyclic strong sparse-signal boundary arrays are reported to obey a global-BH truncated-harmonic envelope $\operatorname{FDR}\leq q\{1+O(\log\log(1/q))\}+q^3=o(q\sqrt{\log(1/q)})$; their specified sparse-signal and boundary scaling therefore fails the asymptotic NOT check.
- The tested opposed signal-ladder arrays are reported to have an earlier global ladder crossing that bounds the null cutoff by an independent Gaussian factor with an integrable null-tail envelope, giving $O(q)$ FDR despite their growing mean-type count and arbitrary changing loading angle; this ladder mechanism fails the asymptotic NOT check.
- The tested independent-null arrays with at most one arbitrarily dependent alternative are reported to have $O(q)$ FDR, including the prescribed superpolynomial dimension, diverging mean, and exactly singular covariance regime; this sparse global-gate mechanism fails the asymptotic NOT check.
- Harmonic-event constructions with standard-normal marginals and covariance $I_N$, but dependent absolute-value events, fail joint Gaussianity: a jointly Gaussian vector with covariance $I_N$ would have independent coordinates. The tested construction therefore fails H2, leaving the later checks and NOT unknown.

## Limitations

- Weakly coupled common-gate models remain unresolved. This round provides no completed global-crossing analysis that excludes them; an unfinished analysis is missing coverage, not a failed object or a refutation.
- Richer interior residual-noise models, other signal-ladder geometries, and growing-block or high-rank covariance structures outside the specified tested families remain uncovered. The reported bounds are not uniform results for every Gaussian model with many mean types, sparse signals, or an interior covariance component.
- The harmonic construction shows that Gaussian marginals and a valid covariance matrix alone do not ensure an admissible jointly Gaussian object. Its excluded dependence mechanism supplies neither an admissible counterexample nor a verified bound for admissible Gaussian dependence.
- No candidate survived this round: three reports fail the asymptotic NOT check and one fails an assumption. This establishes no counterexample to the conjecture and does not prove its unrestricted uniform upper bound. Any later proof using these reported envelopes or crossing arguments still requires the relevant independent verification.
