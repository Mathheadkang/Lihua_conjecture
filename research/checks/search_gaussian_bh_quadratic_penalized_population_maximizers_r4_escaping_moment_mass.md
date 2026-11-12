---
type: search_round
title: >-
  Escaping second-moment mass does not obstruct fixed-cap Wasserstein
  compactness
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_quadratic_penalized_population_maximizers_r4_s1_positive_cap_escaping_null_mass
  - >-
    cand_gaussian_bh_quadratic_penalized_population_maximizers_r4_s2_escaping_positive_atom
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:55:39.431Z'
extension_version: 0.0.4
---

## Obstructions

- Escaping mean mass under a uniform finite second-moment cap cannot retain a nonvanishing first-moment tail: for every law in the cap and every R > 0, the integral of |theta| over |theta| > R is at most C/R. In particular, an atom of weight p at mean magnitude R with p R^2 <= C contributes at most C/R to the first-moment transport cost of moving its mean to zero while retaining its direction and tag; the completion permits zero means with either tag. Thus the positive- and negative-mean escape families tested this round cannot defeat Wasserstein compactness by carrying second moment to infinity. A strict drop in second moment at their Wasserstein limit is compatible with the claimed lower semicontinuity, and is not a failed conclusion. Both recorded candidates fail NOT; the candidate that also checked full BH FDR found its convergence compatible with the limit law. This is evidence about these escape mechanisms, not a proof of the complete target.

## Limitations

- The round tested two escaping-atom families in the boundary-degenerate and small-case directions. It did not test every bounded-second-moment sequence or establish closedness of the full tagged domain. The first-moment tail estimate is a compactness ingredient, not a completed proof of compactness or lower semicontinuity in the stated parameter space.
- The candidate summaries do not establish general penalized attainment, applicability of the fixed-loading FDR continuity theorem to arbitrary maximizing sequences, canonical approximation with convergent moments, vanishing-penalty limits, signed transport comparisons, or simultaneous finite endpoint recovery with o(epsilon) errors.
- FDR convergence was reported for the escaping-null candidate only; the positive-atom candidate summary establishes its Wasserstein and moment behavior. No additional FDR calculation is inferred for that candidate.
- No claim is made about varying ambient dimension, attained unpenalized maxima, convergence of maximizing laws as the penalty vanishes, finite-model derivatives, or unrestricted Gaussian BH order bounds. Failure to find a counterexample does not verify the target.
