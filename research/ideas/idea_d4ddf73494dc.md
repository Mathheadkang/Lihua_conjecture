---
type: idea
title: >-
  Exact shallow-null centering changes largest BH rank pointwise but full FDR
  moves oppositely
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

This is an exact pointwise centering/dilution diagnostic, not a counterexample to a coarse expected-FDR comparison or the main theorem. Write u(t)=barPhi^{-1}(t), choose 0<q<1/2, and put U=u(q), z_0=u(q/4), a=3(z_0-U)/2, and mu=z_0+u(5q/6). With Z standard Gaussian define T=(Z,Z-a,mu-Z). The means are (0,-a,mu), the true-null set is exactly {1,2}, and the fixed covariance is vv^T for v=(1,1,-1). Center only the second null to obtain T^0=(Z,Z,mu-Z), retaining covariance, labels, alternatives, all three coordinates, and the original ordinary BH rule. As q tends to zero, a U tends to log(8), so the changed null lies in the shallow strip -2log(U)/U<theta_2<0 for all sufficiently small q.

Set L=max{u(q/3),mu-u(2q/3)} and H=min{U+a,mu-U}. Both terms defining L are strictly below z_0 and both terms defining H are strictly above z_0; hence E={L<Z<H} has positive probability. On E the uncentered model has p_1<q/3, p_2>q, and 2q/3<p_3<q. Its actual largest BH crossing is R=1, V=1, FDP=1. In the centered model all three p-values are below q, so its actual largest crossing is R^0=3, V^0=2, FDP^0=2/3. Thus the pathwise domination FDP<=FDP^0 is false, even for shallow negative null means and exactly unchanged covariance and labels.

Quantile expansion u(cq)=U-log(c)/U+o(1/U) gives U(L-U) tending to log(16/5) and U(H-U) tending to log(24/5). Consequently P(E)/q tends to 5/16-5/24=5/48. The pointwise reversal contributes q*(5/144+o(1)) to E[(FDP-FDP^0)1_E]. This is only an O(q) effect.

The full expectations move in the opposite direction here. To compute them, put x=U(Z-U)>=0, y=exp(-x), and use the Gaussian tail asymptotics. The three rescaled p-values p_i/q converge to (y,8y,5/(24y)) in the original model and (y,y,5/(24y)) in the centered model. Also the law of y on the false-rejection tail, divided by q, converges to Lebesgue measure on (0,1); dominated convergence applies because every false rejection requires Z>=U and the x-density divided by q is bounded by a constant times exp(-x). Threshold boundaries have zero limiting measure.

For the centered model, limiting FDP is 1 on 0<y<5/24 and 2/3 on 5/24<y<1. Its FDR/q therefore tends to 5/24+(2/3)(19/24)=53/72. For the original model, rank three is impossible in the limit; limiting FDP is 1 on 0<y<5/16, 1/2 on 5/16<y<2/3, and 0 on 2/3<y<1. Its FDR/q tends to 5/16+(1/2)(2/3-5/16)=47/96. Thus (FDR^0-FDR)/q tends to 71/288>0: centering raises the full expected FDR in this example, despite lowering it pointwise on E.

Both full FDRs are at most P(Z>=U)=q, directly from the unchanged true-null directions. This already-obstructed scalar family is therefore not entered as a new main-theorem candidate. The calculation blocks a pathwise centering shortcut; it neither refutes expected-FDR monotonicity nor obstructs FDR(theta)<=C FDR(theta_nulls_centered)+Cq. Such an unrestricted coarse comparison remains unresolved.
