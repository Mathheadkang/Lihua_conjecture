---
type: plan
title: >-
  Universal one-sided order via sign splitting, a linear Simes bound and
  Gaussian-refined linking
status: pending
target_asset: gaussian_bh_one_sided_universal_order_upper
route_lemmas:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_bh_sign_split_cluster_steering_bound
  - gaussian_null_positive_carrier_cluster_intensity_bound
route_title: 'via sign splitting, linear Simes and refined linking'
origin: researcher
inspired_by:
  - idea_afb46a36a429
  - idea_26f348b94400
  - idea_33e7435632a7
  - idea_e6e1f4c16f22
  - idea_76d8bdfb8584
tags:
  - sign_split_route
route_round: 1
reduction_digest: b5cbaf29d2161f975e77d7218c31142cba0c2a79f1a8e4ce8c6966276a516f04
reduction_inputs:
  gaussian_bh_one_sided_universal_order_upper: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
  gaussian_bh_fractional_frame_surface_kernel: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
  gaussian_bh_conditional_compound_calibration: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
  gaussian_bh_negative_null_boundary_strip: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
  gaussian_bh_conditional_subpoisson_calibration: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
  gaussian_simes_one_sided_uniform_linear_bound: 056ac9e2897851e7a490dc0b61a7810240e679307e0595cf07ea9c09c0ec8abc
  gaussian_bh_sign_split_cluster_steering_bound: 4f504776ef9d05ca6e613df26ad574964aa50a24ff5098db3d1c7b8692792457
  gaussian_null_positive_carrier_cluster_intensity_bound: da363815fd21877edf046c9113f5e0ad720e6f24faa65ff2548ecfa8eb26cd0b
reduction_verified_digest: b5cbaf29d2161f975e77d7218c31142cba0c2a79f1a8e4ce8c6966276a516f04
reduction_checked: true
---

# Universal one-sided order via sign splitting, a linear Simes bound and Gaussian-refined linking

## Goal

Target: [gaussian_bh_one_sided_universal_order_upper](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement through its acceptance criterion: $F_1(q)\le A_1q[1+\sqrt{\log(1/q)}]$ on a universal interval, for every finite $N$, every $\theta$, and every unit-diagonal PSD $\Sigma$, singular ones included. The original labels $I_0=\{i:\theta_i\le0\}$, the largest qualifying BH rank and non-strict comparisons stay fixed throughout. This plan works out the researcher-selected route of [the selected direction](../ideas/idea_afb46a36a429.md), whose content is in [the route proposal](../ideas/idea_26f348b94400.md). The FDP is split into three parts:

- a null-only crossing part, paid by a linear Simes bound (Core I of [the two-class proposal](../ideas/idea_33e7435632a7.md));
- a steering part, in which nulls whose residual correlations across clusters are nonpositive given a carrier are paid by their conditional cluster intensity (sign split, negative side);
- a null-side refined-linking part, in which positive null association is moved into a null-only carrier and into clusters, and the resulting intensity must have the half-space tail (sign split, positive side).

External inequalities named before execution. The [linear Simes bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md) supplies Core I; on pure-sign classes it is backed by the [positive Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) and by the Chi-Ramdas-Wang nonpositive-correlation bound recorded in idea_4e6b9464da07. The steering lemma is meant to use Gaussian interpolation of the cross-cluster covariance (block negative association) together with the approved [sub-Poisson calibration](../assets/gaussian_bh_conditional_subpoisson_calibration.md) and [compound calibration](../assets/gaussian_bh_conditional_compound_calibration.md) mechanisms. The refined-linking lemma is meant to use the Gaussian Mills-ratio gain of conditional tail ratios when the residual standard deviation is at least of order $1/U$, with $U=\overline\Phi^{-1}(q)$.

Remainders, stated before execution. After the reduction below, the only quantities left are the following, and none of them is the FDR up to $O(q)$:

- $(\mathrm{R}_1)$ $\mathbb P(E_0)$, a null-only Simes rejection probability;
- $(\mathrm{R}_2)$ $\mathbb E[\mathrm{FDP}\,\mathbf 1_{E_0^c}]-C_2\mathbb E\min\{1,qK(Y)\}$, the steering excess. It must be $O(q)$ against an explicit conditional cluster intensity;
- $(\mathrm{R}_3)$ $\mathbb E\min\{1,qK_0(Y)\}$, a functional of the null law alone. It contains no alternatives and no BH rank.

## Route

- gaussian_simes_one_sided_uniform_linear_bound: bounds $\mathbb P(E_0)$, the null-only crossing event, by $C_Sq$ in step 2. This is the linear Simes input; by [the amplification observation](../ideas/idea_8699fa13f1f6.md) it is also necessary for the target.
- gaussian_bh_sign_split_cluster_steering_bound: on $E_0^c$, bounds the FDP by $C_2q+C_2\mathbb E\min\{1,qK(Y)\}$ for any carrier and partition that satisfy the sign-split condition (step 4). This is the negative-side and steering half.
- gaussian_null_positive_carrier_cluster_intensity_bound: supplies a null-only carrier $Y$ and a partition that satisfy the sign-split condition, with $\mathbb E\min\{1,qK_0(Y)\}\le C_3q\sqrt{\log(1/q)}$ (step 3). This is the positive-side Gaussian-refined linking.

## Plan

1. [x] Trivial cases and notation. If $I_0=\varnothing$, then $V\equiv0$ and $\operatorname{FDR}=0$. Otherwise put $N_0=|I_0|\ge1$ and $\alpha=qN_0/N\in(0,q]$. Fix $0<q\le q_*=\min\{q_0,q_2,q_3\}$, where $q_0$, $q_2$ and $q_3$ are the intervals of the three lemmas. Since $0\le\mathrm{FDP}\le1$,
$$
\mathrm{FDP}\le\mathbf 1_{E_0}+\mathrm{FDP}\,\mathbf 1_{E_0^c},
\qquad
E_0=\{\exists k\ge1:\#\{i\in I_0:p_i\le qk/N\}\ge k\}.
$$
2. [x] Core I: $\mathbb P(E_0)\le C_Sq$. Write $T_i=\theta_i+X_i$ with $X_{I_0}\sim\mathcal N_{N_0}(0,\Sigma_{I_0I_0})$, where $\Sigma_{I_0I_0}\in\mathcal C_{N_0}$. Since $\theta_i\le0$, we have $p_i\ge\widetilde p_i=\overline\Phi(X_i)$ for $i\in I_0$. Moreover, $E_0$ is the event that the ordered null p-values satisfy $p_{0,(k)}\le\alpha k/N_0$ for some $k\le N_0$, and this event is decreasing in the p-values. Hence $\mathbb P(E_0)$ is at most the centered Simes rejection probability for $N_0$ tests at level $\alpha\le q_0$. By [the linear Simes bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md), it is at most $C\alpha\le C_Sq$, where $C_S=C$ is that lemma's constant.
3. [x] Positive carrier. Apply [the positive-carrier lemma](../assets/gaussian_null_positive_carrier_cluster_intensity_bound.md) with $n=N_0$, $\mu=\theta_{I_0}$ and $\Sigma_0=\Sigma_{I_0I_0}$, to get $m$, $A$, $D$ and $\mathcal C$. On the original space, extended if needed, define $Y=A(T_{I_0}-\theta_{I_0})+W$ with $W\sim\mathcal N_m(0,D)$ independent of the whole vector $T$. Then $(T,Y)$ is jointly Gaussian. The joint law of $(T_{I_0},Y)$ is the law of $(X,Y)$ in that lemma, so $\operatorname{Cov}(T_{I_0}\mid Y)$ is the lemma's matrix $Q$ and satisfies its sign-split condition for $\mathcal C$. The conditional probabilities $\mathbb P(\min_{i\in c}p_i\le t\mid Y)$ have the lemma's joint law, so
$$
\mathbb E\min\{1,qK_0(Y)\}\le C_3q\sqrt{\log(1/q)}.
$$
The carrier never contains an alternative coordinate.
4. [x] Steering. The pair $(Y,\mathcal C)$ meets the hypotheses of [the steering lemma](../assets/gaussian_bh_sign_split_cluster_steering_bound.md). Its intensity uses the denominator $N\ge N_0$, so
$$
K(Y)=\max\Bigl\{1,\tfrac{N_0}{N}\sup_t\tfrac1{N_0t}\textstyle\sum_c|c|\,\mathbb P(\min_{i\in c}p_i\le t\mid Y)\Bigr\}\le K_0(Y).
$$
Hence
$$
\mathbb E[\mathrm{FDP}\,\mathbf 1_{E_0^c}]\le C_2q+C_2\mathbb E\min\{1,qK(Y)\}\le C_2q+C_2C_3q\sqrt{\log(1/q)}.
$$
5. [x] Assembly. Taking expectations in step 1 and using steps 2-4 gives, for every finite model and every $0<q\le q_*$,
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le(C_S+C_2)q+C_2C_3q\sqrt{\log(1/q)}\le A_1q\bigl[1+\sqrt{\log(1/q)}\bigr],
$$
with $A_1=\max\{C_S+C_2,C_2C_3\}$. The right side does not depend on the model, so taking the supremum gives the same bound for $F_1(q)$.

## Verification

Step 5 is exactly the sufficient finite-level conclusion in the target's acceptance criterion, with $\widetilde q_{0,1}=q_*$. The target's own conversion then gives the target constant $C_1=2A_1$ and $q_{0,1}=\min\{q_*,e^{-1}\}$. The following are uniform because each lemma is stated with universal constants and all model parameters may depend on $q$: all $N$, all $\theta$ (only $\theta_{I_0}\le0$ enters steps 2-3), all unit-diagonal PSD $\Sigma$ including singular ones (both lemmas and the linear Simes bound allow singular covariance and the pseudo-inverse conditional covariance), and all null proportions (enter only through $N_0/N\le1$ in steps 2 and 4). The BH procedure is never altered, and the FDP and its labels are the original ones.

Calibrations to run before and during execution, as sanity checks on the lemma statements rather than proofs:

- independent nulls with arbitrary alternatives: $Y$ constant and singleton clusters give $K_0\equiv1$, so remainder $(\mathrm{R}_3)$ is $O(q)$ and $(\mathrm{R}_2)$ is the class-E conjecture;
- Lei's one-factor family ([lower bound](../assets/lei2026_one_sided_fdr_lower.md)): conditioning on the null sample mean gives a nonpositive residual and $K_0\approx e^{z_+^2/2}$, the half-space tail;
- independent comonotone blocks: the blocks as clusters give $K_0\equiv1$;
- nulls with positively correlated alternative copies: the carrier is null-only, so these copies are never revealed. This is the over-revealing failure of conditioning on all alternatives.

The first execution check of each lemma must also run the tail diagnostic of [the tail-calibration note](../ideas/idea_76d8bdfb8584.md) on its intensity: a Markov tail of $qK_0$ over a growing range of $\lambda$ refutes the chosen carrier, not the target.

## Difference from failed plans

- plan_252211621cea: no signed half-line occupation or switch sum, so it never reaches the masked switch sum that integration by parts identified with the FDR. The remainder is an explicit Simes probability plus a conditional intensity.
- plan_503f8fddcbb5: no global shift, record partition or entrant Stein allocation. Covariance enters only through a conditional covariance sign condition, not through facet coefficients $1-\Sigma_{jk}$.
- plan_ee2f7b97740a: no rank-chain transport or Hall-cut max-flow, hence no non-potential cut mass. BH rank is handled once, inside the steering lemma, against a fixed intensity.
- plan_one_sided_order_actual_mean_global_flux_20261106: no positive-flux charging of critical crossings. The largest-rank event enters only through $E_0$ and the steering lemma, so the inactive crossings that made the marginal envelope $N^2/4$ are never counted.
- plan_one_sided_order_common_anchor_rotation_20261107: no rotation or integrated signed facet flux. Its terminal identities cancelled back to the FDP; here no identity is used, only two inequalities with non-FDR right sides.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: no convex isotonic proxy, so there is no activation flux. The majorant is a conditional cluster intensity whose tail can be tested directly.
- plan_one_sided_order_fdp_entropy_mills_coherence_20261107: no trace-versus-deficit certificate of order $q$. The intensity remainder $(\mathrm{R}_3)$ is allowed the half-space size $q\sqrt{\log(1/q)}$, which the selected-null coherence counterfamily requires.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no diagonal completion of a BH boundary matrix, so there is no face or label multiplicity. Gaussian interpolation is used only for cross-cluster negative association at fixed conditional law.
- plan_one_sided_order_mixed_trace_replica_cells_20261108: no replica cells or cross-face pairing. Distinct rank faces are never compared; the comparison is with the conditional cluster intensity.
- plan_one_sided_order_negative_contact_transport_20261106: no contact transport or diagonal allocation with inverse-noise charges. Negative correlations are not transported but absorbed by the sign-split condition, and degenerate residuals are allowed by clusters and pseudo-inverses.
- plan_one_sided_order_peeling_history_kernel_20261107: no peeling histories, whose summation by parts ended at the unknown FDR. Remainder $(\mathrm{R}_3)$ is null-only and free of BH masks.
- plan_one_sided_order_three_face_noise_packing_20261106: no budget maximized over an auxiliary covariance, the source of its $\log N$ obstruction. Every quantity uses the actual conditional covariance of the original model.

## Reduction

The three route lemmas are used as black boxes, by their statements: the [linear Simes bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md) (constants $C,q_0$), the [steering lemma](../assets/gaussian_bh_sign_split_cluster_steering_bound.md) (constants $C_2,q_2$) and the [positive-carrier lemma](../assets/gaussian_null_positive_carrier_cluster_intensity_bound.md) (constants $C_3,q_3$). None of the target's listed dependencies is needed. Put $C_S=C$, $q_*=\min\{q_0,q_2,q_3\}\in(0,1)$ and $A_1=\max\{C_S+C_2,\,C_2C_3\}$; these are universal.

Fix $0<q\le q_*$ and an admissible model $(N,\theta,\Sigma)$, $\Sigma\in\mathcal C_N$ possibly singular, $T\sim\mathcal N_N(\theta,\Sigma)$, $p_i=\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$, and ordinary BH at level $q$ with its rejection set $\mathcal R$, $R=|\mathcal R|$, $V=|\mathcal R\cap I_0|$, $\mathrm{FDP}=V/(R\vee1)$. We show
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le A_1q\bigl[1+\sqrt{\log(1/q)}\bigr].
$$

**Step 1 (trivial case, splitting).** If $I_0=\varnothing$ then $V\equiv0$ and the FDR is $0$. Assume $N_0=|I_0|\ge1$ and put $\alpha=qN_0/N\in(0,q]$. Let
$$
E_0=\Bigl\{\exists k\in\{1,\ldots,N\}:\ \#\{i\in I_0:p_i\le qk/N\}\ge k\Bigr\},
$$
which is exactly the event of the same name in the steering lemma. Since $0\le\mathrm{FDP}\le1$, pointwise $\mathrm{FDP}=\mathrm{FDP}\,\mathbf 1_{E_0}+\mathrm{FDP}\,\mathbf 1_{E_0^c}\le\mathbf 1_{E_0}+\mathrm{FDP}\,\mathbf 1_{E_0^c}$, hence
$$
\operatorname{FDR}\le\mathbb P(E_0)+\mathbb E\bigl[\mathrm{FDP}\,\mathbf 1_{E_0^c}\bigr].
$$
Enlarging the probability space by an independent factor (used in Step 3) changes neither side, since both are expectations of functions of $T$.

**Step 2 ($\mathbb P(E_0)\le C_Sq$).** Put $X=T_{I_0}-\theta_{I_0}\sim\mathcal N_{N_0}(0,\Sigma_{I_0I_0})$. The principal submatrix $\Sigma_{I_0I_0}$ is symmetric, PSD and unit-diagonal, so $\Sigma_{I_0I_0}\in\mathcal C_{N_0}$ (possibly singular). Let $\widetilde p_i=\overline\Phi(X_i)$, $i\in I_0$. Since $\theta_i\le0$ and $\overline\Phi$ is decreasing, $p_i=\overline\Phi(\theta_i+X_i)\ge\widetilde p_i$.

Since $\#\{i\in I_0:p_i\le s\}\le N_0$, a $k$ witnessing $E_0$ satisfies $k\le N_0$. For $k\le N_0$, writing $p_{0,(1)}\le\cdots\le p_{0,(N_0)}$ for the ordered null p-values with multiplicities, $\#\{i\in I_0:p_i\le qk/N\}\ge k$ is equivalent to $p_{0,(k)}\le qk/N=\alpha k/N_0$. Thus
$$
E_0=\bigl\{\exists k\in\{1,\ldots,N_0\}:p_{0,(k)}\le\alpha k/N_0\bigr\}.
$$
Each count $\#\{i\in I_0:p_i\le s\}$ is nonincreasing in every $p_i$, so replacing $p_i$ by $\widetilde p_i\le p_i$ only enlarges the event: $E_0\subseteq\widetilde E_0=\{\exists k\le N_0:\widetilde p_{0,(k)}\le\alpha k/N_0\}$. The event $\widetilde E_0$ is exactly the event of the linear Simes bound for dimension $N_0$, covariance $\Sigma_{I_0I_0}$ and level $\alpha$, and $0<\alpha\le q\le q_0$. Hence
$$
\mathbb P(E_0)\le\mathbb P(\widetilde E_0)\le C\alpha\le C_Sq .
$$

**Step 3 (null-only carrier).** Apply the positive-carrier lemma with $n=N_0$, $\mu=\theta_{I_0}\in(-\infty,0]^{N_0}$, $\Sigma_0=\Sigma_{I_0I_0}\in\mathcal C_{N_0}$ and the level $q\le q_3$. It yields $m\ge0$, $A\in\mathbb R^{m\times N_0}$, a diagonal PSD $D$ and a partition $\mathcal C$ of $I_0$ (identified with $\{1,\ldots,N_0\}$) into nonempty clusters. On the product of the original space with a space carrying $W\sim\mathcal N_m(0,D)$, so that $W$ is independent of the whole vector $T$, define
$$
Y=A(T_{I_0}-\theta_{I_0})+W\qquad(Y\text{ constant if }m=0).
$$
Then $(T-\theta,W)$ is a centered Gaussian vector (independent Gaussian blocks), and $(T,Y)$ is an affine image of it, hence jointly Gaussian. With $X=T_{I_0}-\theta_{I_0}\sim\mathcal N_{N_0}(0,\Sigma_0)$ from Step 2, the pair $(T_{I_0},Y)=(\mu+X,\,AX+W)$ has exactly the joint law of the lemma's pair (there $X'\sim\mathcal N(\mu,\Sigma_0)$ and $Y'=A(X'-\mu)+W'$ with $W'\sim\mathcal N_m(0,D)$ independent, so $(X',Y')=(\mu+(X'-\mu),\,A(X'-\mu)+W')$): both are the same affine image of a pair of independent $\mathcal N(0,\Sigma_0)$ and $\mathcal N(0,D)$ vectors.

For a jointly Gaussian pair, the conditional covariance is the deterministic generalized Schur complement $\Sigma_{I_0I_0}-\operatorname{Cov}(T_{I_0},Y)\operatorname{Cov}(Y)^+\operatorname{Cov}(Y,T_{I_0})$, and the canonical regular conditional law of $T_{I_0}$ given $Y=y$ is $\mathcal N\bigl(\theta_{I_0}+\operatorname{Cov}(T_{I_0},Y)\operatorname{Cov}(Y)^+(y-\mathbb EY),\,Q\bigr)$. Both are functions of the joint law of $(T_{I_0},Y)$ alone. Since that joint law is the lemma's, the matrix $Q=\operatorname{Cov}(T_{I_0}\mid Y)$ in the steering lemma's pseudo-inverse form is the lemma's $Q=\operatorname{Cov}(X\mid Y)$, and by property 1 of the lemma
$$
Q_{ij}\le0\quad\text{whenever $i,j$ lie in distinct clusters of }\mathcal C.
$$
Likewise, for every cluster $c$ and $t\in(0,q]$, the function $y\mapsto\mathbb P(\min_{i\in c}p_i\le t\mid Y=y)$, with $p_i=\overline\Phi(T_i)$, is the same function as $y\mapsto\mathbb P(\min_{i\in c}P_i\le t\mid Y=y)$ in the lemma, because $\min_{i\in c}\overline\Phi(\cdot)$ is a fixed measurable map applied to the same canonical conditional law. Hence the lemma's intensity, written on our space as
$$
K_0(Y)=\max\Bigl\{1,\ \sup_{t\in(0,q]\cap(\mathbb Q\cup\{q\})}\frac1{N_0t}\sum_{c\in\mathcal C}|c|\,\mathbb P\Bigl(\min_{i\in c}p_i\le t\Bigm|Y\Bigr)\Bigr\},
$$
is the same measurable function of $Y$ as in the lemma, and $Y$ has the same law there. Property 2 gives
$$
\mathbb E\min\{1,qK_0(Y)\}\le C_3q\sqrt{\log(1/q)} .
$$
The carrier is built from null coordinates and independent noise only.

**Step 4 (steering).** The steering lemma applies: $(N,\theta,\Sigma)$ is admissible with $I_0\ne\varnothing$; $0<q\le q_2$; $Y\in\mathbb R^m$ ($m\ge0$) lives on an extension and $(T,Y)$ is jointly Gaussian (Step 3); $\mathcal C$ is a partition of $I_0$ into nonempty clusters satisfying the sign-split condition for $Q=\operatorname{Cov}(T_{I_0}\mid Y)$ (Step 3). Its intensity is, for $0<t\le q$,
$$
\Gamma(t;Y)=\frac1{Nt}\sum_{c\in\mathcal C}|c|\,\mathbb P\Bigl(\min_{i\in c}p_i\le t\Bigm|Y\Bigr)=\frac{N_0}{N}\,\Gamma_0(t;Y)\le\Gamma_0(t;Y),
$$
where $\Gamma_0$ is the expression inside the supremum defining $K_0$; the inequality uses $\Gamma_0\ge0$ and $N_0\le N$. Both suprema run over the same set $(0,q]\cap(\mathbb Q\cup\{q\})$, so $K(Y)\le K_0(Y)$ (as extended reals), and therefore $\min\{1,qK(Y)\}\le\min\{1,qK_0(Y)\}$ pointwise. The steering lemma and Step 3 give
$$
\mathbb E\bigl[\mathrm{FDP}\,\mathbf 1_{E_0^c}\bigr]\le C_2q+C_2\,\mathbb E\min\{1,qK(Y)\}\le C_2q+C_2C_3\,q\sqrt{\log(1/q)} .
$$
Here FDP, $E_0$, $I_0$ and the BH procedure are the original ones; the steering lemma alters none of them.

**Step 5 (assembly).** By Steps 1, 2 and 4,
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le(C_S+C_2)q+C_2C_3\,q\sqrt{\log(1/q)}\le A_1q\bigl[1+\sqrt{\log(1/q)}\bigr],
$$
also trivially when $I_0=\varnothing$. The constants $C_S,C_2,C_3,q_*$ do not depend on $N,\theta,\Sigma$, the null proportion, rank, or on the carrier and partition chosen (which may depend on the model and $q$, as both lemmas allow). Taking the supremum over all finite models at the fixed level $q$ gives $F_1(q)\le A_1q[1+\sqrt{\log(1/q)}]$ for every $0<q\le q_*$. This is the sufficient finite-level conclusion of the target's acceptance criterion with $\widetilde q_{0,1}=q_*\in(0,1)$; by the target's own conversion, $C_1=2A_1$ and $q_{0,1}=\min\{q_*,e^{-1}\}$ give $F_1(q)\le C_1q\sqrt{\log(1/q)}$ for $0<q\le q_{0,1}$, since $1\le\sqrt{\log(1/q)}$ there. $\square$

Remainder accounting: $(\mathrm R_1)$ is paid by the linear Simes bound, $(\mathrm R_2)$ by the steering lemma and $(\mathrm R_3)$ by the positive-carrier lemma; nothing else is left over.

## Reduction verdict

confirmed

Checked as written, with the three route lemmas used only by their statements; none of the target's listed dependencies is used.

1. Split (Step 1). The case $I_0=\varnothing$ gives $V\equiv0$. For $N_0\ge1$, $\alpha=qN_0/N\in(0,q]$. The event $E_0$ is word for word the steering lemma's event. The bound $\mathrm{FDP}\le\mathbf 1_{E_0}+\mathrm{FDP}\,\mathbf 1_{E_0^c}$ uses only $0\le\mathrm{FDP}\le1$. Moving to a product extension changes no expectation of a function of $T$.
2. Containment in the centred Simes event (Step 2). A witness $k$ must satisfy $k\le N_0$, because the null count is at most $N_0$. For $k\le N_0$, "count $\ge k$" is equivalent to $p_{0,(k)}\le qk/N$, and $qk/N=\alpha k/N_0$ exactly. Monotonicity goes the right way: $\theta_i\le0$ and $\overline\Phi$ decreasing give $p_i=\overline\Phi(\theta_i+X_i)\ge\overline\Phi(X_i)=\widetilde p_i$. Counts $\#\{p_i\le s\}$ are nonincreasing in each $p_i$, so $E_0\subseteq\widetilde E_0$. The linear Simes bound's hypotheses all hold: dimension $N_0\ge1$; $\Sigma_{I_0I_0}\in\mathcal C_{N_0}$ (a principal submatrix of a PSD unit-diagonal matrix, singular allowed); centred law $X\sim\mathcal N_{N_0}(0,\Sigma_{I_0I_0})$; level $0<\alpha\le q\le q_0$; non-strict comparisons with multiplicities. The lemma's event is $\widetilde E_0$ exactly, so $\mathbb P(E_0)\le C\alpha\le Cq$.
3. Carrier (Step 3). The positive-carrier lemma's hypotheses hold with $n=N_0$, $\mu=\theta_{I_0}\in(-\infty,0]^{N_0}$, $\Sigma_0=\Sigma_{I_0I_0}$ and $q\le q_3$. It supplies $(m,A,D,\mathcal C)$ for every such input, so a carrier exists for every model, not only some. $(T_{I_0},Y)=(\mu+X,AX+W)$, with $W$ independent of all of $T$, has the lemma's joint law. The conditional covariance (generalized Schur complement) and the canonical regular conditional law are functionals of that joint law. So the steering lemma's $Q=\operatorname{Cov}(T_{I_0}\mid Y)$ equals the lemma's $Q$, and property 1 gives the sign-split condition. Likewise $K_0(Y)$ is the lemma's intensity, with the same normalisation $1/(nt)=1/(N_0t)$ and the same index set of $t$. Property 2 gives $\mathbb E\min\{1,qK_0\}\le C_3q\sqrt{\log(1/q)}$.
4. Steering (Step 4). The steering lemma's hypotheses hold. The model is admissible with $I_0\ne\varnothing$, and $q\le q_2$. $Y$ lives on an extension. $(T,Y)$ is jointly Gaussian, as an affine image of the independent Gaussian pair $(T,W)$. $\mathcal C$ partitions $I_0$ into nonempty clusters and satisfies the sign-split condition for the pseudo-inverse $Q$. The steering lemma is stated for every carrier and partition meeting that condition, with constants independent of them, so the model- and $q$-dependent choice from Step 3 is allowed. Its $\Gamma(t;Y)=(N_0/N)\Gamma_0(t;Y)\le\Gamma_0(t;Y)$ is the only normalisation difference, and the suprema run over the same set. Hence $K\le K_0$, also as extended reals with $\min\{1,q\cdot\infty\}=1$, and $\mathbb E[\mathrm{FDP}\,\mathbf 1_{E_0^c}]\le C_2q+C_2C_3q\sqrt{\log(1/q)}$.
5. Constants and levels (Step 5). $q_*=\min\{q_0,q_2,q_3\}\in(0,1)$ makes all three lemmas applicable at every $0<q\le q_*$. The bound $(C_S+C_2)q+C_2C_3q\sqrt{\log(1/q)}\le A_1q[1+\sqrt{\log(1/q)}]$ holds with $A_1=\max\{C_S+C_2,C_2C_3\}$. All constants are universal, and the supremum is taken at fixed $q$. This is the target's sufficient finite-level criterion. The conversion with $C_1=2A_1$ and $q_{0,1}=\min\{q_*,e^{-1}\}$ is the target's own.

Minor, not affecting validity: the labels $(\mathrm R_1)$-$(\mathrm R_3)$ in the closing remainder line are defined in the plan's Goal section, not in the Reduction. The reduction is sound; all the mathematical weight sits in the three lemmas. Their own motivations flag the steering lemma as containing the open class-E conjecture (constant $Y$, singleton clusters, independent nulls), and multiscale positive structures as the main risk for the positive-carrier lemma.
