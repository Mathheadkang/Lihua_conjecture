---
type: search_round
title: 'Round 1 boundary, mark, and moment obstructions for array compactification'
target_asset: gaussian_bh_exchangeable_array_variational_compactification
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r1_s1_singular_zero_mean
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r1_s2_two_mark_atoms
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r1_s3_infinite_moment_common_mean
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:48:00.757Z'
extension_version: 0.0.4
---

## Obstructions

- Singular all-copy covariance does not by itself produce dimension dependence or a discontinuity at the zero-mean boundary: the tested all-copy family has exact dimension-independent FDR and its boundary limit is continuous. This blocks that family as a counterexample, rather than establishing continuity for all singular arrays.
- False-zero marking cannot lower the moment penalty while improving upon canonical retagging of the same observations. Replacing every mark $(\theta_i,\ell_i)=(0,0)$ by $(0,1)$ preserves means, covariances, joint exchangeability, all p-values, BH ranks, and $M_2$, and increases each finite FDP by the fraction of rejected newly true coordinates. The tested two-mark zero-mean family has finite FDR exactly $q/2$ and becomes $q$ after canonical retagging; it also admits the reported explicit marked directing representation. Once limiting completion is established separately, the finite pointwise comparison passes to the limit. Thus noncanonical zero marks alone cannot defeat the claim that a canonical maximizer can be chosen, conditional on existence; this neither characterizes every maximizer nor establishes existence.
- Escape to an infinite second moment alone does not contradict a value or continuity assertion made on all of $\mathfrak P$: the tested shared heavy-tailed null-mean family retains a bounded continuous FDR functional despite infinite limiting $M_2$. Attainment of the penalized extrema is expressly asserted within $\mathfrak P_2$. An infinite-moment law is therefore outside the asserted optimizer class; moment divergence by itself is not a failed attainment claim. This obstruction is confined to the tested shared-mean family and does not establish continuity under arbitrary unbounded-mean limits.

## Limitations

All three supplied candidates failed their NOT check; no counterexample survived. This record summarizes the supplied failure lines and target statement without independently rereading candidate bodies. Coverage was limited to boundary_degenerate, small_cases, and drop_hypothesis.

The round did not establish the uniform submodel comparison, its repeated-index error, joint finite-subarray continuity, or compactness and lower semicontinuity on moment sublevels. It did not test general heterogeneous mean/covariance arrays or prove the canonical finite-supremum equalities with simultaneous moment control. The latter do not imply simultaneous deterministic finite FDR/moment approximation of arbitrary outer parameter mixtures.

The terminal-rank-one logarithmic bound, normalized $q$-coercivity, existence and vanishing-penalty limits, all lawful comparison and signed moment-expansion claims, and common-loading removal remain unproved by this round. General value claims and finite-second-moment attainment must remain separate, and outer mixtures remain expectations of conditional Gaussian FDRs rather than a single Gaussian model. No uniformity in $\sigma$, normalized bound as $\delta\downarrow0$, or main universal-order upper bound follows.

The example's marked representation does not prove the general marked Dovbysh--Sudakov extension, measurable mark recovery, the unit-ball bound, jointly measurable isonormal realization, or affinity/integrability for maximum component selection. The independently verified and researcher-approved primary-source theorem gate for clause 6 remains in force. The canonical-retagging proof step was recorded separately as draft approach idea_aec904d88a42; it does not bypass any of these obligations.
