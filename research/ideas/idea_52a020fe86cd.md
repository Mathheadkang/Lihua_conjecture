---
type: idea
title: >-
  Mean-ordered alternative insertion can unlock a harmonic Gaussian FDR
  increment
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - universal-order
  - alternative-insertion
  - harmonic-gate
  - mean-order-obstruction
  - finite-gaussian
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 4
    slot: 3
    statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
    outcome: no candidate written (show idea_52a020fe86cd for what was found)
---

DRAFT exact finite auxiliary counterexample to a proposed proof-induction step, not to the main uniform-order bound. The attempted dimension induction kept a fixed BH grid c*k while adding all original nulls first and positive alternatives in descending mean order, hoping that each added alternative increases FDR by at most A c[1+S^{-1}(c m)] at stage m. The following family disproves that local increment bound EVEN with the stated mean order.

Fix0<q<=S(1), integer N>=3 and c=q/N. Put u_r=S^{-1}(cr), v_r=S^{-1}(c(r-1/2)), r=3,...,N, and let Z standard normal. The OLD N-1 model has the one original true null T0=Z and N-2 alternatives

$$
T_r=u_r+v_r-Z,\qquad r=3,\ldots,N.
$$

Their positive means b_r=u_r+v_r strictly decrease with r. Run old BH at level c(N-1), so its grid is exactly c*k. Its Gaussian covariance is a unit-diagonal PSD rank-one Gram matrix; no non-Gaussian evidence is used. If the null were selected at old rank k>=2, the (k-1)th ordered alternative, indexed r=k+1, would require Z<=u_(k+1)+v_(k+1)-u_k<u_k, whereas null selection requires Z>=u_k. This is impossible. For Z>=u1 the null is selected at rank1 and all higher ranks fail; hence FDR_old=c exactly.

Choose ANY0<delta<b_N and add the new alternative

$$
T_*=Z+\delta.
$$

Its mean is smaller than every existing alternative mean, so adding it LAST respects descending positive-mean order. All original coordinates' means and covariance marginal remain unchanged, and the full enlarged model is still jointly Gaussian with unit-diagonal PSD rank-one covariance. The original true-null set remains {0}; T_* has strictly positive mean and is not relabelled as null. Run new BH at level cN=q, retaining the SAME grid c*k. Distinguish these levels explicitly; this is a fixed-grid induction comparison, not two models run at the same nominal level.

Whenever the null is selected the new shifted copy has an even smaller p-value and is selected too, so rank1 cannot carry false discoveries. For every Z>=u2, rank2 qualifies and all ranks>=3 fail because v3<u2; contribution to FDR is S(u2)/2=c. For r=3,...,N, the null is selected at actual largest rank r precisely on the disjoint interval

$$
Z\in[u_r,v_r],\qquad\Pr\{u_r\le Z\le v_r\}=c/2.
$$

At rank r both the null and its new alternative copy pass, while the required (r-2)th old alternative passes exactly when Z<=v_r. Any higher rank l>r fails since v_l<=v_(r+1)<u_r. Conversely if the null is selected at a rank r>=3 these same conditions are necessary. Consequently

$$
\operatorname{FDR}_{new}=c+\frac c2\sum_{r=3}^N\frac1r,\qquad
\operatorname{FDR}_{new}-\operatorname{FDR}_{old}=\frac c2(H_N-H_2).
$$

At fixed q, this increment divided by c[1+S^{-1}(q)] diverges as N grows. Thus no finite universal constant bounds the proposed ordered one-alternative increment. The full FDR is only of order q log(N)/N and tends to zero; this does NOT refute the main target. It also illustrates why per-coordinate or per-insertion budgets can miss a gate unlocking stored harmonic rank structure.

The parent and a separate read-only scout independently reconstructed the weak-copy gate and exact rank intervals. The scout performed4434 deterministic interior rank checks for N10,100,1000 with zero mismatches, used as calibration only. The analytic largest-rank calculation above is the claimed candidate argument; it remains a draft observation, not native approval or a main-target counterexample. A stronger-gate variant T_*=2u1-Z added last has increment additionally containing S(2u1-u2)/2, but violates descending mean order and is not needed here.

Any viable insertion approach needs an amortized global resource or a different, precisely specified order; arbitrary insertion and descending means alone do not provide the missing Gaussian uniformity. Preserve the existing one-null harmonic family idea_7d255a49227b and all prior plans unchanged.

## Tried

- Search round 4 for gaussian_bh_one_sided_universal_order_upper (slot 3): no candidate written (show idea_52a020fe86cd for what was found)
