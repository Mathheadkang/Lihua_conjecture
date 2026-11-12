---
type: search_round
title: 'Mixed-density and singular-marginal search, round 2'
target_asset: gaussian_conditional_tail_density_replica_bound
mode: refute
round: 2
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: d962a0c4c2ebebb96a5dc8b28cb1e9b4f8c265c0b7f73aedb2d43016b25043f7
performed_by: unknown
created_at: '2026-11-07T00:51:35.717Z'
extension_version: 0.0.4
---

## Obstructions

- Equality cases for the mixed-density product, including sign-reflected singular coordinates with appropriately reflected deterministic levels, reduce to the squared-density expression. The tested equality families therefore supplied no separate violating mechanism.
- Weighted Cauchy--Schwarz bounds a mixed-density expression by the geometric mean of its two squared-density expressions. Consequently, a violation of the claimed common mixed bound requires a violation of at least one corresponding squared bound; a three-coordinate dependence pattern alone cannot evade that reduction.
- Each displayed scalar expression depends on at most three Gaussian coordinates. Adding coordinates while retaining their joint marginal does not amplify the expression. The tested growing singular blocks supplied no independent dimension-growth mechanism.
- The workers reported interpolation-integral limits $2$ as $\eta\downarrow0$ and $1$ as $\eta\to\infty$. These endpoint checks supplied no violation of its asserted upper bound.

## Limitations

- All five workers returned NONE and wrote no candidate files. No counterexample was identified; this outcome is not a proof or native verification of the draft lemma.
- A sampled mixed-density screen for the singular $N=3$ equicorrelation matrix with off-diagonal entries $-1/2$ found no violation. This finite exploration was not a certified global optimization or an exhaustive search over covariance matrices, levels, means, residual variances, or dimensions.
- The reductions recorded above do not establish the uniform squared-density bound. Endpoint checks alone do not establish the entire interpolation integral assertion, and no independent proof verification was performed by this summary.
- Random levels, matrix aggregation, and a main FDR order bound remain outside this deterministic-level target. No new proof approach beyond the candidate argument already supplied in the context pack was identified, so no duplicate approach idea was recorded.
