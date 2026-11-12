---
type: idea
title: 固定复制数的小噪声分裂归约与二阶近极值尺度障碍
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - exact-cloning
  - noise-splitting
  - stationarity-obstruction
---

Scoped new calculation, requiring an independent full proof audit before use as an established result. It explains why the proposed tiny-noise clone split currently does not close the main proof. No target or plan was modified.

Clone every original coordinate K times, same statistic and label, total NK coordinates. Perturb only group i by T_ib=theta_i+sqrt(1−epsilon²)(T_i−theta_i)+epsilon xi_b, with independent standard Gaussian xi_b in new latent directions. Unit variances and lawful Gaussian covariance are retained. For fixed finite N,K,q, let u_r=S^{-1}(qr/(NK)) and d=min_{r<NK}(u_r−u_{r+1})>0. If any partly selected group has copy score range<d, the largest qualifying rank cannot select just j<K of its copies: at rank r each selected copy exceeds u_r; every omitted copy is >u_r−d>=u_{r+K−j}, so r+K−j also qualifies. Thus all groups are fully selected or omitted. The untouched groups are exact ties. Outside the perturbed group's bad-range event, expanded ordinary BH is precisely original BH with coordinate i replaced by min_b T_ib, with the identical true-null FDP. The bad event has probability at most 2K² exp(−d²/(4epsilon²)), so bounded-FDP errors are smaller than every fixed power of epsilon for this fixed model.

For a PD original covariance, Taylor expansion gives F_split=F+epsilon m_K ∂_iF+O(epsilon²), m_K=E min_b xi_b<0. For a free-sign mean, compensate by shifting every mean in group i by −epsilon m_K. Then F_split=F+epsilon²[v_K C_ii−(Sigma C)_ii]+o(epsilon²), C=(1/2)Hess_theta F and v_K=Var(min_b xi_b). The covariance perturbation is epsilon²[v_K e_i e_i^T−(e_i Sigma_{i·}+Sigma_{·i} e_i^T)/2]. For K2, m_2=−1/sqrt(pi), v_2=1−1/pi. At a genuine all-model global maximizer with a lawful compensation, this would force (Sigma C)_ii>=v_K C_ii, and formally nonnegativity of (Sigma C)_ii as K increases and v_K tends to0.

Obstructions: upward compensation is unlawful at zero-mean true nulls; a global finite PD maximizer has not been proved; a near-extremizer gap need not be o(epsilon²) within the model-dependent tiny grid scale d; fixed-N logdet regularization is not invariant under cloning and cannot justify the expanded-model comparison. The leading flux is a signed face/mean derivative, and the second order is a covariance contraction rather than a positive mean-square FDP energy. Finite-noise splitting keeps a full signed FDP difference for which no new uniform estimate is known. Hence this calculation supplies necessary formal stationarity information, not a valid main proof plan.
