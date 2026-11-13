---
type: plan
title: >-
  Universal one-sided order via ultrametric null directions of penalized
  maximizers and a null-tree bound
status: abandoned
target_asset: gaussian_bh_one_sided_universal_order_upper
route_lemmas:
  - gaussian_bh_null_overlap_ghirlanda_guerra_maximizer
  - gaussian_bh_null_ultrametric_maximizer_selection
  - gaussian_bh_null_ultrametric_order_bound
route_title: via ultrametric null trees at maximizers
origin: researcher
inspired_by:
  - idea_b808cca5bf7f
  - idea_ae102c56085d
  - idea_38a72ab5ee7e
tags:
  - parallel-round-20261112
  - ultrametric
route_round: 1
reduction_digest: 30bb327f610d33b0f3cc3f2beea8298e36e509d089e11b46095f82fea9bb573d
reduction_inputs:
  gaussian_bh_one_sided_universal_order_upper: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
  gaussian_bh_fractional_frame_surface_kernel: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
  gaussian_bh_conditional_compound_calibration: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
  gaussian_bh_negative_null_boundary_strip: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
  gaussian_bh_conditional_subpoisson_calibration: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
  gaussian_bh_null_overlap_ghirlanda_guerra_maximizer: c004cd7dd3ebba2bde77adaf595610273c90f3f1141552d69887bd909631a7ab
  gaussian_bh_null_ultrametric_maximizer_selection: 6e1f56f90f077e3d2a82f2d1edf41557d4fb8ddd7d799691aec714a283063eea
  gaussian_bh_null_ultrametric_order_bound: 3ae61a91d41df487fd7a27c6c72109d3e529bf06b13a3edc2a1e611fc5034a6c
reduction_verified_digest: 30bb327f610d33b0f3cc3f2beea8298e36e509d089e11b46095f82fea9bb573d
reduction_checked: true
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement: universal $C_1,q_{0,1}$ with $F_1(q)\le C_1q\sqrt{\log(1/q)}$ for $0<q\le q_{0,1}$, over every finite $N$, every mean vector, every unit-diagonal PSD covariance (singular included), the original labels $I_0=\{i:\theta_i\le0\}$ and ordinary BH with its largest qualifying rank and non-strict comparisons. This works out the researcher's selected route ([selection](../ideas/idea_b808cca5bf7f.md), content in [Route 3](../ideas/idea_ae102c56085d.md)): worst-case marked arrays are taken ultrametric through Ghirlanda-Guerra identities and Panchenko's ultrametricity theorem, and BH is then bounded on trees.

This slot's version imposes ultrametric structure only on the **null-tagged** directions. Alternatives keep arbitrary directions, signs of correlation and means, both in the Ghirlanda-Guerra lemma and in the tree bound. The reason is that the identities force nonnegative overlaps (Talagrand positivity). A worst case that needs alternatives negatively correlated with nulls would refute a full-array version but not this one. A second difference is that the route works at an exact penalized maximizer (item 2 of the approved [marked-array compactification](../assets/gaussian_bh_exchangeable_array_variational_compactification.md)) and selects one deterministic directing population. A parallel route of this round (slot 3) instead imposes the identities and the tree hypothesis on the whole correlation array along near-maximizing sequences.

External Gaussian inputs, as the direction requires: Panchenko, *The Parisi ultrametricity conjecture*, Ann. of Math. 177 (2013) 383-393, with Talagrand's positivity principle (to be imported and verified before Lemma 2 is proved; locations to be read from the source); the approved [Dovbysh-Sudakov representation](../library/panchenko2009_dovbysh_sudakov/assets/lib_panchenko2009_dovbysh_sudakov_mixture.md); for Lemma 3, chaining over tree levels with the approved [directional-entropy bound](../assets/directional_entropy_one_sided_fdr_bound.md) as the per-level charge.

Stated remainders (before execution). The reduction below leaves no remainder: every step is an inequality between values, closed by approved compactification limits. Lemma 1 leaves a statement about the null-overlap law of one maximizer. That statement is a property of the correlation array alone, not the FDR. Lemma 2 leaves nothing beyond Panchenko's theorem and component selection. Lemma 3 is the target restricted to a proper class, models whose null correlations form a tree, and it must be paid by an explicit tree-chaining charge. In the independent-null star tree ($\Sigma_{ij}=0$ for distinct nulls) that charge must be $O(q)$, so it cannot be the FDR itself.

## Route

- gaussian_bh_null_overlap_ghirlanda_guerra_maximizer: gives, at fixed $\sigma,q,\eta$, a canonical maximizer $P_*$ of $\mathcal F-\eta M_2$ whose null-tag overlap array satisfies the Ghirlanda-Guerra identities (Step 2).
- gaussian_bh_null_ultrametric_maximizer_selection: turns $P_*$ into a deterministic canonical maximizing population $\mu$ whose iid samples have nonnegative ultrametric null-null correlations almost surely (Step 2).
- gaussian_bh_null_ultrametric_order_bound: bounds the FDR of every finite model with nonnegative ultrametric null-null correlations, alternatives arbitrary, by $A_Tq[1+\sqrt{\log(1/q)}]$ (Step 3).

## Plan

1. [x] Fix $0<q\le q_0:=\min\{q_T,\overline\Phi(1)\}$, where $q_T<1/2$ is the interval of Lemma 3; fix $0<\sigma<1$ and $\eta>0$. All items of the compactification apply at this $q$.
2. [x] By Lemma 1 there is a canonical maximizer $P_*\in\mathfrak P_2$ of $\mathcal F(\cdot;q,\sigma)-\eta M_2$ with $P_*(E_0)>0$ whose null-tag overlap array satisfies the Ghirlanda-Guerra identities. By Lemma 2 there is a deterministic canonical $\mu$ such that $P_\mu$ is again a maximizer, so
$$
A_{\eta,\sigma}(q)=\mathcal F(P_\mu;q,\sigma)-\eta M_2(P_\mu)\le\mathcal F(P_\mu;q,\sigma),
$$
and $P_\mu$-almost surely $C_{ij}\ge0$ and $C_{ik}\ge\min\{C_{ij},C_{jk}\}$ for all pairwise distinct null-tagged $i,j,k$.
3. [x] For each $n$ and $P_\mu$-almost every $\omega$, the finite model of the [marked-array definition](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md) is an admissible one-sided model. It has $n$ tests, means $\theta_{1:n}$ and covariance $\Sigma^{(n)}=(1-\sigma^2)C_{1:n,1:n}+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}$, which has unit diagonal and is PSD. Canonical tags give $\ell_i=\mathbf 1_{\{\theta_i\le0\}}$, so $D_n$ is the original one-sided FDP with $I_0=\{i\le n:\theta_i\le0\}$. For distinct null indices, $\Sigma^{(n)}_{ij}=(1-\sigma^2)C_{ij}+\sigma^2$ is an increasing affine image of $C_{ij}$, so it stays nonnegative and ultrametric. Lemma 3 gives $\mathbb E[D_n\mid\omega]\le A_Tq[1+\sqrt{\log(1/q)}]$ almost surely.
4. [x] Integrating over $\omega\sim P_\mu$ gives $\mathcal F_n(P_\mu;q,\sigma)\le A_Tq[1+\sqrt{\log(1/q)}]$ for every $n$. Item 1 of the compactification ($\mathcal F=\lim_n\mathcal F_n$) gives the same bound for $\mathcal F(P_\mu;q,\sigma)$, hence for $A_{\eta,\sigma}(q)$ by Step 2.
5. [x] Item 2 of the compactification ($A_{\eta,\sigma}(q)\to W_\sigma(q)$ as $\eta\downarrow0$) gives $W_\sigma(q)\le A_Tq[1+\sqrt{\log(1/q)}]$ for every $\sigma\in(0,1)$. Item 5 ($W_\sigma(q)\to F_1(q)$ as $\sigma\downarrow0$, valid for $q<1/2$) gives $F_1(q)\le A_Tq[1+\sqrt{\log(1/q)}]$ for $0<q\le q_0$.
6. [x] Apply the target's acceptance criterion with $A_1=A_T$ and $\widetilde q_{0,1}=q_0$: take $q_{0,1}=\min\{q_0,e^{-1}\}$ and $C_1=2A_T$.

## Verification

Steps 2-5 bound the original envelope $F_1(q)$ at each fixed $q\le q_0$ through the approved limits $F_1=\lim_{\sigma\downarrow0}W_\sigma$ and $W_\sigma=\lim_{\eta\downarrow0}A_{\eta,\sigma}$. The supremum over all $N,\theta,\Sigma$, including singular matrices and q-dependent models, is therefore controlled without any restriction. No constant depends on $\sigma$ or $\eta$: the only constants are $A_T,q_T$ of Lemma 3. The finite models fed to Lemma 3 are genuine admissible one-sided models: canonical tags coincide with the original labels and no coordinate is deleted or recentered. Their null-null correlations meet Lemma 3's hypothesis by Lemma 2 and the affine common loading. Step 6 is exactly the sufficient finite-level conclusion in the target's acceptance criterion, so the displayed statement follows with universal $C_1,q_{0,1}$. If Lemma 1 fails, the route is obstructed. A falsifier is any $(\sigma,q,\eta)$ at which no canonical maximizer has Ghirlanda-Guerra null overlaps, for instance one where every maximizer needs negatively correlated null directions. That outcome refutes neither the target nor Lemma 3.

## Difference from failed plans

- plan_252211621cea: no signed occupation or switch-sum accounting; the hard estimate is moved to a structural statement about optimizers plus a bound on a restricted tree class, so no step reduces to a weighted unknown FDR.
- plan_503f8fddcbb5: no global-shift record allocation or Stein facet flux; the remainder is a tree-class FDR bound, not a combined signed integrated estimate.
- plan_ee2f7b97740a: no rank-chain transport or Hall-cut certificate; dimension-free control comes from the tree structure forced at maximizers.
- plan_one_sided_order_actual_mean_global_flux_20261106: no aggregate positive flux or crossing charging; the actual largest-rank event is kept inside the finite models given to Lemma 3.
- plan_one_sided_order_common_anchor_rotation_20261107: no rotation interpolation whose terminal terms cancel back to the FDP; the reduction is a chain of value inequalities through approved limits.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: no convex proxy or activation flux; the external input is spin-glass ultrametricity, not a BH majorant.
- plan_one_sided_order_fdp_entropy_mills_coherence_20261107: no trace-versus-coherence certificate (refuted there by a low-coherence family); the low-null-loading lower families are tree models and are handled by Lemma 3 at the permitted order.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no diagonal completion of a signed boundary matrix, hence no $N^2$ completion charge.
- plan_one_sided_order_mixed_trace_replica_cells_20261108: no replica cells or cross-face pairing; replicas enter only through the exchangeable overlap array of a maximizer.
- plan_one_sided_order_negative_contact_transport_20261106: no negative-covariance contact transport; negative null correlations are excluded at maximizers by the identities, not charged.
- plan_one_sided_order_peeling_history_kernel_20261107: no peeling or sibling allocation that saturates at the FDR; sibling structure enters Lemma 3 only through a genuine tree filtration on a restricted class.
- plan_one_sided_order_three_face_noise_packing_20261106: no integrated three-face charge (refuted there in equicorrelation by a $\log N$ divergence); equicorrelated nulls are a one-level tree in Lemma 3, which must give a bound free of $N$.

## Reduction

Black boxes used, each by its statement only: Lemma 1 = [null-tag Ghirlanda-Guerra maximizer](../assets/gaussian_bh_null_overlap_ghirlanda_guerra_maximizer.md), Lemma 2 = [null-ultrametric maximizer selection](../assets/gaussian_bh_null_ultrametric_maximizer_selection.md), Lemma 3 = [null-ultrametric order bound](../assets/gaussian_bh_null_ultrametric_order_bound.md), and items 1, 2 and 5 of the approved [marked-array compactification](../assets/gaussian_bh_exchangeable_array_variational_compactification.md), with the notation of the approved [marked parameter array](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md). Write $B(q)=q[1+\sqrt{\log(1/q)}]$.

**Step 1 (levels).** Let $A_T>0$ and $q_T\in(0,1/2)$ be the universal constants of Lemma 3, and put $q_0=\min\{q_T,\overline\Phi(1)\}$. Then $0<q_0<1/2$ and $q_0$ is universal. Fix $0<q\le q_0$, $0<\sigma<1$ and $\eta>0$. Since $q\le\overline\Phi(1)=q_{\max}$, the hypotheses $0<q\le q_{\max}$ of Lemmas 1 and 2 hold; since $q<1/2$, items 1, 2 and 5 of the compactification apply at $q$; since $q\le q_T$, Lemma 3 applies at $q$.

**Step 2 (a deterministic null-ultrametric maximizer).** Lemma 1 at $(\sigma,q,\eta)$ gives a canonical $P_*\in\mathfrak P_2$ with $\mathcal F(P_*;q,\sigma)-\eta M_2(P_*)=\max_{P\in\mathfrak P_2}\{\mathcal F(P;q,\sigma)-\eta M_2(P)\}$, $P_*(E_0)>0$, and null-tag overlap array satisfying the Ghirlanda-Guerra identities. These are verbatim the hypotheses of Lemma 2 at the same $(\sigma,q,\eta)$. Lemma 2 gives a separable Hilbert space $\mathcal H$ and a deterministic probability $\mu$ on $\mathbb R\times B_{\mathcal H}\times\{0,1\}$ with: (i) $\mu$-a.e. $(\theta,v,\ell)$ has $\ell=\mathbf 1_{\{\theta\le0\}}$, and $\mu\{\ell=1\}>0$; (ii) the iid-generated array law $P_\mu$ lies in $\mathfrak P_2$ and attains $\max_{\mathfrak P_2}\{\mathcal F-\eta M_2\}$; (iii) $P_\mu$-a.s., $C_{ij}\ge0$ and $C_{ik}\ge\min\{C_{ij},C_{jk}\}$ for all pairwise distinct $i,j,k\ge1$ with $\ell_i=\ell_j=\ell_k=1$. By item 2 of the compactification that maximum equals $A_{\eta,\sigma}(q)$, and since $M_2(P_\mu)\ge0$ and $\eta>0$,
$$
A_{\eta,\sigma}(q)=\mathcal F(P_\mu;q,\sigma)-\eta M_2(P_\mu)\le\mathcal F(P_\mu;q,\sigma).
$$

**Step 3 (each finite conditional model satisfies Lemma 3).** Let $\Omega_\mu$ be the set of arrays $\omega$ such that: $\omega$ is a lawful marked array (every finite principal matrix of $C$ is PSD, unit diagonal); $\ell_i=\mathbf 1_{\{\theta_i\le0\}}$ for every $i\ge1$; infinitely many $i$ have $\ell_i=1$; and property (iii) holds. Each condition has $P_\mu$-probability one: the first because $P_\mu\in\mathfrak P$ is a law on lawful arrays (directly, $C_{1:n,1:n}=\mathrm{Gram}(v_1,\ldots,v_n)+\mathrm{diag}(1-\|v_i\|^2)$ with $\|v_i\|\le1$); the second by (i) and countable additivity, the marks $(\theta_i,\ell_i)$ being iid with law the mark marginal of $\mu$; the third by the second Borel-Cantelli lemma, the events $\{\ell_i=1\}$ being independent with common probability $\mu\{\ell=1\}>0$; the fourth by (iii). Hence $P_\mu(\Omega_\mu)=1$.

Fix $n\ge1$ and $\omega\in\Omega_\mu$. By the marked-array definition, conditional on $\omega$ the vector $T^{(n)}$ has law $\mathcal N_n(\theta_{1:n},\Sigma^{(n)})$ with $\Sigma^{(n)}=(1-\sigma^2)C_{1:n,1:n}+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}$. This matrix is symmetric, PSD as a nonnegative combination of the PSD matrices $C_{1:n,1:n}$ and $\mathbf 1\mathbf 1^{\mathsf T}$, and has diagonal $(1-\sigma^2)\cdot1+\sigma^2=1$; it may be singular. So $(n,\theta_{1:n},\Sigma^{(n)})$ is an admissible Gaussian multiple-testing model. Put $I_0=\{i\le n:\theta_i\le0\}$, its original one-sided true-null set. Since $\ell_i=\mathbf 1_{\{\theta_i\le0\}}$ for all $i$, the tagged FDP is $D_n=\sum_{i\in\mathcal R_q}\ell_i/(R_n\vee1)=|\mathcal R_q\cap I_0|/(R_n\vee1)$, where $\mathcal R_q$ is the ordinary largest non-strict BH rejection set of the one-sided p-values $\overline\Phi(T^{(n)}_i)$. As $\mathcal R_q$ is a function of $T^{(n)}$ alone,
$$
\mathbb E[D_n\mid\omega]=\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;n,\theta_{1:n},\Sigma^{(n)}).
$$
Check Lemma 3's hypotheses for this model. Let $i,j\in I_0$ be distinct. Since $\omega$ has infinitely many null-tagged indices, there is $k\ge1$, $k\notin\{i,j\}$, with $\ell_k=1$; (iii) applied to $(i,j,k)$ gives $C_{ij}\ge0$, so $\Sigma^{(n)}_{ij}=(1-\sigma^2)C_{ij}+\sigma^2\ge\sigma^2>0$. Let $i,j,k\in I_0$ be pairwise distinct. The map $x\mapsto(1-\sigma^2)x+\sigma^2$ is strictly increasing because $1-\sigma^2>0$, so it commutes with $\min$, and (iii) gives
$$
\Sigma^{(n)}_{ik}=(1-\sigma^2)C_{ik}+\sigma^2\ge(1-\sigma^2)\min\{C_{ij},C_{jk}\}+\sigma^2=\min\{\Sigma^{(n)}_{ij},\Sigma^{(n)}_{jk}\}.
$$
No condition is required of entries involving $i\notin I_0$ or of the alternative means. (If $|I_0|\le1$ the hypotheses are vacuous.) Since $0<q\le q_T$, Lemma 3 gives $\mathbb E[D_n\mid\omega]\le A_TB(q)$ for every $n\ge1$ and every $\omega\in\Omega_\mu$.

**Step 4 (integration and completion).** By the definition of $\mathcal F_n$ and $P_\mu(\Omega_\mu)=1$,
$$
\mathcal F_n(P_\mu;q,\sigma)=\mathbb E_{\omega\sim P_\mu}\mathbb E[D_n\mid\omega]\le A_TB(q)\qquad(n\ge1).
$$
Since $P_\mu\in\mathfrak P$ and $q\in(0,1/2)$, item 1 of the compactification gives $\mathcal F(P_\mu;q,\sigma)=\lim_n\mathcal F_n(P_\mu;q,\sigma)\le A_TB(q)$. With Step 2, $A_{\eta,\sigma}(q)\le A_TB(q)$. The right side depends on neither $\eta$ nor $\sigma$, and $\eta>0$, $\sigma\in(0,1)$ were arbitrary.

**Step 5 (removing the penalty and the common loading).** Item 2 of the compactification gives $A_{\eta,\sigma}(q)\to W_\sigma(q)$ as $\eta\downarrow0$, so $W_\sigma(q)\le A_TB(q)$ for every $\sigma\in(0,1)$. Item 5 gives $W_\sigma(q)\to F_1(q)$ as $\sigma\downarrow0$, valid since $0<q<1/2$, where $F_1$ is the original unrestricted one-sided supremum of the [worst-case definition](../definitions/gaussian_worst_case_bh_fdr.md), the same $F_1$ as in the target. Hence
$$
F_1(q)\le A_T\,q\left[1+\sqrt{\log(1/q)}\right]\qquad(0<q\le q_0).
$$
Since $q\in(0,q_0]$ was arbitrary, this holds on the whole interval; $F_1(q)$ is the supremum over all $N$, $\theta\in\mathbb R^N$ and unit-diagonal PSD $\Sigma$ (singular included) taken separately at each $q$, so every finite model, including $q$-dependent ones, is covered.

**Step 6 (the target).** This is the sufficient finite-level conclusion of the target's acceptance criterion with $A_1=A_T$ and $\widetilde q_{0,1}=q_0<1$. Explicitly, put $q_{0,1}=\min\{q_0,e^{-1}\}\in(0,1)$ and $C_1=2A_T$. For $0<q\le q_{0,1}$ we have $\log(1/q)\ge1$, so $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$ and
$$
F_1(q)\le A_Tq\left[1+\sqrt{\log(1/q)}\right]\le2A_T\,q\sqrt{\log(1/q)}=C_1q\sqrt{\log(1/q)}.
$$
The constants $C_1=2A_T$ and $q_{0,1}=\min\{q_T,\overline\Phi(1),e^{-1}\}$ are built only from Lemma 3's universal constants and absolute numbers; $\sigma$, $\eta$, $P_*$ and $\mu$ enter only inside limits whose bound does not depend on them. So the constants are independent of $N$, $\theta$, $\Sigma$, the null proportion, the rank and every other model parameter, which is the target statement. No remainder term is left: the only unproved inputs are Lemmas 1-3 as stated.

## Reduction verdict

confirmed

Independent check of `## Reduction` against the exact target statement, using Lemmas 1-3 and items 1, 2 and 5 of the approved [marked-array compactification](../assets/gaussian_bh_exchangeable_array_variational_compactification.md) by their statements only, with the approved [marked parameter array](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md) definition.

1. Levels (Step 1). $q_0=\min\{q_T,\overline\Phi(1)\}$ is universal, and $\overline\Phi(1)\approx0.159<1/2$. So every $0<q\le q_0$ meets Lemma 1's and Lemma 2's $0<q\le\overline\Phi(1)$, the compactification's $q\in(0,1/2)$ (items 1, 2, 5) and Lemma 3's $q\le q_T$. $\sigma\in(0,1)$ and $\eta>0$ are fixed as Lemmas 1, 2 and the compactification require.
2. Chaining Lemma 1 into Lemma 2 (Step 2). Lemma 1's conclusion is literally Lemma 2's hypothesis: a canonical maximizer in $\mathfrak P_2$ of $\mathcal F-\eta M_2$, the same notion of canonical, $P_*(E_0)>0$, Ghirlanda-Guerra identities, at the same $(\sigma,q,\eta)$. Lemma 2 item 2 says $P_\mu$ attains the same maximum, which item 2 of the compactification identifies as $A_{\eta,\sigma}(q)$. Since $M_2(P_\mu)<\infty$ and $M_2\ge0$, we get $A_{\eta,\sigma}(q)\le\mathcal F(P_\mu;q,\sigma)$. The direction of the inequality is right.
3. Full-measure set (Step 3). $P_\mu\in\mathfrak P_2\subseteq\mathfrak P$ is by definition a law on lawful arrays. Canonical tags for every index follow from Lemma 2 item 1 and a countable union of null sets. Infinitely many null tags follow from the second Borel-Cantelli lemma: the tags are iid with $\mu\{\ell=1\}>0$. Property (iii) is Lemma 2 item 3. All four claims are correct.
4. Conditional models (Step 3). The definition gives $T^{(n)}\mid\omega\sim\mathcal N_n(\theta_{1:n},(1-\sigma^2)C_{1:n,1:n}+\sigma^2\mathbf 1\mathbf 1^{\mathsf T})$. This is realized by $g_n$ independent of $\omega$, so $\mathbb E[D_n\mid\omega]$ is the explicit function $\omega\mapsto\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;n,\theta_{1:n},\Sigma^{(n)})$. The tagged numerator equals $|\mathcal R_q\cap I_0|$ because the tags are canonical on $\Omega_\mu$. $\Sigma^{(n)}$ is symmetric, PSD and unit-diagonal, so the model is admissible in the sense of the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), singular matrices included.
5. Lemma 3's hypotheses (Step 3). Nonnegativity is genuinely needed: $C_{ij}\in[-1,1]$ alone would not make $\Sigma^{(n)}_{ij}\ge0$. It is obtained correctly. Lemma 2 item 3 asks for three pairwise distinct null-tagged indices. When $I_0\cap[n]$ has only two elements, a third null index $k$, possibly beyond $n$, exists because there are infinitely many null tags, and item 3 quantifies over all indices of the infinite array. Ultrametricity transfers because $x\mapsto(1-\sigma^2)x+\sigma^2$ is strictly increasing and so commutes with $\min$. Lemma 3 asks nothing of alternative entries or alternative means. Its bound $A_TB(q)$ is uniform in $n$ and in $\omega\in\Omega_\mu$.
6. Integration and limits (Steps 4-5). $\mathcal F_n(P_\mu)\le A_TB(q)$ for every $n$. Item 1 gives the limit $\mathcal F(P_\mu)\le A_TB(q)$, hence $A_{\eta,\sigma}(q)\le A_TB(q)$ for all $\eta>0$ and $\sigma\in(0,1)$. Item 2 ($A_{\eta,\sigma}\to W_\sigma$ as $\eta\downarrow0$) and item 5 ($W_\sigma\to F_1$ as $\sigma\downarrow0$, $0<q<1/2$) pass this bound to $F_1(q)$, because the bound does not depend on $\eta$ or $\sigma$. The $F_1$ in item 5 is the one-sided supremum of the [worst-case definition](../definitions/gaussian_worst_case_bh_fdr.md) over $N$, $\theta\in\mathbb R^N$ and $\Sigma\in\mathcal C_N$. It is exactly the target's $F_1$, taken separately at each $q$.
7. Constants (Step 6). For $q\le e^{-1}$ we have $\log(1/q)\ge1$, so $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$. This gives $C_1=2A_T$ and $q_{0,1}=\min\{q_T,\overline\Phi(1),e^{-1}\}\in(0,1)$. Both are built from Lemma 3's universal constants and absolute numbers only. This is the target's statement, with no remainder.

No gap was found that needs a new idea. The objects $\sigma$, $\eta$, $P_*$ and $\mu$ appear only inside limits of a bound that does not depend on them. The target's listed dependencies are not used, and the reduction does not need them. What remains is Lemmas 1-3 as stated, in particular the Ghirlanda-Guerra lemma (Lemma 1) and the tree order bound (Lemma 3).

## Dropped

Its first lemma, the Ghirlanda-Guerra identities at the null-overlap maximizer, is refuted by a verified counterexample (antipodal nulls with zero moments), so the route cannot be completed; dropped at the researcher's request.
