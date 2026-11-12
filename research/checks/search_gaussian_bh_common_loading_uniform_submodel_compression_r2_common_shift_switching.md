---
type: search_round
title: 'Round 2: common-shift smoothing of switches and a rare active null'
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r2_s1_critical_two_atom
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r2_s2_rare_null_seed
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r2_s3_opposite_null_atoms
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:21:11.318Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested two-atom critical-switch family, changing the empirical atom mass cannot leave a fixed expected FDP or normalized-rank error: the common Gaussian shift smooths the critical switching event, and the reported binomial mass error gives an O(m^{-1/2}) bound uniformly over positive mean separation. Changing only that separation does not evade this obstruction. This conclusion is confined to the tested family and does not establish a uniform bound over arbitrary atom masses or score laws.
- The tested opposite-null-atom family has the same switching obstruction: its reported threshold-switch probability is at most a constant times the binomial mass error, so its expected full-FDP and normalized-rank discrepancies vanish. Distinct scores and reverse residual directions alone therefore do not produce a counterexample in this family.
- The tested sole-active-index construction does not turn a microscopic positive rank into a fixed expected discrepancy, even when the active index is sampled with probability tending to zero. The reported full-FDP and rank errors both vanish. This rules out that specific sparse-seed regime, rather than every possible microscopic-rank construction.
- A proof step suggested by the switching failures is an exact Gaussian smoothing bound for bounded monotone rank functions. For any nondecreasing f: R -> [0,1] and h >= 0, Tonelli applied to the Stieltjes measure of f gives E[f(Z+h)-f(Z)] <= h/sqrt(2*pi), because each interval of length h has Gaussian probability at most h/sqrt(2*pi) and the total variation of f is at most one. Conditional on the residual scores and the sampled indices, each actual normalized BH rank is such a function of the independent common Z. Consequently, once the required trimmed-rank transfer is established, abrupt switches of actual ranks can be controlled in expectation without bounding their number or differentiating the rank function. This is a possible proof step, not a completed transfer argument or an FDP monotonicity claim.

## Limitations

- This summary uses only the current stage pack and its candidate failure lines; candidate bodies were not read and their calculations were not independently reverified. No survivor or confirmed counterexample was reported.
- The round covered two-score switching and one rare-active-index regime. It did not cover arbitrary many-atom laws, growing residual dimension, large cascades of competing crossings, or distributions with many threshold-near tangencies.
- A general empirical-tail maximal estimate, two-way trimmed-rank transfer, continuous-rank/finite-grid identification, and exact total-count self-consistency at positive actual rank remain unproved by these search failures.
- The smoothing step controls monotone ranks only. A full comparison must still handle the original mixed FDP through tagged tails and self-consistency; monotonicity of the FDP is unavailable.
- The rare-seed failure does not verify the approved microscopic-rank bound's applicability in general or its locally uniform vanishing in q. Uniformity over arbitrary populations and over compact q sets remains unresolved.
