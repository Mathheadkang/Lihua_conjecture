---
type: search_round
title: 'Round 5: fixed-loading and Wasserstein hypothesis screening'
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T01:05:57.973Z'
extension_version: 0.0.4
---

## Obstructions

- Dimension growth alone does not violate the target hypotheses: finite-dimensional parameter laws can be embedded in the same fixed separable Hilbert space. Such a sequence remains eligible when its deterministic laws converge in the stipulated Wasserstein metric. However, a direction-escape construction whose unit directions remain separated and whose laws do not converge in that metric fails the convergence hypothesis; orthogonal escape without Wasserstein convergence cannot refute the continuity assertion.
- A sequence that varies the common loading instead of keeping the prescribed positive loading fixed does not test the asserted continuity implication. A singular limiting argument as the loading vanishes cannot supply a counterexample at the fixed loading required here.
- Choosing a parameter law using the realized isonormal process or common Gaussian violates the deterministic-law hypothesis. Such adaptive selections cannot refute the population functional defined for deterministic parameter laws.
- Constructions using nonunit directions or tags outside the closed tagged parameter domain violate the target's parameter hypotheses. In particular, a nonvanishing tag change is not an innocuous perturbation across zero mean under the stipulated tagged metric; alternative-tagged zero means must be approximated with their tag preserved.

## Limitations

Round 5 produced no candidate. These are hypothesis-screening obstructions, not a general proof of any of the four conclusions and not an exclusion of every admissible construction in the indicated broad directions.

The earlier calculations for common-score, two-block, flat-crossing, fold, double-contact and circular-direction families remain family-specific. This round does not establish general joint measurability or representative invariance, attainment and equality at every positive largest crossing, the dimension- and law-uniform microscopic-rank estimate, arbitrary-law Wasserstein continuity of the original common-cutoff mixed-label FDP, or canonical finite approximation and replication for arbitrary laws. In particular, the random-cutoff numerator must be controlled together with the actual largest non-strict crossing, including competing crossings, vanishing positive ranks and rank one.

Finite dimension growth inside a fixed Hilbert space remains admissible; only proposed sequences failing the actual Wasserstein hypothesis are excluded. No conclusion about continuity uniform in a vanishing common loading, exchange of atomization and variation limits, first-variation identities or optimization conditions follows. No genuinely new general proof step was established beyond the existing board, so no approach idea is recorded.
