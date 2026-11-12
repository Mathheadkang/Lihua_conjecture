---
type: search_round
title: Round 2 opposed null blocks for the one-sided universal order bound
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 2
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - cand_gaussian_bh_one_sided_universal_order_upper_r2_s2_two_sign_null_blocks
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:29:48.227Z'
extension_version: 0.0.4
---

## Obstructions

- The tested positive- and negative-unit-loading null blocks have reported exact FDR=q, including growing dimension and unbalanced block sizes, so they do not produce the normalized divergence needed to refute the universal order bound.

## Limitations

The small_cases candidate passed H1 through H5 and failed NOT; the other four directions produced no candidate files, and no survivor was reported. This summary uses the supplied failure line without independently reconstructing candidate calculations. The nonexhaustive search does not cover arbitrary growing covariance rank, many-direction configurations, or general mean and covariance sequences, and supplies no proof or independent verification verdict.
