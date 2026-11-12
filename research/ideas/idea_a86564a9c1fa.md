---
type: idea
title: 随机化Mills幅度以消去秩标签：有限方向的后验信息迹界
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - randomized-marks
  - posterior-information
  - direction-entropy
---

Concrete refinement of idea_a7a7c3543b07, to prove in full and independently audit before treating as a lemma. Let v_1,...,v_K be the distinct oriented true-null vectors in a finite model (false directions unrestricted). Under Q=f gamma/F, let alpha_g(G) be the proportion of the actual V selected true nulls belonging to group g, and eta(G)=H/h(u_R) in (0,1]. Introduce a finite terminal random label L in {0,1,...,K} by Q(L=g|G)=eta alpha_g for g>=1 and Q(L=0|G)=1−eta. Give labels marks c_g=v_g/H and c_0=0. Then b=B/f=E_Q[c_L|G] EXACTLY. This Bernoulli radial randomization removes the rank R from the label without changing b; no independent Gaussian-mixture representation is assumed.

The posterior label martingales and finite-entropy Ito identity described in idea_a7a7c3543b07 imply
|M| <= F sqrt{2 I_Q(L;G) E_Q integral Var(c_L|F_t)dt}.
Since a_t=E[c_L|F_t], the integrated mark variance is E||c_L||²−E integral||a_t||² <=(1−x)/H². Consequently
|M| <= (F/H) sqrt{2 I_Q(L;G)(1−x)} <=(F/H) sqrt{2 H_Q(L)(1−x)} <=(F/H)sqrt{2log(K+1)(1−x)}.
Localization/log-regularization, Brownian innovation identification and integrability must be written out; the finite-label entropy is bounded. This uses the exact signed trace, not a sum of positive face costs.

A selected true null in group g requires v_g·G>=U because all null means are <=0. Thus F<=min(1,Kq), without any restriction on false directions or actual rank cascades. For K<=2 and U>=3, the certificate gives |M|<=q sqrt(1−x), since 2sqrt(2log3)/H<1. This extends the square-root budget to arbitrary finite models with at most two distinct true-null directions, including genuinely noncollinear and mixed-label cases; it is a scoped candidate derivation, not a native-approved theorem or the unrestricted target. K=1 has the sharper elementary centering bound |M|<=F/H sqrt(1−x)<=q/H sqrt(1−x), independently checked during round4.

Remaining obstruction: K or H_Q(L) may grow arbitrarily, so this does not establish the universal mixed budget. A future route could compress nearby oriented marks with a quantitatively controlled posterior-information error, retaining actual selected weights; no such geometric compression theorem is currently proved. High raw label entropy among nearly coincident directions should not be treated as genuine Gaussian complexity. Do not replace F/H by q in the general information certificate.
