---
type: search_round
title: Round 1 obstructions for rank-one translated BH congestion
target_asset: gaussian_bh_one_sided_translated_cell_mehler_congestion
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_one_sided_translated_cell_mehler_congestion_r1_s1_opposite_ladder_ties
  - >-
    cand_gaussian_bh_one_sided_translated_cell_mehler_congestion_r1_s2_two_opposed_scores
  - >-
    cand_gaussian_bh_one_sided_translated_cell_mehler_congestion_r1_s3_boundary_spike_opposite_alternatives
statement_digest: d49b6ceedd94063add2326953562443ef9d47a5aaa10af748c68abcc336945a7
performed_by: unknown
created_at: '2026-11-10T23:02:13.805Z'
extension_version: 0.0.4
---

## Obstructions

- **Opposite-direction threshold ladders have only boundary congestion.** For every finite N >= 2, 1 <= k < N, and 0 < q <= S(1), take k null copies with mean zero and direction +1, and N-k alternatives with direction -1 and means 2u_{k+j}. The exact forced-rank masks exclude ranks r < k, confine every r > k to y = 0, and leave rank k for y > 0. Thus, almost everywhere, H_q(y) = 1{y >= 0} exp(-u_k y-u_k^2/2); the physical null multiplicity k cancels 1/k. Every positive-time Mehler law ignores the singleton, and, with L = log(1/q), sigma^2 = 1-exp(-2/L), its smoothed supremum is at most phi(u_k)/(u_k sigma) <= 2qk/(N sigma) <= 2q sqrt(L)/sqrt(1-exp(-2)). Its mass and actual FDR both equal qk/N. This rules out the entire exact ladder family, including arbitrary N,k depending on q, rather than merely a fixed model. Candidates cand_gaussian_bh_one_sided_translated_cell_mehler_congestion_r1_s1_opposite_ladder_ties and cand_gaussian_bh_one_sided_translated_cell_mehler_congestion_r1_s3_boundary_spike_opposite_alternatives cover the same family; the latter has the narrower range N >= 3, 2 <= k < N. They are not independent families. Arbitrarily large unsmoothed boundary values do not refute part (b).

- **The specified two-score positive-width overlap has bounded amplitude.** For N = 2, d = 1, a_1 = +1, a_2 = -1, theta_1 = 0 and theta_2 = u_1+u_2, the full forced-rank density, up to singleton values, is 1{y > 0} exp(-u_1 y-u_1^2/2) + (1/2)1{0 <= y <= u_1-u_2} exp(-u_2 y-u_2^2/2). Hence simultaneous positive-width cells alone do not force divergence: the density is pointwise at most 7q sqrt(log(1/q)), and every Mehler average satisfies the same bound uniformly in x and admissible q. Its mass and actual FDR are 3q/4. This is the exact mean choice in cand_gaussian_bh_one_sided_translated_cell_mehler_congestion_r1_s2_two_opposed_scores, not a conclusion for arbitrary two-score means.

## Limitations

- No arbitrary rank-one mixed-label arrays were covered: general null means, arbitrary alternative means, mixtures of null directions, perturbed ladders with positive-width higher-rank cells, and many simultaneously overlapping positive-measure rank cells remain unresolved.
- No rank-two or higher correlated arrays, general Gram matrices, or growth of dimension and direction count were tested. No general weighted congestion estimate for the sum of full forced-rank masks was established.
- Removing a finite union of equality hyperplanes is legitimate under the positive-variance Mehler law, but does not bound congestion on positive-measure regions. The half-line kernel estimate controls a single kernel; summing it over unrestricted cells can lose the needed universal constant.
- The checks establish the mass identity only in these explicit families. They neither prove part (a) for every model nor prove the universal part (b). All three candidates failed NOT; no counterexample survived this round.
- The initial pack contained only failure lines. Native show of Object and Checks for each named candidate was needed to recover the parameter ranges, exact supports, constants, and the duplicate ladder-family coverage before stating these obstructions.
