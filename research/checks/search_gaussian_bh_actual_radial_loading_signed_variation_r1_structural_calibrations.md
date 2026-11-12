---
type: search_round
title: Round 1 structural calibrations for the signed actual radial-loading response
target_asset: gaussian_bh_actual_radial_loading_signed_variation
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_actual_radial_loading_signed_variation_r1_s2_single_null_scalar
statement_digest: 7fdc4735d0d5e381ad9fbb0ee8f7ab5df233763c161d5f77194d54300e4e7cac
performed_by: unknown
created_at: '2026-11-09T18:20:32.937Z'
extension_version: 0.0.4
---

## Obstructions

- Zero-loading populations are stationary under the prescribed transport: if $v=0$ almost surely, both the loading and its compensating private variance remain unchanged. Their kernels, tails, actual ranks and cutoff payoff are therefore unchanged. This family cannot produce a nonzero response contradicting the asserted formula.
- Populations with zero true-null mass have $V_X=0$, $f_X=0$ and zero full and cutoff FDP at every endpoint. Both signed response terms vanish; this family cannot test a nonzero signed contribution.
- Saturating the loading norm does not remove private smoothing: even at $\|v\|=1$, the conditional private standard deviation is at least the fixed $s>0$. Thus an attempted counterexample based on a degenerate conditional score or a rank-one survival atom does not belong to this boundary family: the smoothed tails have quantile tending to $-\infty$ as rank tends to one, the barrier tends to $+\infty$, and rank-one survival has value zero.
- The tested lawful single-null scalar calibration fails the required conclusion-negation check, rather than a hypothesis check: candidate `cand_gaussian_bh_actual_radial_loading_signed_variation_r1_s2_single_null_scalar` passes H1--H4 and fails NOT because the direct cutoff derivative agrees with the complete signed actual-rank response. Its reported value, approximately $-0.3480485316$, is a numerical diagnostic accompanying the exact agreement. This rules out that tested object; it does not establish the formula for arbitrary scalar mixtures or directing laws.

## Limitations

- Only one candidate was recorded. The other directions supplied boundary calibrations or no plausible object; they did not exhaust their search spaces. No survivor or verified counterexample was obtained, and this round is not a proof of the target.
- The round did not settle competing or infinitely many active suffix minima, their measurable selection-free envelope, compact uniformity under transport, or the asserted survival difference-quotient convergence in $L^1(dr)$.
- The conditional actual-rank brackets, the conditional domination bound independent of the directing law and Gaussian realization, and the large-$d_X$ regime still require full arguments. Agreement in the scalar calibration does not supply those arguments.
- Arbitrary Borel directing laws, infinite-dimensional isonormal representatives, differentiation under the directing law, endpoint integrability, and outer-expectation limit interchange remain outside the verified scope of the search.
- Genuine deterministic extremal comparison and canonical finite endpoint recovery with $o(\epsilon)$ error were not tested. This round establishes neither covariance monotonicity nor a bound uniform as regularizers vanish, and it does not identify the actual response with a chosen dual radial contact derivative.
