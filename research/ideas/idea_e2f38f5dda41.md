---
type: idea
title: >-
  Aligned negative null means defeat even a signed square-root cluster
  comparison
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - universal-order
  - negative-null-means
  - aligned-rank-facets
  - auxiliary-counterexample
  - finite-gaussian
  - independent-scoped-audit
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 5
    slot: 1
    statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
    outcome: no candidate written (show idea_e2f38f5dda41 for what was found)
---

NEW FINITE auxiliary counterexample, independently scoped checked. It strengthens the absolute-modulus obstruction in idea_0e63e86f1cc7: SAME original true-null category is insufficient even for the favorable-direction proposed comparison FDR_original<=FDR_actual-anchor+Cq sqrt(delta)(1+U) when null means can differ. It does NOT refute the main universal-order target, global zero-null-mean least favorability, or the common-anchor integrated negative-flux gate. All means and labels are preserved through contraction.

Fix0<q<=S(1), U=u_q>=1, a=u_(q/2), N=2m, sigma=N^{-3}, r=sqrt(1-sigma^2). Let Z and epsilon_(m+1),...,epsilon_N be independent standard normals. Set

$$
T_i=Z,\quad\theta_i=0\quad(1\le i\le m),
$$

$$
\theta_j=u_{qj/N}-a<0,\qquad T_j=\theta_j+rZ+\sigma\varepsilon_j\quad(m<j\le N).
$$

This is a lawful finite unit-diagonal PSD jointly Gaussian model; the first m duplicate rows make it singular, which the original target explicitly permits. EVERY coordinate is an original true null. Contract the centered weak coordinates to the ACTUAL anchor Z and preserve their displayed negative means. In the contracted model the weak score order is the original index order. Every rank j>=m qualifies exactly when Z>=a; smaller ranks can qualify only above a. Thus contracted ordinary largest-rank BH FDR is exactly S(a)=q/2.

Finite sufficient inequalities for the ORIGINAL model: put H=phi(U)/q, L=sqrt(log m), g=1/(NH), h=sigma L/2, B=g/(4sigma). Choose a finite integer m sufficiently large so

$$
h\le\min\{g,a\},\qquad \sigma a\le L/2,\qquad
\exp[-mS(L)]+2mS(B)\le1/2.
$$

Such finite m exist: h/g tends to0, sigma a/L tends to0, mS(sqrt(log m)) tends to infinity, and B grows as N^2/(4H). The displayed inequalities themselves are a checkable finite certificate; no population replacement of BH is used.

Let E={all weak |epsilon_j|<=B, and some weak epsilon_j>=L}. By a union bound and independence, P(E)>=1-exp[-mS(L)]-2mS(B)>=1/2. Adjacent weak means, including the gap from the zero-mean strong block to the first weak mean, differ by at least g, since inverse-tail differentiation gives a spacing at least (q/N)/phi(U)=g. On E, weak-noise differences are at most2sigma B=g/2, so their original index order is preserved. For Z>=0 the strong block remains above all weak coordinates: its gap from the largest weak score is at least g-sigma B>0.

For Z in [a-h,a), all m strong scores exceed every weak rank threshold u_(qj/N), j>m, because h<=g<=a-u_(q(m+1)/N). On E choose j with epsilon_j>=L. Then

$$
rZ+\sigma\varepsilon_j\ge r(a-h)+\sigma L\ge a,
$$

using a(1-r)<=a sigma^2<=sigma L/2 and h=sigma L/2. Thus T_j>=u_(qj/N); its ACTUAL global descending rank is j by the preserved order, so rank j really qualifies in ordinary BH. For all Z>=a the m strong scores already qualify rank m without needing E. Hence, since all labels are true,

$$
\operatorname{FDR}_{original}-q/2
\ge\Pr(E)\int_{a-h}^{a}\phi(z)\,dz
\ge\sigma L\phi(a)/4
\ge q\sigma(1+U)L/16.
$$

The final inequality uses phi(a)>=a S(a)>=qU/2 and U>=1. The ACTUAL-anchor spread is delta_anchor=1-r<=sigma^2; the maximum pairwise covariance distance in the cluster equals sigma^2. Either convention yields sqrt(delta)<=sigma. Thus the ratio to q sqrt(delta)(1+U) is at least sqrt(log m)/16 and diverges through the finite family. A finite universal comparison constant is impossible. All correlations are nonnegative, so both FDRs remain compatible with PRDS control at level q; this is explicitly not a counterexample to the main target.

Independent scoped audit: a fresh read-only reviewer checked order preservation, event probability, existence of finite m, actual qualifying rank, means/labels, constants and both spread conventions. It confirmed the favorable signed auxiliary-modulus obstruction and the stated limited scope. This is not native approval of a research asset.

Smallest exact sign calibration: N=2, a=u_(q/2), b=u_q, T1=Z, T2=b-a+Y with Corr(Z,Y)=sqrt(1-sigma^2); BOTH means are nonpositive. Anchor contraction has FDR=q/2. The exact original-minus-anchor gap is P(b<=Z<a,Y>=a)+P(Z<b,Y>=2a-b)>0. The growing-m certificate aligns many such distinct qualifying faces at the same anchor value; the maximum independent residual supplies the sqrt(log m) factor.

A viable cluster/peeling comparison must retain an explicit mean-threshold alignment or logarithmic spread/cluster-size charge and prove how that resource is paid. Same-category labels alone and a bare sqrt(delta) modulus do not provide it. No existing main statement, failed plan, prior observation or approval record has been overwritten.

## Tried

- Search round 5 for gaussian_bh_one_sided_universal_order_upper (slot 1): no candidate written (show idea_e2f38f5dda41 for what was found)
