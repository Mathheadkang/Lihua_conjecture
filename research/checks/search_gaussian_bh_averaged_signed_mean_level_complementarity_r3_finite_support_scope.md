---
type: search_round
title: >-
  Round 3: finite-support posterior domination and remaining general-law
  obligations
target_asset: gaussian_bh_averaged_signed_mean_level_complementarity
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: e3dcfc508ee344fb52d4454b0676313187354eefcb69339fb28a33f503d7f350
performed_by: unknown
created_at: '2026-11-09T08:17:13.953Z'
extension_version: 0.0.4
---

## Obstructions

- The actual tested family reported this round consists of small examples with a fixed finite-support directing law. The pack gives neither explicit objects nor candidate calculations, and lists no round-3 candidates. Its reported obstruction has the following elementary scope: if pi=sum_i alpha_i delta_{x_i}, with all alpha_i>0, then every normalized nonnegative posterior density satisfies p(x_i)<=1/alpha_i. Consequently, if the integrated selector weights have a uniform finite total mass C, their mean-density coordinates satisfy 0<=G(x_i)<=C/alpha_i, and this fixed finite-support family is uniformly integrable. This rules out concentration of posterior densities alone as a counterexample within that family; applying it to all target selector vectors still requires checking their normalization and uniform weight bound. The finite-support reduction is recorded as draft approach idea_1fa28e9136fb, not as a proof of the target.
- The earlier strictly negative true singleton and strictly positive false singleton obstructions remain relevant only to maximum-specific conclusions: the former can improve by moving its mean toward zero, and the latter has zero full-FDP payoff and can improve by shrinking its positive mean. Each fails actual normalized global maximality before a complementarity violation is checked. This round supplies no new actual maximum, and these singleton failures do not exclude those laws from the target's fixed-law clauses.
- Earlier extreme-mean, posterior-concentration, and level-zero explorations carry no explicit new objects or checked calculations in this pack. They therefore supply no additional certified whole-family obstruction. The earlier conditional cutoff/marginal-validity reduction is already recorded as idea_fd90b2fd8168; it is not reclassified as a proved level-coercivity result here.

## Limitations

No candidate was written this round, no candidate reached a checked conclusion failure, and no actual canonical normalized global maximizing law was constructed or verified. The actual-maximum hypothesis and canonical exclusion of a zero-mean false tag remain essential for clauses 4 and 5; findings for arbitrary finite-support laws do not test those conclusions without these hypotheses.

The finite-support posterior estimate depends on the fixed positive atom weights. It does not establish uniform absolute continuity for a fixed diffuse or countably infinite-support law, nor uniformity across laws with vanishing atom weights. Failure of this simple bound outside finite support is not a counterexample. The target fixes pi and all private regularizers; varying-law or vanishing-noise/cutoff sequences would not by themselves refute its compactness claim.

The pack does not supply the selector definitions needed to certify their normalization, their integrated total-weight bound, or their scalar-coordinate bounds. Joint measurability, representative invariance, general-law gradient uniform integrability, weak compactness, active support representation and nested-intersection support limits remain unproved here. So do the survival-flux identity, extension from lawful velocities to K, weak closedness and separation of C^-+K^circ, and averaged matching at actual maxima. The finite-support reduction proves none of these general obligations.

The earlier conditional level-zero bound still needs its approved-model dependency checks, and this round does not certify a common coercive level interval, the zero-penalty value limit, or the vanishing signed mean penalty. No unrestricted extremal flux estimate, smoothing/cutoff derivative limit, or either unrestricted Gaussian BH main bound is established.
