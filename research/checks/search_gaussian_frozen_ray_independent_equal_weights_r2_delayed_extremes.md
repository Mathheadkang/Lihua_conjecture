---
type: search_round
title: 'Round 2: delayed extreme directions and the unresolved collective regime'
target_asset: gaussian_frozen_ray_independent_equal_weights
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_frozen_ray_independent_equal_weights_r2_s3_late_onset_growing_dimension
statement_digest: 50a2723662d1d1615266b7b08a764c5aeb61551586db2c3dbbdffbb9ea16dccc
performed_by: unknown
created_at: '2026-11-11T00:43:39.696Z'
extension_version: 0.0.4
---

## Obstructions

- The growing family indexed by every integer n >= 3 with K=n and c=alpha=exp(n^2) fails to refute either assertion: the candidate report bounds the truncated-moment excess above sqrt(log(c)/pi) by 2 and the normalized tail alpha sqrt(log(alpha)) P(Lambda >= alpha) by 5, uniformly in n. This rules out this entire specified sequence of delayed extreme thresholds, rather than just individual numerical parameter choices. It does not rule out other joint growth rates of K, c, and alpha. The reported mechanism combines scalar coordinate envelopes and clipping/variance control; the supplied summary does not contain the candidate's detailed derivation.

## Limitations

The round has one recorded failed candidate and no surviving counterexample. Its quantitative conclusion concerns only K=n and c=alpha=exp(n^2). The earlier report's late single-leader asymptotics are screening evidence, not a uniform finite-parameter exclusion of every single-leader regime. They cannot be promoted to an additional general obstruction without error bounds and control of all remaining contributions.

No worker settled the critical collective-SNR regime, simultaneous contributions of many coordinates at a common maximizing w, or the full range of joint growth rates and thresholds. Neither a dimension-uniform bound over all parameters nor the sharp moment coefficient for the full target has been established. Failure to find a counterexample proves neither assertion, and no Gaussian BH reduction follows.

The useful proposed proof step is recorded separately as [Separate late extreme tails by clipping independent scalar envelopes](../ideas/idea_978f04065c8e.md): clip the independent scalar envelopes at K alpha, combine an exceedance union bound with a variance bound above their clipped mean, and retain the collective regime as a separate obligation. That draft approach requires explicit scalar integral estimates and constants; it is not certified by this summary. It adds the independent clipping/concentration step rather than duplicating the earlier exact scalar and fixed-two-direction calculations.
