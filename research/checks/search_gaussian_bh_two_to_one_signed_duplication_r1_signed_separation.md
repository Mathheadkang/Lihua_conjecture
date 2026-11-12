---
type: search_round
title: Signed-duplication first-round boundary and rank obstructions
target_asset: gaussian_bh_two_to_one_signed_duplication
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 987e0b4167580298c08435b5d415d205e1f3153780e8613a7e16afb82038f6a6
performed_by: unknown
created_at: '2026-11-07T02:40:05.266Z'
extension_version: 0.0.4
---

## Obstructions

- Boundary, zero-statistic, and threshold-tie constructions cannot make both signed copies reject: the larger member of each complementary p-value pair is at least one half, whereas every duplicated BH threshold is at most q, strictly below one half.
- Small finite models and large-dimensional extremal configurations retain the same potentially qualifying ranks: the smaller signed p-values are exactly one half of the original two-sided p-values, and their first N thresholds are qk/(2N).
- Singular or degenerate covariance does not invalidate Gaussian admissibility of the signed vector: signed duplication is a linear image and its covariance has unit diagonal and is positive semidefinite.
- A false-rejection-count reversal cannot arise merely by changing nonzero means: each rejected original two-sided true null contributes a rejected signed coordinate with zero mean; additional negative signed means can only add one-sided true-null rejections.

## Limitations

No concrete candidate was produced in this round. The family-level observations above summarize the reported boundary, small-model, hypothesis, known-example, and extremal searches; they are not a completed proof or an independently verified result. In particular, a full argument must still show that the largest qualifying rank and the resulting rejection sets coincide for every finite realization, including arbitrary multiplicities and zero rejections. No uniform finite-constant bound for either main FDR target was established or tested by this reduction search.
