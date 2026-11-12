---
type: search_round
title: >-
  Round 2 obstructions: random signed corrections and independent constant
  blocks
target_asset: gaussian_bh_finite_signed_p_path_identity
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - cand_gaussian_bh_finite_signed_p_path_identity_r2_s1_randomized_simes_excess
  - >-
    cand_gaussian_bh_finite_signed_p_path_identity_r2_s2_unbalanced_independent_constant_block
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:30:56.090Z'
extension_version: 0.0.4
---

## Obstructions

- An all-null Gaussian model with FDR exceeding the unit-constant Simes bound does not refute a signed identity whose random downward-jump term accounts for that excess. In the tested full-rank two-coordinate model with correlation $-1/2$ and $q=1/4$, the exact calibration is $F=q(1+\mathbb E D)$ with $0\leq D\leq1/2$; the numerical value $F\approx0.25652759>q$ agrees with this identity. The candidate fails NOT. This is a failure of the unit-constant Simes bound in the tested model, not a refutation of the main universal-constant target.
- A large independent block of conditionally constant paths does not itself break the finite-event description or signed identity: retaining the constants in the non-strict BH count gives the tested $N=1000$ construction exactly two clipped-affine regimes, both matching the direct conditional rejection calculation. The candidate fails NOT. This calibration does not extend to every configuration of constant ties or independent blocks.

## Limitations

Both recorded round-2 candidates fail NOT; there is no surviving counterexample. The additional constant-tie and endpoint search produced no plausible candidate, rather than a general exclusion argument. The decimal FDR above is numerical; the stated signed calibration and two-regime formulas are exact.

The round does not prove the general identity. Joint measurability, a measurable finite event construction, arbitrary simultaneous crossings and threshold ties, the endpoint and derivative assertions in all admissible models, conditional change of variables, and absolute integrability of the random signed jump sums still require general proofs. No quantitative bound on the positive jump budget, and hence no main universal-constant FDR bound or refutation, is established.

These examples calibrate mechanisms already explicit in the target statement; they do not supply a genuinely new proof step warranting a separate approach idea.
