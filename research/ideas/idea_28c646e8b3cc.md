---
type: idea
title: >-
  Quantitative obstruction to the fixed-loading compression certificate at
  subexponential effective dimension
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - quantitative-compression
---

## Scope
This is a proved diagnostic of the explicit approximation CERTIFICATE in the approved compression proof, not a refutation of the compression theorem or the universal one-sided target. The target, canonical labels, negative null means, largest BH rank and two completion roots are unchanged. Relevant approved nodes are [fixed-loading compression](../assets/gaussian_bh_common_loading_uniform_submodel_compression.md), [fixed-loading continuity](../assets/gaussian_bh_common_loading_wasserstein_fdr_continuity.md), and [central window](../assets/gaussian_bh_one_sided_free_central_window_core.md). No result outside the target dependencies is used as a target-proof black box.

## Quantitative empirical certificate obstruction
Write U=S^{-1}(q), and distinguish e_m^{cert}, the particular deterministic error defined in compression Proof Step 7, from any sharper error whose existence the theorem permits. That proof uses p_m(gamma)=min{1,8/(gamma sqrt(m))} and E_m=2B(2a)+(1+3/a)Q_m+2gamma/a+p_m, with Q_m=c+gamma+positive terms+p_m. Consequently E_m>=gamma+p_m. If p_m=1 this is at least 1; otherwise AM-GM gives gamma+8/(gamma sqrt(m))>=4sqrt(2)m^{-1/4}. Taking the stated infimum and minimum with 2 proves
$$
e_m^{cert}(q,\sigma)\ge\min\{1,4\sqrt2\,m^{-1/4}\}.
$$
Thus for any fixed C,A<infinity, m<=exp(CU) cannot make this certificate <=AqU for all sufficiently small q. Indeed q<=phi(U)/U implies qU<=phi(U), whereas exp(-CU/4)/phi(U) tends to infinity. BY on m tests costs q H_m=O(qU) at log(m)=O(U), so this explicit uniform absolute-tail certificate cannot close that bridge. This does not lower-bound the actual expected sampled-FDP difference.

## Microscopic certificate obstruction
Let 0<sigma<=1/4, tau=sqrt(1-sigma^2), 0<a<1, b=qa, and assume v_b=S^{-1}(b)<=2U. The continuity microscopic certificate is B(q,sigma,a)=E_Z min{1,q I_Z(b)}, with
$$
I_z(b)=\int_{v_b}^{\infty}\frac{\phi((v-\sigma z)/\tau)}{\tau S(v)}\,dv
=e^{z^2/2}\int_{v_b}^{\infty}\frac{h(v)}{\tau}
 e^{-(\sigma v-z)^2/(2\tau^2)}\,dv,\qquad h(v)=\phi(v)/S(v).
$$
The identity is direct completion of the square. For v>0, integration of x phi(x) on [v,infinity) proves h(v)>=v. For z in [U/2,3U/4], v in [z/sigma,(z+tau)/sigma] lies above 2U>=v_b. Substitution x=(sigma v-z)/tau on this subinterval yields I_z(b)>=exp(-1/2) z sigma^{-2} exp(z^2/2)>=exp(-1/2) z exp(z^2/2). Also q exp(-1/2) z exp(z^2/2)<1 throughout that z interval, since q<=phi(U)/U. Monotonicity of min(1,x), followed by integration against phi(z), proves
$$
B(q,\sigma,a)\ge
\frac{5e^{-1/2}}{32\sqrt{2\pi}}qU^2.
$$
For a=exp(-CU), the hypothesis v_b<=2U holds at all sufficiently large U: equivalently S(2U)/S(U)<=exp(-CU), which follows from Mills bounds. This lower bound is on the scalar dominating certificate, not on actual microscopic FDR. The central-window theorem controls Y_i<=U; it supplies no bound for the discarded small normalized ranks or its complementary shell.

## Gaussian regularization transfer and remaining gate
For each fixed finite original model, set T_i(alpha)=theta_i+cos(alpha) X_i+sin(alpha) Z, with common Z independent of the original centered Gaussian vector X, and alpha=arcsin(sigma). Labels are unchanged. For each i and each fixed BH threshold u_k, the scalar smooth path cos(t)X_i+sin(t)Z has standard-normal value and an independent standard-normal derivative at every t. Its expected number of crossings of u_k-theta_i on [0,alpha] is alpha exp(-(u_k-theta_i)^2/2)/pi<=alpha/pi (the elementary one-dimensional Rice formula, or its directly proved coarea version). A union bound over N^2 comparisons therefore gives
$$
E|D_\sigma-D_0|\le \min\{1,N^2\arcsin(\sigma)/\pi\}.
$$
Alternatively fixed-N convergence alone follows by almost sure convergence of all N^2 comparisons, each with a continuous marginal at its threshold, then bounded convergence; this version needs no Rice formula. Neither version is uniform in N. The approved Wasserstein theorem fixes sigma and does not assert sigma-down-to-zero continuity uniformly over models. Any Rice-based quantitative bound above requires an independent check of the crossing identity before being reused as an established auxiliary lemma.

The unresolved useful gate is a direct expected signed-FDP compression error O(qU) at log(m)=O(U), together with common-noise removal uniform enough to avoid N-dependent sigma. No such gate has been proved here, and writing it as a plan step would be filler. A distinct next test is rank-stratified relative-error sampling with an anchored rejected coordinate: retain the exact identity E[(1+Bin(R-1,p))^{-1}]=[1-(1-p)^R]/(pR), and test whether a Gaussian-weighted small-rank payment can control the complementary (1-p)^R term WITHOUT replacing sampled BH by the intersection of the original rejection set. This is an unproved proposal, not a lemma or an authorized extra required root.
