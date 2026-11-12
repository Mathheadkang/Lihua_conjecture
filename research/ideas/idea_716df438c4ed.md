---
type: idea
title: >-
  Global primary-cap bound and coupling tradeoff for common-gated Gaussian
  blocks
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
  - lei2026_two_sided_fdr_lower
tags:
  - common-gate
  - two-sided
  - finite-N
  - partial-obstruction
  - unresolved-crossing
---

This draft observation establishes a finite-N cap bound and exact Gaussian tradeoff identities for the common-gated test family. It does not exclude every intermediate coupling and supplies no counterexample.

## Exact common-gate model and global crossing

Take B equal blocks of size m, N=Bm. Let W,Z_1,...,Z_B and all E_{ji} be independent standard normals. Put Y_j=epsilon Z_j+sW, s=sqrt(1-epsilon^2). A null coordinate in block j is r Z_j+sqrt(1-r^2)E_{ji}. Every nonnull coordinate is a deterministic source mean mu_l plus Y_j (reverse both signs where the chosen source loading requires it). The source two-sided construction has positive nonnull loading, so its replacement is +Y_j. All observations are exactly jointly Gaussian with Sigma=AA^T+diag(1-||A_i||^2), and all diagonal entries equal one.

For p(c)=2 PhiBar(c), let H_alt(c;y) be the nonnull contribution to a single block's empirical exceedance proportion, including its deterministic type weights. With null fraction pi_0, the conditional mean of the global empirical exceedance proportion is
$$
G_{Z,W}(c)=\frac1B\sum_{j=1}^B\{\pi_0 h_{r,Z_j}(c)+H_{\rm alt}(c;Y_j)\},
$$
where h_{r,z}(c)=PhiBar((c-rz)/sqrt(1-r^2))+PhiBar((c+rz)/sqrt(1-r^2)).
The finite BH cutoff uses the actual empirical proportion F_N(c), through inf{c>=p^{-1}(q):q F_N(c)/p(c)>=1}. A population approximation would use q G(c)/p(c), which is a SUM of local-alpha normalized crossings when alpha=q/B. Neither object is a sum of local FDRs, and replacing F_N by G requires a separate uniform crossing argument.

## A finite-N global cap lemma

Suppose each block has a identical primary nonnulls with positive mean mu_p and value mu_p+Y_j. Let
$$
t_*=qa/N,\quad c_*=p^{-1}(t_*),\quad d=\mu_p-c_*,
\quad {\cal A}=\{\max_jY_j\geq-d\}.
$$
On A, a block's a primary p-values are at most t_*, so their rank qualifies for GLOBAL BH and R>=a. The same is true after replacing any null p-value by zero. Extra secondary nonnull coordinates and arbitrary deterministic secondary means cannot invalidate this cap.

Put sigma=sqrt(1-r^2)>0 and kappa=r(c_*+1)/sigma. For c in [0,c_*], the unfavorable conditional null tail is at most PhiBar(c). The favorable tail's argument is at least c-r|z|/sigma. Since the normal hazard is increasing and lambda(c)=phi(c)/PhiBar(c)<=c+1 for c>=0, integrating the hazard gives
$$
\frac{h_{r,z}(c)}{p(c)}
\leq\frac{1+\exp\{\kappa|z|\}}2.
$$
Conditional on W,Z, all p-values are independent, including deterministic alternatives. If R^{(i)} denotes the BH count after setting null p_i=0, the exact leave-one-out identity gives its expected FDP contribution as E[F_i(qR^{(i)}/N)/R^{(i)} | W,Z]. On A, the threshold belongs to [t_*,q], so the preceding tail bound applies. Summing over nulls and integrating the factors, using E exp(kappa|Z|)=2 exp(kappa^2/2)Phi(kappa), proves the finite-N inequality
$$
\operatorname{FDR}\leq q\pi_0\left\{\frac12+e^{\kappa^2/2}\Phi(\kappa)\right\}
+\mathbb P({\cal A}^c).
$$
This derivation retains the global BH rank, all primary ties, and every secondary coordinate. If r(c_*+1)->0, its first term is q pi_0{1+o(1)}. It does not require null-factor maxima to be uniformly bounded, because the factor integration is performed after summing the conditional bound.

## Exact gating probabilities

At any fixed cutoff c, a primary block is inactive exactly when -c-mu_p<Y_j<c-mu_p (boundary equality has probability zero). Conditional on W=w, all B blocks are inactive with probability
$$
\left[
\Phi\left(\frac{c-\mu_p-sw}{\epsilon}\right)
-\Phi\left(\frac{-c-\mu_p-sw}{\epsilon}\right)
\right]^B
$$
for epsilon>0. For the sufficient positive cap above, write M_B=max_jZ_j. Its complementary event has the simpler exact probability
$$
\mathbb P({\cal A}^c)
=\mathbb E\Phi\left(\frac{-d-\epsilon M_B}{s}\right)
$$
when 0<epsilon<1. If epsilon is fixed, d stays bounded, and B->infinity, then
$$
\frac{\log\mathbb P({\cal A}^c)}{\log B}
\longrightarrow-\frac{\epsilon^2}{1-\epsilon^2}.
$$
Proof: M_B/sqrt(2 log B)->1; any fixed relative downward deviation has superpolynomially small probability. Restricting M_B to a fixed relative band and applying the scalar Gaussian tail exponent brackets the logarithmic rate; then shrink the band. Thus for B=ceil(q^{-c_0}) with fixed c_0>0, r c_*->0 and c_0 epsilon^2/(1-epsilon^2)>1, the finite-N cap lemma gives FDR<=q{1+o(1)}+o(q), uniformly in the secondary arrays.

In contrast, if epsilon->0, epsilon sqrt(2 log B)->lambda in [0,infinity), and d->d_0, bounded convergence gives
$$
\mathbb P({\cal A}^c)\longrightarrow\Phi(-d_0-\lambda).
$$
Hence epsilon of order 1/sqrt(log B) can remove the exponentially-in-B independent-gate penalty. This fact alone says nothing about FDR on that event.

## Verified local-alpha source calibration

The exact supplied TeX bh_fdr_research/reference_arxiv/FDR_BH_v4.tex lines 902-1007 and native paper pages 11-12 give, for TWO-sided local level alpha,
$$
b_r=rp^{-1}(r^2),\quad
\tau=\{1-\alpha M(y(b_r))\}r^2/\alpha,\quad
\pi_0=1-r-\tau,
$$
$$
p(c_{\alpha,r})=\alpha(r+\tau)/(1-\alpha\pi_0),
\quad\mu_p=c_{\alpha,r}+y(b_r),
$$
with positive source loading +1. One-sided primary signs and means must not be substituted. If r~alpha^2, then tau/r<=r/alpha=O(alpha), b_r->0 and y(b_r)->1. For an empirical primary fraction exactly r, t_*=(q/B)r=alpha r and
p(c_{\alpha,r})/p(c_*)=(1+tau/r)/(1-alpha pi_0)=1+O(alpha).
Consequently c_{\alpha,r}-c_*->0, mu_p-c_*->1 and r c_*->0 along alpha=q/B->0. The new round-2 failed candidate common_gate_primary_cap instantiates B=ceil(q^{-2}), epsilon=1/sqrt(2), and deterministic source-quantile secondary arrays; its proof is uniform in those secondary arrays. No fixed-alpha O(r^2) remainder is being used uniformly without its 1/alpha factor.

## Exact coupling diagnostic and its limitation

For a standard jointly Gaussian pair (Z,Y) with correlation epsilon, define L_a(Z)=exp(-a^2/2)cosh(aZ). For any deterministic a>=0,
$$
\mathbb E[L_a(Z)\mid Y=y]
=\exp(-\epsilon^2a^2/2)\cosh(\epsilon a y).
$$
For the linear threshold proxy a=|Y| this gives the exact unconditional identity
$$
\mathbb E L_{|Y|}(Z)
=\frac12\left\{\frac1{1-\epsilon}+\frac1{1+\epsilon}\right\}
=\frac1{1-\epsilon^2},\qquad0<=\epsilon<1.
$$
More generally any measurable 0<=a(y)<=|y| satisfies
E L_{a(Y)}(Z)<=1/2+1/{2(1-epsilon)}: bound its positive-exponential term by exp{(epsilon-epsilon^2/2)Y^2} and its negative term by one. The source optimizer a(|y|), extended as zero for |y|<=1, lies in this interval. Thus the single-own-gate scalar-map mechanism loses its square-root-log gain at epsilon->0. These are kernel identities/bounds, not FDR bounds and not a justification for adding local contributions at the global threshold.

In particular the entire gate vector Y carries much more information than a single Y_j. For epsilon>0 its Gaussian posterior is
$$
\operatorname{Cov}(Z\mid Y)
=\frac{s^2}{\epsilon^2+B s^2}{\bf1}{\bf1}^{\mathsf T},
$$
$$
\mathbb E(Z\mid Y)=\epsilon^{-1}
\left[Y-\frac{s^2}{\epsilon^2+B s^2}\left(\sum_jY_j\right){\bf1}\right].
$$
All differences Z_j-Z_k are determined exactly by (Y_j-Y_k)/epsilon. With large B, each posterior coordinate variance is of order 1/B. Therefore conditioning only on the block's own Y_j and applying the scalar attenuation identity at a global threshold is invalid.

The remaining precise gap is to control the globally selected cutoff as a function of all Y_j, all Z_j and empirical null residuals, especially on the nonrare all-primary-off event when epsilon sqrt(log B)=O(1). Retaining the original source means does not automatically retain its scalar first-crossing map after the null/signal loading replacement. This observation does not exclude that regime and does not establish a counterexample.
