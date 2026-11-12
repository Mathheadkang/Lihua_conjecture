---
type: idea
title: >-
  Bounded-entropy inherited Gaussian null compression loses amplification even
  with unbounded carrier count
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - weighted-stratification
  - conditional-calibration
  - bounded-entropy-carriers
---

## Scope and status
This standalone weighted-BH diagnostic extends [the finite inherited-null carrier calculation](idea_efbcf7095e77.md) to an arbitrary finite number of carriers at each model, provided their null-weight entropy is bounded as the common null loading tends to zero. It proves an upper limit, not the exact q limit asserted under the earlier finite-carrier and vanishing-alternative-mass hypotheses. The actual alternatives and their joint Gaussian loadings remain in the selected weighted procedure. No population lower-source transfer, main-theorem proof, native approval, or counterexample to [the unrestricted target](../assets/gaussian_bh_one_sided_universal_order_upper.md) is claimed.

## Standalone statement
Fix q in (0,1) and H<infinity. Consider any sequence of finite weighted testing models indexed by r>0 with r tending to zero. Each model has deterministic nonnegative atom weights summing to one; zero weights are omitted. Its true-null atoms have scores
$$
T_i=\theta_i+rZ+\sqrt{1-r^2}\epsilon_i,\qquad\theta_i\le0,
$$
where Z and all distinct null residuals epsilon_i are independent standard normals. Conditional on Z, the entire alternative p-value vector is independent of the entire null residual vector. The alternative vector may have arbitrary internal dependence, any number of coordinates, arbitrary total mass, and arbitrary conditional law. In particular all original alternatives may depend deterministically on Z, as in the common-loading source family. The number of null atoms, their weights and their means may vary arbitrarily with r. Assume only
$$
H_0(r):=\sum_{i\in I_0}w_i\log(1/w_i)\le H.
$$
Run actual weighted largest-crossing BH at level q, with rejection mass rho and original weighted null numerator, as defined precisely below. Then
$$
\limsup_{r\downarrow0}\operatorname{FDR}_{w,r}(q)\le q. \tag{E}
$$
There is no restriction on the rate at which the number of carriers grows. The entropy bound is fixed while r decreases; q is fixed first, so H may be any finite function H(q) for applications. The alternative total mass need not tend to zero for (E).

Repeated inherited null indices are exact copies. Merge their weights before invoking the statement. This does not change the weighted procedure or FDP, and decreases entropy because a log(1/a)+b log(1/b)>=(a+b)log(1/(a+b)). After merging, the source's distinct inherited nulls have the conditional independence required above. Weights depending on the observed Gaussian scores are excluded. Independent external randomization is allowed by conditioning if the stated deterministic entropy bound holds almost surely.

## Actual largest-rank rule and exact conditional identity
For weighted atoms let C(t)=sum_i w_i 1{p_i<=t}. Put
$$
\rho=\sup(\{0\}\cup\{a\in[0,1]:C(qa)\ge a\}),
\qquad \operatorname{FDP}=\begin{cases}
\rho^{-1}\sum_{i\in I_0}w_i\mathbf1_{\{p_i\le q\rho\}},&\rho>0,\\
0,&\rho=0.
\end{cases}
$$
This is exactly the largest qualifying cumulative mass among ordered weighted atoms; C(q rho)=rho when rho>0. Multiplicities and non-strict comparisons are retained. For null i, force its p-value to zero and let rho_i be the ACTUAL largest weighted rank of that changed vector. Then rho_i>=w_i and, pathwise,
$$
\mathbf1_{\{p_i\le q\rho\}}/\rho
=\mathbf1_{\{p_i\le q\rho_i\}}/\rho_i, \tag{LOO}
$$
with the left side zero if rho=0. To prove it, replacement by zero cannot decrease the largest crossing. If p_i<=q rho_i, restoring it leaves the forced-zero selected set qualifying, hence rho=rho_i. Conversely, if i is originally selected, at any proposed larger crossing its original p-value already lies below the larger threshold, so replacing it by zero does not change that larger count; no new larger crossing can be created. Thus rho=rho_i on original rejection as well. This proves both implications even with ties and long cascades.

Conditional on Z=z, the original null p-value p_i is independent of rho_i, since rho_i depends only on the remaining coordinates. If F_{i,r,z}(t)=P(p_i<=t|Z=z), (LOO) gives the exact label-specific formula
$$
\mathbb E\!\left[\frac{w_i\mathbf1_{\{p_i\le q\rho\}}}{\rho}\,\middle|Z=z\right]
=w_i\mathbb E\!\left[\frac{F_{i,r,z}(q\rho_i)}{\rho_i}\,\middle|Z=z\right]. \tag{CI}
$$
No selected rank is treated as independent without this conditioning and forced-zero identity. In particular q rho_i>=q w_i, which provides the needed truncated calibration range for each label. Alternatives remain inside rho_i; no alternative marginal probability is multiplied by another gate probability.

## Uniform conditional density cap for dust
Write S=barPhi, sigma=sqrt(1-r^2), and first set theta_i=0. Then
$$
F_{r,z}(t)=S((u-rz)/\sigma),\qquad u=S^{-1}(t).
$$
For 0<t<1, its p-density is
$$
f_{r,z}(t)
=\sigma^{-1}\exp\!\left\{\frac{-r^2u^2+2rzu-r^2z^2}{2\sigma^2}\right\}
=\sigma^{-1}\exp\!\left\{\frac{z^2}{2}-\frac{r^2(u-z/r)^2}{2\sigma^2}\right\}
\le\sigma^{-1}e^{z^2/2}.
$$
For 0<r<=1/2, sigma^{-1}<=2, so integrating from zero gives
$$
F_{r,z}(t)\le 2e^{z^2/2}t,\qquad0\le t\le1. \tag{DC}
$$
A negative null mean only lowers its conditional CDF, hence F_{i,r,z}<=F_{r,z} and (DC) holds unchanged for every original true null.

Choose
$$
\varepsilon_r=\exp(-1/\sqrt r),\qquad
D_r=\{i\in I_0:w_i<\varepsilon_r\},\qquad
\delta_r=\sum_{i\in D_r}w_i.
$$
Since log(1/w_i)>1/sqrt(r) on D_r, the entropy assumption gives
$$
\delta_r\le H\sqrt r\longrightarrow0. \tag{DM}
$$
Sum (CI) over D_r and use (DC). The conditional dust FDP contribution is at most 2q delta_r e^{z^2/2}; since every component of FDP is at most one, it is at most
$$
\min\{1,2q\delta_re^{z^2/2}\}. \tag{DP}
$$
This bound holds independently of the number of dust atoms. The fact that E exp(Z^2/2) is infinite does not justify discarding the truncation in (DP).

For lambda=2q delta_r in (0,1), put b=sqrt(2log(1/lambda)). Direct Gaussian integration gives
$$
\mathbb E\min\{1,\lambda e^{Z^2/2}\}
=\frac{2\lambda b}{\sqrt{2\pi}}+2S(b)
\le\frac{2\lambda}{\sqrt{2\pi}}(b+1/b) \longrightarrow0. \tag{DI}
$$
The last inequality uses S(b)<=phi(b)/b and phi(b)=lambda/sqrt(2pi); it is invoked only for sufficiently small positive lambda, so b>0. If delta_r=0 the dust contribution is zero. Thus the total expected dust contribution vanishes uniformly in all model parameters subject to the entropy bound.

## Uniform truncated calibration for large weights
Fix a finite B>0 and put U_q=S^{-1}(q). For labels with w_i>=epsilon_r, the threshold in (CI) lies in [q epsilon_r,q]. On this range
$$
U_q\le u\le M_r:=S^{-1}(q\varepsilon_r)
=O_q(r^{-1/4}). \tag{QR}
$$
For completeness, for small r the upper quantile is positive; the elementary Gaussian bound S(x)<=exp(-x^2/2) for x>=0 gives M_r<=sqrt(2log(1/(q epsilon_r))). Since q is fixed, this proves (QR). The fixed lower endpoint U_q may be negative.

Set y=(u-rz)/sigma. For |z|<=B, 0<r<=1/2 and u in the above interval,
$$
|y-u|\le C\{rB+r^2|u|\}
\le C\{rB+r^2(M_r+|U_q|)\}=:d_r,
$$
where C is numerical. The Gaussian hazard h(s)=phi(s)/S(s) satisfies h(s)<=C'(1+s_+) for every real s, with a numerical C'. Here is an elementary proof avoiding an unproved Mills uniformity assertion: for s>=0 integrate phi over [s,s+1/(s+1)] to get S(s)>=phi(s)e^{-3/2}/(s+1), while for s<0 use S(s)>=1/2 and phi(s)<=1/sqrt(2pi). Therefore
$$
\left|\log\frac{F_{r,z}(t)}t\right|
=\left|\int_u^y h(v)\,dv\right|
\le C'(1+M_r+d_r)d_r
\longrightarrow0, \tag{TC}
$$
uniformly for |z|<=B and q epsilon_r<=t<=q. Indeed the potentially largest terms are O_{B,q}(rM_r+r^2M_r^2)=O_{B,q}(r^{3/4}+r^{3/2}), both tending to zero. Let kappa_{r,B,q} be the exponential of the right side of (TC). Then kappa->1 and
$$
F_{i,r,z}(t)/t\le\kappa_{r,B,q}
$$
on the same range for ALL null means theta_i<=0 by the CDF domination already noted. No number-of-carriers, dimension, or least-variance factor appears.

## Summation and upper limit
Let L_r be the true-null labels with w_i>=epsilon_r. For |z|<=B, apply (CI) and truncated calibration at each label's actual forced-zero rank:
$$
\mathbb E[\operatorname{FDP}_{L_r}\mid Z=z]
\le q\kappa_{r,B,q}\sum_{i\in L_r}w_i
\le q\kappa_{r,B,q}. \tag{LC}
$$
Outside this event the full large-label contribution is at most one. Together with the already proved dust budget,
$$
\operatorname{FDR}_{w,r}(q)
\le \mathbb E\min\{1,2q\delta_re^{Z^2/2}\}
+q\kappa_{r,B,q}P(|Z|\le B)+P(|Z|>B).
$$
For fixed q,H,B let r tend to zero, using (DM), (DI), and (TC), to obtain
$$
\limsup_{r\downarrow0}\operatorname{FDR}_{w,r}(q)
\le qP(|Z|\le B)+P(|Z|>B).
$$
Finally let B tend to infinity. This proves (E). All estimates are uniform over the number of carriers, deterministic weights with H_0<=H, nonpositive null means, and the allowed conditional alternative laws. At r=0 conditional null independence and marginal superuniformity give the usual weighted leave-one-out bound directly. The singular alternative endpoint in which all alternatives depend only on Z is explicitly permitted; no nonsingular perturbation or covariance substitution is needed.

## Consequence for the remaining inherited-carrier construction class
The proof above is standalone and requires no source lower theorem. For the Lei one-sided source family, its null loading is r, distinct null residuals are independent conditional on Z, and every original alternative score is its positive mean minus Z. Thus any construction retaining all those alternatives exactly and representing the null mass by ANY finite number of inherited distinct null carriers with null-weight entropy bounded by a fixed H(q)<infinity meets the proved upper-limit hypotheses, even when the number of carriers is unbounded as r decreases. The exact secondary alternative shaping law W_r and its correlated -Z gate are retained; no atom or product approximation is used.

Conditional on the compact-bracket/finite-transfer source claim identified explicitly in [the earlier observation](idea_efbcf7095e77.md), original finite source layouts can have FDR approaching ell_<= (q), while these bounded-entropy inherited compressions have upper limit at most q (or cq when run at a fixed inflated level cq<1). Therefore the same fixed-constant comparison bridge would fail whenever ell_<= (q)/q exceeds its constants. This corollary remains explicitly CONDITIONAL on that source lower-family transfer, not independently reconstructed here. The standalone conclusion (E) is fully proved above.

This closes the previously untested unbounded-but-bounded-entropy INHERITED-carrier class for the stated conditional-independent Gaussian source. It does not obstruct synthetic changed-loading carriers, score-dependent weights, a null entropy growing unboundedly as r decreases, or a construction outside the stated conditional-independence structure. It supplies no executable main proof plan. The unrestricted target remains unrefuted; no existing research record, target statement, proof, dependency, approval, failed plan, or loop state is edited.
