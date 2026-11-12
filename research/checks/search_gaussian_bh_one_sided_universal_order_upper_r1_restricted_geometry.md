---
type: search_round
title: >-
  Round 1 restricted-family obstructions for the one-sided Gaussian BH order
  bound
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_one_sided_universal_order_upper_r1_s1_exponential_survival
  - >-
    cand_gaussian_bh_one_sided_universal_order_upper_r1_s2_null_span_two_rare_alternative
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T20:00:59.357Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested conditional-independent common-factor regime with small shared null loading, exponentially varying finite rare-alternative survival profiles remain controlled by the reported exact conditional-null density envelope: the actual full-procedure FDR is at most $4q_j\sqrt{\log(1/q_j)}$. Changing the rare-alternative survival profile in this checked regime therefore does not provide the unbounded normalized FDR required by NOT. The native observation `idea_286740ee9cf8` records this argument.
- If the Gaussian null directions span at most two dimensions, any false rejection in the original full BH procedure requires a null statistic at least $U=\overline\Phi^{-1}(q)$. Nonpositive null means then force the norm of the two-dimensional null projection to be at least $U$. Its radial probability is $e^{-U^2/2}=O(q\sqrt{\log(1/q)})$, bounding the entire actual FDP expectation regardless of the number of null directions or the rank and multiplicities of the rare alternatives. Thus growing alternatives alone cannot evade this null-span obstruction. The native observation `idea_743989517bf4` records the argument.
- The reported heterogeneous one-factor residual-variance calculation gives an integrable conditional tail-probability envelope for shallow-null contributions. This obstructs the tested residual-degeneracy mechanism within that one-factor family. It is a tail-probability bound, not a uniform conditional density cap; no density cap is inferred as residual variance vanishes. The native observation `idea_0b8c381bdc41` records this separate argument.

## Limitations

Both recorded round 1 candidates satisfy their model checks and fail NOT; neither is a counterexample. The third worker supplied a family obstruction but no candidate. This summary uses the supplied candidate failure lines, reports, and observation titles, rather than independently re-auditing their proofs; the existing native observations need no duplicate record.

Arbitrary higher-rank null geometry remains unresolved, including growing null span, simultaneous q-dependent degeneracies, unrestricted signed covariance, and rare alternatives coupled to the original largest BH crossing. The two-dimensional radial estimate is not a rank-uniform proof in general dimension. These family results do not supply a signed OU payment, a general model-adaptive rare-alternative preservation bound, or an unrestricted fixed-covariance zero-null comparison. The independently verified deep-negative-null boundary-strip contribution does not control the remaining shallow strip and does not authorize deleting or recentering coordinates. A complete proof must still bound the entire original finite-model supremum with universal constants and receive fresh independent verification; the main theorem remains draft and untouched.
