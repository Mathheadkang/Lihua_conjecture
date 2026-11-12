---
type: idea
title: >-
  Rare Gaussian alternatives obstruct every uniform finite index-subsampling FDR
  bridge
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - quantitative-compression
  - rare-alternative-obstruction
---

## Claim and scope
Uniform sampling of a model-independent finite number of original coordinates cannot provide the proposed order-aware bridge, even with a fixed multiplicative increase of the BH level and an additive O(q) remainder.

Precisely, fix any constants C_0,C_1,c>0, any q_0>0, and any function M assigning a finite positive integer M(q) to every q. There exist 0<q<=q_0 with cq<1 and a finite canonical Gaussian model (N,theta,Sigma) for which
$$
\operatorname{FDR}_N(q)>C_0\,\mathbb E_I[
 \operatorname{FDR}_{M(q)}(cq;\theta_I,\Sigma_I)]+C_1q.
$$
Here I_1,...,I_M are iid uniform original indices, independent of all Gaussian variables; repeated indices are exact copies; original means and true-null labels are retained. Sigma_I is the inherited covariance including those copies. This applies in particular to M(q)=ceil(exp(K sqrt(log(1/q)))) for any fixed K, and indeed to any larger finite function of q. It does NOT refute the main universal order theorem, the approved fixed-positive-common-loading compression theorem, importance sampling, or a bridge with a model-dependent sample size. This diagnostic requires fresh independent verification before promotion to an established asset.

## Exact anchored finite identity
Fix any deterministic p-vector and its ACTUAL largest-rank BH rejection set A, with R=|A|, V=|A intersect I_0|, and alpha=R/N. Sample M iid indices. Let K be the number whose original coordinates lie in A and L the number whose original coordinates lie in A intersect I_0. For R>0, anchoring one sampled occurrence and conditioning it to be a sampled original rejection leaves Bin(M-1,alpha) further original rejections. Thus
$$
\mathbb E\frac1{1+\operatorname{Bin}(M-1,\alpha)}
=\frac{1-(1-\alpha)^M}{M\alpha},
\qquad
\mathbb E_I\frac L{K\vee1}
=\frac VR[1-(1-\alpha)^M].
$$
The first equality follows by integrating E[t^{Bin(M-1,alpha)}] over t in [0,1]. Both sides of the second equality are zero at R=0. This statistic is the sampled intersection with the ORIGINAL rejection set; it is not the FDP of actual sampled BH. An anchor set to p=0 changes the procedure and does not justify identifying them.

## Verified source family and covariance
Use the approved [Lei finite one-sided lower bound](../assets/lei2026_one_sided_fdr_lower.md) and its imported paper lei2026_gaussian_bh, pages 43--46 and 57--58. At fixed q, draw parameters Omega=((Theta_i,B_i)) iid from the source law nu^+_{q,r}, independently of independent standard normals Z,epsilon_1,...,epsilon_N, and set
$$
T_i=\Theta_i+B_iZ+\sqrt{1-B_i^2}\epsilon_i.
$$
The null atom has mass pi_{0,r}=1-r-tau_r, mean zero and loading B=r. Primary alternatives have mass r, mean c_r+b_r>0 and loading -1. Secondary alternatives have total mass tau_r, means a/r+a>0 and loading -1. Source equations (147)--(149) give
$$
\tau_r\sim (1-q)r^2/q,\qquad r\downarrow0
$$
at this fixed q. In particular a_r:=r+tau_r tends to zero. Distinct null coordinates have covariance r^2, null-to-alternative covariance -r, and alternative-to-alternative covariance 1. Every diagonal variance is one. This is an admissible PSD model. The common loading r really tends to ZERO: it is not a private-noise parameter. The approved central/directional coefficient is gamma=sqrt((1-r)/(1+r)), which tends to one, so the directional entropy bound permits the source's order q sqrt(log(1/q)); no contrary coefficient formula is being used.

The source construction/proof gives the following quantifiers: for each fixed q and epsilon>0, all sufficiently small r admit arbitrarily large N for which
$$
\mathbb E_\Omega\operatorname{FDR}_N(q;\Omega)
\ge\ell_{\leq}(q)-\epsilon.
$$
This is exactly the population compact-bracket and finite-model averaging argument on pages 57--58, not a claim that r is fixed independently of the desired error. The approved lower theorem gives
$$
\ell_{\leq}(q)/q\longrightarrow\infty\quad(q\downarrow0).
$$

## Exact secondary-law scale check
For clarity, the source parameters used above are
$$
y_q=\sqrt{2\log(1/q)},\quad b_r=rS^{-1}(r^2),\quad
W_r(a)=\{1-qe^{a^2/2}\}S(a/r)/q,\quad
\tau_r=W_r(b_r),\quad
\mu_r([a,y_q])=W_r(a)/\tau_r,
$$
for b_r<=a<=y_q, and c_r is determined by S(c_r)=q(r+tau_r)/(1-q pi_{0,r}). Thus the total secondary mass above any FIXED parameter a>0 is W_r(a), not tau_r; W_r(a) is exponentially small in 1/r^2. Most secondary mass concentrates near the shrinking b_r. At a score cutoff C the exact rejected secondary mass is W_r(r(C+z)/(1+r)) when its argument is in [b_r,y_q], with the evident endpoint values outside that interval. This is source equation (156). Consequently a typical positive common Z does not imply R/N>=tau_r. For fixed z>0, b_r->0, c_r->infinity and the primary contribution at its own upper score c_r+b_r-z is q r/S(c_r+b_r-z)->0, using the source asymptotics c_r~sqrt(2log(1/r)) and b_r c_r->0. The lower-family argument above relies on the source's proved population and finite transfer, not a heuristic that all secondary alternatives have the same large mean.

## Actual sampled-BH limit
Fix q and its finite M=M(q), and put q'=cq<1. When sampling original indices,
$$
P\{\hbox{some sampled coordinate is alternative}\}\le M a_r,\qquad
P\{\hbox{some sampled indices repeat}\}\le M(M-1)/(2N).
$$
The probabilities here include the source's independent random parameter draw. Conditional on all sampled indices being distinct nulls, their Gaussian scores have mean zero, diagonal variance one, and every off-diagonal covariance r^2. This assertion conditions only on parameters/indices, never on observed Gaussian scores.

Let f_{M,q'}(r) be the FDR of ordinary q'-BH on exactly M such equicorrelated nulls. Since FDP is in [0,1],
$$
\mathbb E_\Omega\mathbb E_I\operatorname{FDR}_{M}(q';\Omega_I)
\le f_{M,q'}(r)+M a_r+M(M-1)/(2N).
$$
Couple the null scores as rZ+sqrt(1-r^2)epsilon_j. For fixed finite M they converge almost surely to independent standard normals as r decreases to zero. There are only M^2 BH threshold comparisons, and every limiting comparison has probability zero of equality. Hence the actual largest-rank BH FDP converges almost surely, and bounded convergence gives f_{M,q'}(r)->q'. The last equality is exact independent-all-null BH FDR: with R_j the forced-zero rank, independence gives E[1{P_j<=q'R_j/M}/R_j]=q'/M, and summing over all j gives q'. This uses the full sampled BH selection, not an intersection, approximation or deterministic cutoff.

## Contradiction to the proposed bridge
Choose q sufficiently small that cq<1 and ell_{\leq}(q)>(C_0 c+C_1)q with a strict positive gap. Fix this q and its finite M. Next choose r sufficiently small, then N sufficiently large, so the preceding lower bound and sampled upper bound make
$$
\mathbb E_\Omega\left[
\operatorname{FDR}_N(q;\Omega)
-C_0\mathbb E_I\operatorname{FDR}_{M}(cq;\Omega_I)
\right]>C_1q.
$$
The order is q first, M(q) fixed second, r small third, and N large last. Such choices are legal under the main target's unrestricted finite-model supremum. Some deterministic realization Omega must satisfy the same strict inequality, proving the claim. Rare alternatives have vanishing sampling probability while still shaping the full population's largest BH crossing; their contribution cannot be charged universally as O(q) in this comparison.

A positive-definite original counterexample is also available if desired: for the selected fixed finite original model, replace Sigma by (1-eta^2)Sigma+eta^2 I. Couple scores with independent original-coordinate noises. All N^2 original comparisons, and all finitely many sampled-list comparisons, stabilize almost surely as eta decreases to zero because every marginal threshold is continuous. Bounded convergence preserves both finite FDR expectations, hence preserves the strict gap for sufficiently small positive eta. Means and labels do not change; sampled repeated indices remain exact copies.

## Remaining direction
No full-target plan follows from this obstruction. A genuinely distinct compression attempt would need to retain the rare alternative shaping measure or use model-dependent importance weights; uniform sampling cannot do so at any model-independent finite budget. A concrete next test is stratification by deterministic means and factor loadings with the original mass weights preserved, followed by an exact WEIGHTED step-up comparison; its weighted rejection rule, largest crossing and conversion back to ordinary equal-weight BH all require proof. No new required root, approval, target statement or protected loop state is changed.
