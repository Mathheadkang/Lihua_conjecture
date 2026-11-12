---
type: search_round
title: >-
  Conditional compound calibration round 2 - finite nonsaturated conditional
  kernels
target_asset: gaussian_bh_conditional_compound_calibration
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_conditional_compound_calibration_r2_s1_heterogeneous_compound
  - >-
    cand_gaussian_bh_conditional_compound_calibration_r2_s1_productized_rank_marginals
  - cand_gaussian_bh_conditional_compound_calibration_r2_s2_moving_active_null
  - >-
    cand_gaussian_bh_conditional_compound_calibration_r2_s3_nonattained_crossover
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T16:01:09.554Z'
extension_version: 0.0.4
---

## Obstructions

- Dependence-driven rank-mixture or harmonic constructions cannot refute this target while their conditional joint law is not the product of the coordinate kernels. Preserving the coordinate marginals and then making the coordinates independent changes the joint rejection events, so the dependent calculation cannot be transferred unchanged. In the tested four-null independent product adaptation, exact enumeration of all $5^4=625$ support outcomes gives $M_q=K_q=1$ and FDR $1/10<1/5$ at $q=1/10$. This is evidence for that adaptation, not a general exclusion of product laws with those types of support.
- The entire recorded moving-active-null family fails NOT despite arbitrary dimension, a varying active null identity, finite nonsaturated envelopes, and marginal dependence. Its original null set is fixed; conditional on each integer state $Z=j$, one original null has law $bU$, inactive nulls equal one, and $B$ original nonnulls equal zero, with $b=q/(aN)$ and $0<q\le a<1/2$. The conditional coordinates are independent. The actual largest BH rank is $B+1$ exactly when the active null is at most $q(B+1)/N$, otherwise $B$ (including zero). Therefore conditional FDR is $\min\{a,1/(B+1)\}\le a$, whereas $M_q=K_q=a/q$ gives bound $2a<1$. Increasing $N$, making the null fraction approach one, or moving the active original label does not remove this obstruction within the recorded family.
- A finite envelope supremum need not be attained to be the target's correct envelope; taking a maximum over positive levels would change the statement. In the recorded continuous two-coordinate crossover family, $q=1/10$, $m(z)=3/4+z/2$, and $F_z(t)/(2t)=m(z)(1-t)$ for $0<t\le q$. Thus $M_q(z)=m(z)$ is approached by rational $t\downarrow0$ and never attained, while $K_q(z)=\max\{1,m(z)\}$ crosses one. Conditional FDR is exactly $(189/2000)m(z)<(1/5)\max\{1,m(z)\}$ throughout the family. Nonattainment, continuous conditioning, and the crossover do not produce a violation in these kernels.

## Limitations

- All four recorded round-2 candidates satisfy their listed hypothesis checks and fail at NOT. No survivor was found. Together with round 1 this gives eleven failed candidates, not a proof of the lemma, universal factor $2$, or either unrestricted main theorem.
- The independent heterogeneous two-null candidate has $M_q=K_q=1$ and exact FDR $41/400$, above the unit-constant value $qK_q=1/10$ but below the target bound $1/5$. It rules out the unit-constant variant for this law; it does not refute the stated factor $2$ or establish its optimality. Individual conditional superuniformity is not a hypothesis and cannot be silently imposed to exclude this candidate.
- The dependence-based harmonic construction is not an additional valid survivor. Its conditional-independence failure is separate from the four recorded candidates' failed-NOT outcomes. Likewise, the moving-active and continuous-nonattainment kernels are valid conditional product tests; their marginal dependence or lack of an attained supremum is not a hypothesis failure.
- The round extends coverage to one arbitrarily large one-active-null family and one continuous nonconstant envelope crossing one, but does not exhaust kernels with several interacting active nulls, arbitrary heterogeneous conditional laws, nontrivial nonnull distributions in high dimensions, or general finite nonsaturated envelopes. The exact discrete enumerations concern only the specified finite support laws. No general family obstruction follows merely from either enumeration.
- All candidate calculations retain the original null labels and actual largest qualifying BH rank with non-strict comparisons. Earlier endpoint-atom and infinite-envelope conventions remain part of the target; the new tests do not authorize replacing the rank by a surrogate, dropping $t=q$, requiring an attained supremum, or replacing the summed-CDF envelope by a sum of individual suprema. General conditional validity and its unconditional implication still require a complete argument; Gaussian order estimates and noise-floor removal remain outside this search result.
