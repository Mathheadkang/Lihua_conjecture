---
type: plan
title: >-
  Universal one-sided order via clump brackets and a compound-Poisson cap below
  mass e^{-u}
status: abandoned
target_asset: gaussian_bh_one_sided_universal_order_upper
route_lemmas:
  - gaussian_bh_angular_cluster_partial_entropy_bound
  - bh_clump_bracket_pathwise_bound
  - gaussian_bh_subexponential_rare_clump_bracket_cap
route_title: via clump brackets and a compound-Poisson rare cap
origin: researcher
inspired_by:
  - idea_5b8f672e4af1
  - idea_c3bc69b22670
  - idea_2251f0ebf933
  - idea_75d71c7756b4
tags:
  - compound_poisson_route
route_round: 1
reduction_digest: cb545e9c594604a2053d132ca133310286bbd37c0298bc187bc03f9adc16e3f2
reduction_inputs:
  gaussian_bh_one_sided_universal_order_upper: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
  gaussian_bh_fractional_frame_surface_kernel: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
  gaussian_bh_conditional_compound_calibration: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
  gaussian_bh_negative_null_boundary_strip: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
  gaussian_bh_conditional_subpoisson_calibration: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
  gaussian_bh_angular_cluster_partial_entropy_bound: 736750aaadb60109c2ce46215b308676bc7a0cd9e89173948fa97978fa8123b1
  bh_clump_bracket_pathwise_bound: 505283800a561693969245cf14db866c63b7fbf613631c942f088194185139db
  gaussian_bh_subexponential_rare_clump_bracket_cap: d66c527595f7967458383519a22868df0977fdbc6933b1f63f69cb380debf465
reduction_verified_digest: cb545e9c594604a2053d132ca133310286bbd37c0298bc187bc03f9adc16e3f2
reduction_checked: true
---

# Universal one-sided order via clump brackets and a compound-Poisson cap below mass e^{-u}

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement $F_1(q)\le C_1q\sqrt{\log(1/q)}$ for $0<q\le q_{0,1}$, uniformly over every finite $N$, every $\theta$, every unit-diagonal PSD $\Sigma$ (singular allowed), the original labels $I_0=\{i:\theta_i\le0\}$ and ordinary BH with largest qualifying rank. This is the researcher-selected compound-Poisson clumping route ([selection](../ideas/idea_5b8f672e4af1.md), [content](../ideas/idea_c3bc69b22670.md)), aimed at the rare-cluster cap of [Route 1](../ideas/idea_2251f0ebf933.md).

What is new in this route, compared with the parallel angular-chaining route: the rare/heavy threshold is put at mass $\tau_q=e^{-u}$, $u=\overline\Phi^{-1}(q)$, instead of $q^{C}$. Then every heavy cluster has $\log(1/\pi_h)<u$, so the existing per-cluster entropy bound already costs $O(q(1+u))$ in total and **no chaining step is needed**. All the difficulty is moved into one rare-part estimate, which is first converted, by a distribution-free pathwise inequality, into an explicit clump-bracket charge. Competition through the single BH cutoff is encoded there by the floor rank $R_{i,0}$, which is computed with the whole clump of $i$ removed and therefore counts every other clump and every alternative.

External inputs named before execution (the failure record requires this): Chen-Stein compound-Poisson approximation of exceedance clumps (Arratia, Goldstein and Gordon, Statist. Sci. 5 (1990) 403-434; Barbour, Novak and Xia, compound Poisson approximation for extremes) used only as one-sided domination of the clump exceedance count, not as two-sided approximation with Berman-type pair sums; the approved [fractional-frame surface kernel](../assets/gaussian_bh_fractional_frame_surface_kernel.md) for the dimension-free rarity of simultaneous exceedances of separated directions; and the Mecke/Georgii-Nguyen-Zessin formula for clump-level leave-out. These are guidance for proving the rare-cap lemma; the reduction below uses only the three route lemmas and approved dependencies.

**Remainder stated before execution.** After Step 6 the only open quantity is $\mathbb E\sum_{i\in S}\Psi_i$ of the rare-cap lemma. It is not the FDR up to $O(q)$: conditional on all coordinates outside clump $K_l$, the ranks $R_{i,0},R_{i,*}$ are fixed, and $\mathbb E[\sum_{i\in K_l}\Psi_i\mid\cdot]$ is an integral of the clump's conditional joint law against an explicit kernel on the window $[qR_{i,0}/N,\,qR_{i,*}/N]$. The cap must bound the clump's conditional exceedance intensity on that window against the competing count $R_{i,0}$.

Calibration the rare-cap lemma must pass (checked when it is attacked, not here). (i) Independent zero-mean nulls: the charge equals $q\pi_0$. (ii) The [one-null staircase](../ideas/idea_75d71c7756b4.md): one singleton clump with charge $(q/N)H_N\le q$. (iii) Many rare clumps, each with its own staircase: $R_{i,0}$ is of order $N$ because the other staircases are switched on, so the charge is $O(q)$. (iv) The small-null-loading lower family of order $qu$: this is why the cap is at scale $q(1+u)$ and not $O(q)$.

## Route

- gaussian_bh_angular_cluster_partial_entropy_bound: applied with $C=1$ to each heavy cluster (mass $>e^{-u}\ge q$), it gives $A_1q\pi_h(2+\log(1/\pi_h))\le A_1q\pi_h(2+u)$, so all heavy clusters together cost $A_1q(2+u)$ (step 5).
- bh_clump_bracket_pathwise_bound: pathwise and distribution-free, it bounds the rare-part FDP by the clump-bracket charge $\sum_{i\in S}\Psi_i$ (step 6).
- gaussian_bh_subexponential_rare_clump_bracket_cap: the compound-Poisson core, which bounds $\mathbb E\sum_{i\in S}\Psi_i\le A_3q(1+u)$ for every $\kappa_3$-sparse rare clump system (step 6).

## Plan

1. [x] Gram reduction. For any admissible $(N,\theta,\Sigma)$, let $w_i$ be the rows of $\Sigma^{1/2}$ (unit vectors in $\mathbb R^N$ since $\Sigma_{ii}=1$). Then $T_i=\theta_i+w_i^{\mathsf T}Z$ with $Z\sim\mathcal N_N(0,I_N)$ has law $\mathcal N_N(\theta,\Sigma)$. The BH FDR depends only on this law, so it suffices to bound the FDR for unit-loading models with $m=N$, $d=N$. This is the setting of the second and third route lemmas.
2. [x] Boundary strip. For $0<q\le\overline\Phi(e)$ (so $u\ge e$), [the shrinking boundary strip lemma](../assets/gaussian_bh_negative_null_boundary_strip.md) gives $\operatorname{FDR}\le q+\mathbb E[V_B/(R\vee1)]$, where $B=\{i:-a_q<\theta_i\le0\}$, $a_q=2\log u/u$ and $V_B=|\mathcal R_q\cap B|$.
3. [x] Greedy decomposition (deterministic). Fix $\kappa=\kappa_3$ from the rare-cap lemma and put $\tau_q=e^{-u}$. Start with $B_{\rm rem}=B$. While some $j\in B_{\rm rem}$ has $|\{i\in B_{\rm rem}:\|w_i-w_j\|\le\kappa/u\}|>\tau_qN$, take that set as the heavy cluster $G_h$ with $v_h=w_j$, and remove it from $B_{\rm rem}$. When this stops, set $S=B_{\rm rem}$. Then partition $S$ greedily: pick any $c\in S_{\rm rem}$, take $K=\{i\in S_{\rm rem}:\|w_i-w_c\|\le\kappa/u\}$ as a clump with center $c$, and remove it. Claim: each $(G_h,v_h)$ is an angular cluster at scale $\kappa$ in the sense of the partial-entropy lemma, with $\pi_h=|G_h|/N>\tau_q$; and $(S,(K_l),(c_l))$ is a $\kappa$-sparse rare clump system in the sense of the rare-cap lemma. Sparsity holds for every $j\in S$ by the stopping rule, and $S\subseteq B$ gives the near-boundary condition.
4. [x] Split. The sets $G_1,\ldots,G_M,S$ partition $B$, so $V_B=\sum_hV_{G_h}+V_S$ pathwise, all counts referring to the same unmodified BH procedure.
5. [x] Heavy part. If additionally $q\le e^{-2}$, then $u\le\sqrt{2\log(1/q)}\le\log(1/q)$ (Gaussian tail $\overline\Phi(t)\le e^{-t^2/2}$ for $t\ge0$), hence $\pi_h>e^{-u}\ge q=q^{1}$. Apply the partial-entropy lemma with $(\kappa,C)=(\kappa_3,1)$ and $q\le q_1(\kappa_3,1)$. Since $\{Y_{G_h}\le u\}$, $\{u<Y_{G_h}\le b_{G_h}\}$ and $\{Y_{G_h}>b_{G_h}\}$ partition the sample space, parts (a) and (b) give $\mathbb E[V_{G_h}/(R\vee1)]\le A_1q\pi_h(2+\log(1/\pi_h))\le A_1q\pi_h(2+u)$. Summing over $h$, with $\sum_h\pi_h\le1$, gives at most $A_1q(2+u)$.
6. [x] Rare part. The clump-bracket lemma with clumps $K_l$ gives $V_S/(R\vee1)\le\sum_{i\in S}\Psi_i$ pathwise, where $\Psi_i$ coincides with the rare-cap lemma's $\Psi_i$ ($N=m$). Taking expectations and applying the rare-cap lemma ($q\le q_3$) gives $\mathbb E[V_S/(R\vee1)]\le A_3q(1+u)$.
7. [x] Assembly. For $0<q\le\widetilde q_{0,1}:=\min\{\overline\Phi(e),e^{-2},q_1(\kappa_3,1),q_3\}$, $\operatorname{FDR}\le q+A_1q(2+u)+A_3q(1+u)\le A'q(1+u)$ with $A'=1+2A_1+A_3$. Then $u\le\sqrt2\sqrt{\log(1/q)}$ gives $\operatorname{FDR}\le\sqrt2A'q[1+\sqrt{\log(1/q)}]$, uniformly over the model. Take the supremum in $(N,\theta,\Sigma)$.

## Verification

Step 1 removes no generality: it is an exact equality in law, and singular $\Sigma$ is covered because $\Sigma^{1/2}$ exists for every PSD matrix. Steps 2 and 4 keep the original labels, the largest qualifying rank and the unmodified rejection count, as the strip lemma and the two counting lemmas require. Step 3 is deterministic and uses only pairwise distances $\|w_i-w_j\|=\sqrt{2-2\Sigma_{ij}}$, which are intrinsic to $\Sigma$. Its outputs meet the hypotheses of the partial-entropy lemma (radius $\kappa_3/u$ about $v_h$, mass $\ge q^1$) and of the rare-cap lemma (radius, sparsity for every $j\in S$, near-boundary means) verbatim. Every constant in Step 7 depends only on $\kappa_3$ and the universal constants of the lemmas, so it is independent of $N$, $\theta$, $\Sigma$, rank, the number of clusters and the null proportion. Step 7 is exactly the acceptance criterion's sufficient finite-level conclusion $F_1(q)\le A_1q[1+\sqrt{\log(1/q)}]$ on a universal interval. That criterion yields the target with $q_{0,1}=\min\{\widetilde q_{0,1},e^{-1}\}$ and $C_1=2\sqrt2A'$.

## Difference from failed plans

- plan_252211621cea: there is no signed occupation/switch sum and no integration by parts that closes back onto the FDR. The open quantity is the explicit clump-bracket charge with clump-removed floor ranks.
- plan_503f8fddcbb5: no global shift or entrant Stein allocation. Competition enters through the floor rank $R_{i,0}$, not through facet fluxes.
- plan_ee2f7b97740a: no transport or Hall-cut allocation. The rare part is bounded by a one-sided compound-Poisson domination of clump exceedances.
- plan_one_sided_order_actual_mean_global_flux_20261106: no positive-flux envelope over crossings. The cascade effect of clump $l$ is confined to the bracket $[R_{i,0},R_{i,*}]$, computed with the actual maximal rank.
- plan_one_sided_order_common_anchor_rotation_20261107: no rotation and no Abel collation onto the FDP. The pathwise inequality is a one-way upper bound that keeps the clump order $D_i$.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: no convex proxy or PAVA activation flux. BH is used directly.
- plan_one_sided_order_fdp_entropy_mills_coherence_20261107: no trace-versus-deficit certificate. The cap is stated at scale $q(1+u)$, consistent with the $qu$ lower family that refuted that certificate.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no covariance interpolation or SDP completion. The Gaussian input is the clump exceedance law at angular scale $\kappa/u$.
- plan_one_sided_order_mixed_trace_replica_cells_20261108: no replica cells or cross-face pairing. Clumps are angular groups of nulls, not BH cells.
- plan_one_sided_order_negative_contact_transport_20261106: no negative-covariance contact allocation and no inverse-noise diagonal charges.
- plan_one_sided_order_peeling_history_kernel_20261107: no stopped peeling or history kernel whose summation returns the FDR. The remainder is fixed before execution and its kernel is explicit.
- plan_one_sided_order_three_face_noise_packing_20261106: no Gram budget maximized against a covariance other than the original. Heavy clusters pay through the existing entropy lemma, and rare clumps through the original model's clump law.

## Reduction

Black boxes used, by statement only: [the partial entropy bound for one angular cluster](../assets/gaussian_bh_angular_cluster_partial_entropy_bound.md) (constants $A_1(\kappa,C)$, $q_1(\kappa,C)$), [the pathwise clump-bracket bound](../assets/bh_clump_bracket_pathwise_bound.md), [the compound-Poisson rare clump cap](../assets/gaussian_bh_subexponential_rare_clump_bracket_cap.md) (universal $\kappa_3\in(0,1]$, $A_3$, $q_3\in(0,\overline\Phi(e)]$), and the approved [shrinking boundary strip lemma](../assets/gaussian_bh_negative_null_boundary_strip.md). Write $A_1:=A_1(\kappa_3,1)$ and $q_1:=q_1(\kappa_3,1)\in(0,1/2)$; these are universal because $\kappa_3$ is. Put
$$
\widetilde q_{0,1}:=\min\{\overline\Phi(e),\,e^{-2},\,q_1,\,q_3\}\in(0,1/2),
$$
fix $0<q\le\widetilde q_{0,1}$ and an admissible model $(N,\theta,\Sigma)$, and set $u=\overline\Phi^{-1}(q)$. Since $q\le\overline\Phi(e)$ and $\overline\Phi$ is strictly decreasing, $u\ge e>1$.

**Gaussian tail fact.** For $t\ge0$, $\overline\Phi(t)=\int_0^\infty\phi(t+s)\,ds=e^{-t^2/2}\int_0^\infty\phi(s)e^{-ts}\,ds\le\tfrac12e^{-t^2/2}\le e^{-t^2/2}$. Applied at $t=u$: $q\le e^{-u^2/2}$, that is,
$$
u\le\sqrt{2\log(1/q)}.\qquad(\ast)
$$
Since $q\le e^{-2}$ we have $\log(1/q)\ge2$, hence $\sqrt{2\log(1/q)}\le\log(1/q)$ and so $u\le\log(1/q)$, i.e. $e^{-u}\ge q$.

**Step 1 (Gram reduction).** Let $\Sigma^{1/2}$ be the symmetric PSD square root of $\Sigma$ (it exists for every PSD matrix, singular or not) and let $w_i^{\mathsf T}$ be its $i$-th row, so $w_i\in\mathbb R^N$, $w_i^{\mathsf T}w_j=(\Sigma^{1/2}\Sigma^{1/2})_{ij}=\Sigma_{ij}$ and in particular $\|w_i\|^2=\Sigma_{ii}=1$. With $Z\sim\mathcal N_N(0,I_N)$ the vector $T':=\theta+\Sigma^{1/2}Z$, $T'_i=\theta_i+w_i^{\mathsf T}Z$, is Gaussian with mean $\theta$ and covariance $\Sigma^{1/2}I_N\Sigma^{1/2}=\Sigma$, so $T'\overset{d}{=}T$. The quantity $V_q^{(1)}/(R_q^{(1)}\vee1)$ is a fixed Borel function of the score vector (p-values $\overline\Phi(T_i)$, then the BH map, with the deterministic null set $I_0=\{i:\theta_i\le0\}$), so $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)$ equals the FDR computed from $T'$. Henceforth $T=T'$, which is exactly the unit-loading model of the partial-entropy lemma and of the rare-cap lemma with $m=d=N$, the same $\theta$, and loadings $w_1,\dots,w_N$. All BH quantities ($\mathcal R_q$, $R$, $V$) refer to the ordinary BH procedure on all $N$ p-values $p_i=\overline\Phi(T_i)$ at level $q$, with largest qualifying rank, multiplicities and non-strict comparisons.

**Step 2 (boundary strip).** Since $0<q\le\overline\Phi(e)$, the strip lemma applies to $(N,\theta,\Sigma)$ (its $U$ is our $u$) and gives, with $a_q=2\log u/u$, $B:=\{i:-a_q<\theta_i\le0\}$, $V_B=|\mathcal R_q\cap B|$,
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le q+\mathbb E\!\left[\frac{V_B}{R\vee1}\right].
$$
Both sides concern the law of $T$ only, so they may be evaluated in the representation of Step 1. Note $B\subseteq I_0$.

**Step 3 (greedy decomposition).** Put $\kappa=\kappa_3$, $\tau_q=e^{-u}$, $r=\kappa/u$. The construction below uses only the deterministic vectors $w_i$ and the deterministic set $B$.

*Heavy phase.* Set $B_{\rm rem}^{(0)}=B$. Given $B^{(h-1)}_{\rm rem}$, if some $j\in B_{\rm rem}^{(h-1)}$ satisfies $|\{i\in B_{\rm rem}^{(h-1)}:\|w_i-w_j\|\le r\}|>\tau_qN$, choose one such $j=j_h$, put $G_h=\{i\in B_{\rm rem}^{(h-1)}:\|w_i-w_{j_h}\|\le r\}$, $v_h=w_{j_h}$, and $B_{\rm rem}^{(h)}=B_{\rm rem}^{(h-1)}\setminus G_h$. Each $G_h$ contains $j_h$, so is nonempty, and the procedure stops after some $M\le|B|$ steps (possibly $M=0$). Put $S=B_{\rm rem}^{(M)}$.

Properties. (H1) $\varnothing\ne G_h\subseteq B\subseteq I_0$, $v_h$ is a unit vector of $\mathbb R^N$, and $\|w_i-v_h\|\le\kappa_3/u$ for $i\in G_h$; since $\kappa_3\in(0,1]$, $(G_h,v_h)$ is an angular cluster at scale $\kappa_3$ in the sense of the partial-entropy lemma (with $m=d=N$). (H2) $\pi_h:=|G_h|/N>\tau_q=e^{-u}\ge q=q^1$, using the tail fact above. (H3) Because the procedure stopped, for every $j\in S$ we have $|\{i\in S:\|w_i-w_j\|\le\kappa_3/u\}|\le\tau_qN$.

*Clump phase.* If $S=\varnothing$ put $L=0$. Otherwise set $S^{(0)}_{\rm rem}=S$; given $S^{(l-1)}_{\rm rem}\ne\varnothing$, pick any $c_l\in S^{(l-1)}_{\rm rem}$, put $K_l=\{i\in S^{(l-1)}_{\rm rem}:\|w_i-w_{c_l}\|\le r\}$ (it contains $c_l$) and $S^{(l)}_{\rm rem}=S^{(l-1)}_{\rm rem}\setminus K_l$; stop when $S^{(L)}_{\rm rem}=\varnothing$. Then $K_1,\dots,K_L$ are nonempty, pairwise disjoint and partition $S$; $c_l\in K_l$; and $\|w_i-w_{c_l}\|\le\kappa_3/u$ for $i\in K_l$ (clump radius). Together with (H3) (sub-exponential sparsity, for every $j\in S$) and $S\subseteq B=\{i:-a_q<\theta_i\le0\}$, where $a_q=2\log u/u$ is exactly the rare-cap lemma's $a_q$ (defined there since $u>1$) and $\tau_q=e^{-u}$ is exactly its $\tau_q$ with $m=N$, the triple $(S,(K_l),(c_l))$ is a $\kappa_3$-sparse rare clump system in the sense of the rare-cap lemma whenever $S\ne\varnothing$.

**Step 4 (split).** By construction $G_1,\dots,G_M,S$ are pairwise disjoint with union $B$. Hence, for every sample point, $V_B=|\mathcal R_q\cap B|=\sum_{h=1}^M|\mathcal R_q\cap G_h|+|\mathcal R_q\cap S|=\sum_hV_{G_h}+V_S$, with one and the same rejection set $\mathcal R_q$ and denominator $R\vee1$, so
$$
\mathbb E\!\left[\frac{V_B}{R\vee1}\right]=\sum_{h=1}^M\mathbb E\!\left[\frac{V_{G_h}}{R\vee1}\right]+\mathbb E\!\left[\frac{V_S}{R\vee1}\right].
$$

**Step 5 (heavy part).** Fix $h$. The hypotheses of the partial-entropy lemma hold with $(\kappa,C)=(\kappa_3,1)$: $\kappa_3\in(0,1]$, $C=1$, $0<q\le q_1(\kappa_3,1)$, the model is the unit-loading model of Step 1, $(G_h,v_h)$ is an angular cluster at scale $\kappa_3$ by (H1), and $\pi_{G_h}=\pi_h\ge q^1$ by (H2); its $V_G$ and $R$ are the counts of the same unmodified BH on all $N$ coordinates, as here. Since $b_{G_h}\ge u$, the events $\{Y_{G_h}\le u\}$, $\{u<Y_{G_h}\le b_{G_h}\}$, $\{Y_{G_h}>b_{G_h}\}$ partition the sample space, so adding (a) and (b),
$$
\mathbb E\!\left[\frac{V_{G_h}}{R\vee1}\right]\le A_1q\pi_h+A_1q\pi_h\Bigl(1+\log\frac1{\pi_h}\Bigr)=A_1q\pi_h\Bigl(2+\log\frac1{\pi_h}\Bigr)<A_1q\pi_h(2+u),
$$
the last step by $\pi_h>e^{-u}$. The $G_h$ are disjoint subsets of $\{1,\dots,N\}$, so $\sum_h\pi_h\le1$ and
$$
\sum_{h=1}^M\mathbb E\!\left[\frac{V_{G_h}}{R\vee1}\right]\le A_1q(2+u)
$$
(trivially also when $M=0$).

**Step 6 (rare part).** If $S=\varnothing$ then $V_S=0$. Otherwise apply the clump-bracket lemma pointwise, for each sample point, to the deterministic vector $p=(\overline\Phi(T_1),\dots,\overline\Phi(T_N))\in[0,1]^N$, level $q\in(0,1)$, the set $I_0$, $S\subseteq B\subseteq I_0$, and the partition $K_1,\dots,K_L$ of $S$ into nonempty sets. Its $R_{i,0},R_{i,*},D_i,\Psi_i$ are defined from the same replacements ($p_i\mapsto0$ and $p_j\mapsto1$ on $K_l\setminus\{i\}$; $p_j\mapsto0$ on $K_l$; the same $D_i$) and with $N=m$ in $\mathbf 1\{p_i\le qR_{i,*}/N\}/\max\{R_{i,0},D_i,Np_i/q\}$, so they coincide with the rare-cap lemma's quantities. Each $\Psi_i$ is a Borel function of $T$ (BH counts are finite-valued Borel functions of $p$), nonnegative and at most $1$, and the lemma's expectation form gives
$$
\mathbb E\!\left[\frac{V_S}{R\vee1}\right]\le\mathbb E\Bigl[\sum_{i\in S}\Psi_i\Bigr].
$$
By Step 3, $(S,(K_l),(c_l))$ is a $\kappa_3$-sparse rare clump system for the unit-loading model with $m=d=N$, and $0<q\le q_3$ (so also $q<1/2$ and $u>1$). The rare-cap lemma gives $\mathbb E\sum_{i\in S}\Psi_i\le A_3q(1+u)$, hence $\mathbb E[V_S/(R\vee1)]\le A_3q(1+u)$, valid also when $S=\varnothing$.

**Step 7 (assembly).** Steps 2, 4, 5, 6 give
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le q+A_1q(2+u)+A_3q(1+u)\le(1+2A_1+A_3)\,q\,(1+u)=A'q(1+u),
$$
with $A'=1+2A_1+A_3$, because $q\le q(1+u)$, $2+u\le2(1+u)$. By $(\ast)$, $1+u\le1+\sqrt2\sqrt{\log(1/q)}\le\sqrt2\bigl(1+\sqrt{\log(1/q)}\bigr)$, so
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le\sqrt2A'\,q\bigl[1+\sqrt{\log(1/q)}\bigr]\qquad(0<q\le\widetilde q_{0,1}).
$$
The constants $\sqrt2A'$ and $\widetilde q_{0,1}$ depend only on $\kappa_3,A_3,q_3$ and $A_1(\kappa_3,1),q_1(\kappa_3,1)$, all universal; they do not depend on $N,\theta,\Sigma$, the rank, the null proportion, $M$, $L$ or $|S|$. Taking the supremum over admissible $(N,\theta,\Sigma)$ at each fixed $q$ yields $F_1(q)\le\sqrt2A'q[1+\sqrt{\log(1/q)}]$ on $0<q\le\widetilde q_{0,1}<1$, which is the sufficient finite-level conclusion of the target's acceptance criterion. Concretely, with $q_{0,1}=\min\{\widetilde q_{0,1},e^{-1}\}=\widetilde q_{0,1}$ (as $e^{-2}<e^{-1}$) we have $\log(1/q)\ge1$, so $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$, and
$$
F_1(q)\le C_1q\sqrt{\log(1/q)},\qquad C_1=2\sqrt2A'=2\sqrt2\bigl(1+2A_1(\kappa_3,1)+A_3\bigr),\qquad0<q\le q_{0,1}.
$$
No term is left over: the only inputs are the four statements above, and the dependencies $\mathtt{gaussian\_bh\_fractional\_frame\_surface\_kernel}$, $\mathtt{gaussian\_bh\_conditional\_compound\_calibration}$ and $\mathtt{gaussian\_bh\_conditional\_subpoisson\_calibration}$ are not needed for the reduction (they are inputs for proving the route lemmas). $\square$

## Reduction verdict

confirmed

1. Constants and level range. $\kappa_3,A_3,q_3$ are universal by the rare-cap statement, and $A_1(\kappa_3,1),q_1(\kappa_3,1)$ depend only on $(\kappa_3,1)$, so they are universal too. $\widetilde q_{0,1}=\min\{\overline\Phi(e),e^{-2},q_1,q_3\}$ lies in $(0,1/2)$ and is at most $\overline\Phi(e)\le\overline\Phi(1)$, $q_1$ and $q_3$, so all four black boxes apply at every $0<q\le\widetilde q_{0,1}$, including the requirement $q<1/2$ in the definitions of the partial-entropy and rare-cap lemmas. Since $q\le\overline\Phi(e)$, $u\ge e>1$, so the rare cap's $\tau_q,a_q$ are defined.
2. Tail fact. $\phi(t+s)=e^{-t^2/2}e^{-ts}\phi(s)$, so $\overline\Phi(t)\le\tfrac12e^{-t^2/2}$ for $t\ge0$. This gives $u\le\sqrt{2\log(1/q)}$, and with $\log(1/q)\ge2$ also $u\le\log(1/q)$, i.e. $e^{-u}\ge q$. Correct.
3. Step 1 (same-law re-representation). The symmetric PSD root exists for singular $\Sigma$; its rows $w_i\in\mathbb R^N$ satisfy $w_i^{\mathsf T}w_j=\Sigma_{ij}$, so $\|w_i\|=1$, and $\theta+\Sigma^{1/2}Z\sim\mathcal N_N(\theta,\Sigma)$. The FDP is a Borel function of $T$ with the deterministic set $I_0$, so the FDR is unchanged. This is exactly the unit-loading model of both lemmas with $m=d=N\ge1$.
4. Step 2 (strip lemma). Its hypotheses are $N\ge1$, PSD unit-diagonal $\Sigma$ (singular allowed) and $0<q\le\overline\Phi(e)$ for the "in particular" part. All hold, $U=u$, and $a_q,B_q$ coincide with the plan's $a_q,B$. The conclusion $\mathrm{FDR}\le q+\mathbb E[V_B/(R\vee1)]$ depends on the law alone, so it carries over to the Step 1 representation. $B\subseteq I_0$.
5. Step 3, heavy phase. Each $G_h$ contains $j_h$, the $G_h$ are disjoint and $M\le|B|$. $(G_h,w_{j_h})$ satisfies the partial-entropy lemma's definition of an angular cluster at scale $\kappa_3$ word for word: $\varnothing\ne G_h\subseteq I_0$, $v_h$ is a unit vector in $\mathbb R^N$, and $\|w_i-v_h\|\le\kappa_3/u$ with the same $u=\overline\Phi^{-1}(q)$. Also $\pi_h>e^{-u}\ge q=q^C$ with $C=1$. The construction uses only the deterministic $w_i$ and $B$, so the clusters are deterministic, as the lemma requires.
6. Step 3, remainder versus the rare-cap hypotheses. The stopping rule says that no $j\in S=B^{(M)}_{\rm rem}$ has more than $\tau_qN$ points of $S$ within distance $r=\kappa_3/u$. That is exactly condition 2 (sub-exponential sparsity) with $m=N$ and $\tau_q=e^{-u}$. The clump phase gives nonempty, pairwise disjoint $K_l$ that partition $S$, with $c_l\in K_l$ and $\|w_i-w_{c_l}\|\le\kappa_3/u$, which is condition 1. $S\subseteq B=\{i:-a_q<\theta_i\le0\}$ with the rare cap's own $a_q=2\log u/u$. So when $S\ne\varnothing$, $(S,(K_l),(c_l))$ is a $\kappa_3$-sparse rare clump system as defined there, word for word. The case $S=\varnothing$ is handled separately and contributes $V_S=0$.
7. Step 4. The sets $G_1,\dots,G_M,S$ partition $B$, so $V_B$ splits exactly over the same rejection set and denominator, and linearity of expectation (all terms bounded and nonnegative) gives the displayed identity.
8. Step 5. The lemma's $V_G$ and $R$ are counts of the same full BH procedure. $b_G=\overline\Phi^{-1}(q\pi_G)\ge u$ is finite because $0<q\pi_G<1/2$. So $\{Y\le u\},\{u<Y\le b\},\{Y>b\}$ partition the sample space, and (a)+(b) bound the whole $\mathbb E[V_{G_h}/(R\vee1)]$ by $A_1q\pi_h(2+\log(1/\pi_h))<A_1q\pi_h(2+u)$. Disjointness gives $\sum_h\pi_h\le1$. The constants do not depend on $M$, the other clusters or the outside directions, as the lemma states.
9. Step 6. The clump-bracket lemma's hypotheses hold: $N\ge1$, $q\in(0,1)$, a deterministic $p\in[0,1]^N$ at each sample point, $S\subseteq I_0$, and a partition into nonempty clumps. Its expectation form holds for random p-values on any probability space. Its $p^{(i,0)},p^{(i,*)},D_i,\Psi_i$, with $N=m$, are literally the rare cap's $R_{i,0},R_{i,*},D_i,\Psi_i$, so the two bounds chain to $\mathbb E[V_S/(R\vee1)]\le A_3q(1+u)$.
10. Step 7. $q+A_1q(2+u)+A_3q(1+u)\le(1+2A_1+A_3)q(1+u)$, and $1+u\le\sqrt2(1+\sqrt{\log(1/q)})$ by $(\ast)$. This gives the acceptance criterion's sufficient finite-level form uniformly over $(N,\theta,\Sigma)$ at each fixed $q$, hence for the supremum $F_1(q)$. Converting with $q_{0,1}=\widetilde q_{0,1}\le e^{-2}$ gives $F_1(q)\le C_1q\sqrt{\log(1/q)}$ with $C_1=2\sqrt2(1+2A_1(\kappa_3,1)+A_3)\in(0,\infty)$ universal. That is the exact target statement.

No lemma is used beyond its statement and no term is left over. The unused dependencies (surface kernel, the two calibrations) do not affect validity. What remains is proving the three draft route lemmas.

## Dropped

Researcher-approved drop (12 Nov 2026): its rare-clump cap is refuted by a verified counterexample showing the clump bracket charge can be of order q log(1/q); the route cannot be completed as stated. Its proved lemmas (partial entropy bound, pathwise clump-bracket bound) stay approved for other routes.
