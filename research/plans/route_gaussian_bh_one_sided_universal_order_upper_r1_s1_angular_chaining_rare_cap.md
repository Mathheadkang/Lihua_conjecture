---
type: plan
title: >-
  Universal one-sided order via angular clusters, a rare-direction cap and the
  Gaussian width of few centres
status: pending
target_asset: gaussian_bh_one_sided_universal_order_upper
route_lemmas:
  - gaussian_bh_angular_cluster_entropy_bound
  - gaussian_bh_rare_direction_cap
  - gaussian_bh_heavy_cluster_gaussian_width_bound
route_title: 'via angular clusters, rare cap and chaining'
origin: researcher
inspired_by:
  - idea_2251f0ebf933
  - idea_1147e4ead925
  - idea_c5bacf260246
  - idea_75d71c7756b4
tags:
  - parallel-round-20261112
  - route-1
route_round: 1
reduction_digest: f7f094e6864d2c73803ada47f89bf4382372a3786be6375fb89754bfb62f74bc
reduction_inputs:
  gaussian_bh_one_sided_universal_order_upper: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
  gaussian_bh_fractional_frame_surface_kernel: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
  gaussian_bh_conditional_compound_calibration: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
  gaussian_bh_negative_null_boundary_strip: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
  gaussian_bh_conditional_subpoisson_calibration: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
  gaussian_bh_angular_cluster_entropy_bound: c0f4a35d70bb8c3321136accd04202b71bb70ae9a12fd0aaa5c3d48abe6e1b98
  gaussian_bh_rare_direction_cap: 9afb59906629533a14999f6caaf3ad9532b3838891de891a2f9d6b5299480a12
  gaussian_bh_heavy_cluster_gaussian_width_bound: 3e13e3d00c2dbbf6978ff6a3123305f6478a95bf232bc1dd375809f3564c207b
reduction_verified_digest: f7f094e6864d2c73803ada47f89bf4382372a3786be6375fb89754bfb62f74bc
reduction_checked: true
---

## Goal

Target: [gaussian_bh_one_sided_universal_order_upper](../assets/gaussian_bh_one_sided_universal_order_upper.md)

Prove the unchanged statement: finite universal $C_1$ and $q_{0,1}$ with $F_1(q)\le C_1q\sqrt{\log(1/q)}$ for $0<q\le q_{0,1}$, uniformly over all finite $N$, all means, all unit-diagonal PSD $\Sigma$ (singular included), with the original labels $I_0=\{i:\theta_i\le0\}$ and ordinary BH at its largest qualifying rank. This works out the researcher's route [Route 1: directional entropy to multi-scale chaining with a rare-cluster cap](../ideas/idea_2251f0ebf933.md): group null directions at angular scale about $1/u$, cap rare clusters through competition at the single BH cutoff, get a dimension-free $q\log(1/q)$ milestone, then use chaining (the Gaussian width of the at most $q^{-C}$ heavy centres) to reach $q\sqrt{\log(1/q)}$.

External Gaussian inputs: (a) angular stability. A null whose direction has cosine $\rho\ge1/2$ with a cluster centre $v$ has its own standard projection correlated $\rho$ with $Y=v^{\mathsf T}Z$. Truncating at $\{Y\le\beta\}$ instead of at its own projection costs only an additive $A_1(\kappa)$ in the Mills strip integral when $\beta\sqrt{1-\rho^2}\le\kappa$. (b) Generic chaining and the majorizing-measure theorem: the mean width $\mathbb E\max_jv_j^{\mathsf T}Z\asymp\gamma_2(\{v_j\})$ and is at most $\sqrt{2\log J}$. (c) Competition through the single BH cutoff, for the rare cap.

Planning-time check of where the approved [directional-entropy bound](../assets/directional_entropy_one_sided_fdr_bound.md) uses "same ray": only in using the group projection $Y_h$ both as the argument of each null's conditional ratio $M_i$ and as the truncation variable $\{Y_h\le b_h\}$. The leave-one-out step conditions on the full $Z$ and is direction-free. Lemma L1 replaces that one step by the correlation computation in (a).

## Route

- gaussian_bh_angular_cluster_entropy_bound (L1): the entropy bound for clusters of angular radius $\kappa/\beta_j$ with free truncation levels; gives the $q\log(1/q)$ milestone in step 5 and is the base case that L3 refines.
- gaussian_bh_rare_direction_cap (L2): bounds the total contribution of nulls whose $\kappa_2/u$-angular neighbourhood has null mass below $q^{C_2}$ by $A_2q(1+u)$ (step 3).
- gaussian_bh_heavy_cluster_gaussian_width_bound (L3): bounds the contribution of at most $q^{-C}$ angular clusters by $A_3q(1+u+\text{mean width of centres})$ (step 6).

## Plan

1. [x] Representation. For a given $(N,\theta,\Sigma)$ choose $\delta\in[0,1]^N$ maximizing $\sum_i\delta_i$ subject to $\Sigma-\operatorname{diag}(\delta)\succeq0$ (a compact nonempty feasible set, so a maximizer exists). Let $a_i$ be the $i$-th row of $(\Sigma-\operatorname{diag}\delta)^{1/2}$, $d=N$. Then $\|a_i\|^2=1-\delta_i\le1$ and $\Sigma(A)=\Sigma$, so this is a [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) of the same law, with the same p-values, labels and BH output in distribution. Any other representation would also serve, since L1--L3 hold for all representations. This choice makes the independent case $\Sigma=I$ have all $r_i=0$, so no null is rare there.
2. [x] Constants. Take $\kappa_2,C_2,A_2,q_2$ from L2, put $\kappa=2\kappa_2$, $C=C_2$, and take $A_3,q_3$ from L3 at $(\kappa,C)$. Choose a universal $q_0\le\min\{q_2,q_3,\overline\Phi(1),e^{-1}\}$ so small that, for $q\le q_0$, $2\kappa_2/u\le\pi/3$ and $u\ge\sqrt{\log(1/q)}$. The latter holds for small $q$ by the Mills lower bound $\overline\Phi(x)\ge x\phi(x)/(1+x^2)$.
3. [x] Rare part. Split $I_0=I_{\mathrm{rare}}\sqcup I_{\mathrm{hv}}$ with $I_{\mathrm{rare}}$ as in L2 for this representation. Since $V/(R\vee1)$ is additive over this split, L2 gives $\mathbb E[|\mathcal R_q\cap I_{\mathrm{rare}}|/(R\vee1)]\le A_2q(1+u)$.
4. [x] Covering of heavy directions. Let $H^+=\{i\in I_{\mathrm{hv}}:r_i>0\}$, so $\mu_i\ge q^{C_2}$ on $H^+$. Pick a maximal subset $c_1,\ldots,c_J\in H^+$ whose directions $w_{c_j}$ have pairwise angles $>2\kappa_2/u$. By the triangle inequality for angles, the caps $B_j=\{k\in I_0:r_k>0,\angle(w_k,w_{c_j})\le\kappa_2/u\}$ are pairwise disjoint, and $|B_j|/m=\mu_{c_j}\ge q^{C_2}$, hence $J\le q^{-C_2}$. By maximality every $i\in H^+$ is within angle $2\kappa_2/u$ of some $w_{c_j}$. Assign it to the least such $j$, and put the nulls of $I_{\mathrm{hv}}$ with $r_i=0$ into $C_1$. If $H^+=\varnothing$ but $I_{\mathrm{hv}}\ne\varnothing$, use $J=1$ with an arbitrary unit $v_1$; if $I_{\mathrm{hv}}=\varnothing$, the heavy contribution is $0$. With $v_j=w_{c_j}$, every member with $r_i>0$ has $a_i^{\mathsf T}v_j=r_i\cos\angle(w_i,v_j)\ge r_i\cos(2\kappa_2/u)$, because the angle is at most $2\kappa_2/u\le\pi/3$.
5. [x] Milestone (researcher-requested; the target does not use it). Apply L1 to the clusters of step 4 with $\beta_j=\overline\Phi^{-1}(q\max\{\pi_j,q^{C_2}\})\ge u$. Then $\rho_i\ge\cos(2\kappa_2/u)\ge1/2$, and $\beta_j\sqrt{1-\rho_i^2}\le\sqrt{2(1+C_2)\log(1/q)}\cdot2\kappa_2/u\le2\kappa_2\sqrt{2(1+C_2)}=:\kappa_1$. Hence the heavy contribution is at most $q[\tfrac32+A_1(\kappa_1)+\sum_j\pi_j\log(1/\pi_j)]+q\sum_j(\pi_j+q^{C_2})$. Using $\sum_j\pi_j\log(1/\pi_j)\le\log J+1/e$ and $J\le q^{-C_2}$, it is at most $q[4+A_1(\kappa_1)+C_2\log(1/q)]$, plus the $\gamma$-term $qu/\sqrt{2\pi}$. With step 3 this gives the dimension-free bound $\mathrm{FDR}\le A q(1+\log(1/q))$.
6. [x] Heavy part via L3. The partition of step 4 satisfies the hypotheses of L3 at $(\kappa,C)=(2\kappa_2,C_2)$, since $J\le q^{-C_2}$ and the angle condition holds. Thus the heavy contribution is at most $A_3q(1+u+\mathbb E\max_jv_j^{\mathsf T}Z)\le A_3q(1+u+\sqrt{2\log J})\le A_3q(1+u+\sqrt{2C_2\log(1/q)})$, using the standard bound $\mathbb E\max_{j\le J}G_j\le\sqrt{2\log J}$ for standard normals ($=0$ when $J=1$).
7. [x] Conclusion. By Chernoff, $u\le\sqrt{2\log(1/q)}$, as in the approved entropy proof. Adding steps 3 and 6 gives $\mathrm{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)\le A'q[1+\sqrt{\log(1/q)}]$ for all models and all $0<q\le q_0$, with $A'=A_2(1+\sqrt2)+A_3(1+\sqrt2+\sqrt{2C_2})$. The target's acceptance criterion then gives $q_{0,1}=\min\{q_0,e^{-1}\}$ and $C_1=2A'$.

## Verification

Steps 1--4 are exact constructions on the original model: the same law, the same labels, the same full BH procedure; no coordinate is removed, recentred or relabelled. The FDP is split additively into rare and heavy null contributions with the actual denominator $R\vee1$. Step 3 is L2 verbatim. Step 6 is L3 verbatim once step 4 checks $J\le q^{-C_2}$ (disjoint caps of mass $\ge q^{C_2}$) and the angle condition. Step 7 is arithmetic. All constants come from L2 and L3 and from the universal choice of $q_0$, so nothing depends on $N$, $d$, the means, $\Sigma$, its rank or the null proportion, and every parameter may vary with $q$. Singular $\Sigma$ is handled by the representation itself (no inverse is taken). Step 5 is a checkpoint only.

Remainders, stated before execution, and saturation check. The whole unproved content sits in L2 and L3, and each must be proved as an independent inequality, never through an identity returning the FDR.
- L3's remainder is the explicit charge $A_3q(1+u+\text{width})$. In the zero-mean independent case ($\Sigma=I$, step 1 gives all $r_i=0$, $J=1$) it equals $A_3q(1+u)$, not the FDR.
- L2 is vacuous in that case. With a rank-deficient high-dimensional spread of null directions, L2 carries the whole problem at angular scales $\gg\kappa_2/u$. This is the route's main risk.

First tests:
- L1: the Mills strip computation $\int_\beta^\infty h(s)\Phi((\beta-\rho s)/\sqrt{1-\rho^2})\,ds\le A_1(\kappa)$ for $\beta\sqrt{1-\rho^2}\le\kappa$, $\rho\ge1/2$, where $h=\phi/\overline\Phi$.
- L2 (the researcher's failure criterion): a family with many null clusters at angle about $1/u$, each of mass below $q^{C}$, with $\mathrm{FDR}/(q\log(1/q))$ unbounded, refutes L2. Probe copies of the one-null staircase [idea_75d71c7756b4](../ideas/idea_75d71c7756b4.md) on nearly orthogonal factors, and a densely filled cap of radius $10\kappa_2/u$ in high dimension.
- L3: $J=q^{-C}$ orthogonal equal clusters of unit-loading zero-mean nulls with staircase alternatives. The leader-tracking calculation of [idea_c5bacf260246](../ideas/idea_c5bacf260246.md) predicts a total tilt of order $u$, within the claimed charge.

## Difference from failed plans

- plan_252211621cea: no signed Stein occupation or pairing of path endpoints; the bound is an inequality from conditional leave-one-out ratios, angular truncation and Gaussian width, so there is no switch sum that integrates back to the FDR.
- plan_503f8fddcbb5: no global shift or record partition and no entrant allocation; dimension enters only through the covering number of heavy directions, which is capped by mass.
- plan_ee2f7b97740a: no rank-chain transport or Hall-cut certificate; the "chain" here is a chaining tree on the sphere of null directions, not on BH ranks.
- plan_one_sided_order_actual_mean_global_flux_20261106: no counting of critical crossings or positive flux; maximal-rank events are never enumerated.
- plan_one_sided_order_common_anchor_rotation_20261107: no rotation interpolation and no signed facet flux, so no (P23)-type remainder; the external inputs are angular stability and the majorizing-measure width.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: no convex proxy, PAVA masks or activation flux; BH is used only through the approved leave-one-out identity and the two route lemmas.
- plan_one_sided_order_fdp_entropy_mills_coherence_20261107: that plan's failed certificate charged the trace at $O(q)$ against coherence. Here the charge is $q(1+u+\text{width})$, which already allows the $c_0qu$ low-coherence counterfamily, and entropy is directional (masses of null directions), not FDP-tilt entropy.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no covariance interpolation or diagonal completion of a boundary matrix, hence no $N^2$ completion charge.
- plan_one_sided_order_three_face_noise_packing_20261106: no contact/Gram budget maximized over an independent $Q$. Covariance enters only through angles between actual null loadings, so the $\rho\downarrow0$ equicorrelation obstruction is charged by the width of one centre (zero), not by $1/\rho$.
- plan_one_sided_order_mixed_trace_replica_cells_20261108: no convex-cell replicas or cross-face comparisons.
- plan_one_sided_order_negative_contact_transport_20261106: no negative-covariance contact transport or inverse-noise diagonal charges.
- plan_one_sided_order_peeling_history_kernel_20261107: no peeling histories or summation by parts that terminates at the FDR; the rare cap L2 must be an independent inequality.

## Reduction

The lemmas [gaussian_bh_rare_direction_cap](../assets/gaussian_bh_rare_direction_cap.md) (L2), [gaussian_bh_heavy_cluster_gaussian_width_bound](../assets/gaussian_bh_heavy_cluster_gaussian_width_bound.md) (L3) and, for the milestone only, [gaussian_bh_angular_cluster_entropy_bound](../assets/gaussian_bh_angular_cluster_entropy_bound.md) (L1) are used as black boxes through their statements. The target uses only L2 and L3.

Notation. For unit vectors $x,y$ write $\angle(x,y)=\arccos(x^{\mathsf T}y)\in[0,\pi]$; this is the geodesic metric on the unit sphere, so it satisfies the triangle inequality, and for $0\le t\le\pi$ one has $x^{\mathsf T}y\ge\cos t$ if and only if $\angle(x,y)\le t$, because $\cos$ is strictly decreasing on $[0,\pi]$.

Two Gaussian tail facts. (G1) Chernoff: $\overline\Phi(t)\le e^{-t^2/2}$ for $t\ge0$. Hence if $0<x\le1/2$ then $t=\overline\Phi^{-1}(x)\ge0$ and $x=\overline\Phi(t)\le e^{-t^2/2}$, i.e. $\overline\Phi^{-1}(x)\le\sqrt{2\log(1/x)}$. (G2) Mills lower bound: $\overline\Phi(t)\ge t\phi(t)/(1+t^2)$ for $t>0$. Put $s=\sqrt{\log(1/q)}$. Then $\overline\Phi(s)\ge q^{1/2}\,s/((1+s^2)\sqrt{2\pi})$, and $\overline\Phi(s)\ge q$ is equivalent to $g(s):=s e^{s^2/2}/(1+s^2)\ge\sqrt{2\pi}$. Since $(\log g)'(s)=1/s+s-2s/(1+s^2)\ge1/s+s-1>0$, $g$ is increasing, and $g(3)=3e^{9/2}/10>27>\sqrt{2\pi}$. So for $q\le e^{-9}$ (that is $s\ge3$), $\overline\Phi(s)\ge q=\overline\Phi(u)$ and therefore $u\ge s=\sqrt{\log(1/q)}$.

**Step 1 (representation).** Fix an admissible model $(N,\theta,\Sigma)$ and $q$. The set $\mathcal D=\{\delta\in[0,1]^N:\Sigma-\operatorname{diag}\delta\succeq0\}$ contains $0$ and is closed (the PSD cone is closed) and bounded, so $\delta\mapsto\sum_i\delta_i$ attains its maximum at some $\delta\in\mathcal D$. (Any $\delta\in\mathcal D$, e.g. $\delta=0$, would serve below; the maximizer is the plan's choice.) Let $A=(\Sigma-\operatorname{diag}\delta)^{1/2}$ (the PSD square root, $d=N$) with rows $a_i^{\mathsf T}$. Then $AA^{\mathsf T}=\Sigma-\operatorname{diag}\delta$, so $\|a_i\|^2=\Sigma_{ii}-\delta_i=1-\delta_i\in[0,1]$ and $a_i^{\mathsf T}a_k=\Sigma_{ik}$ for $i\ne k$. Hence $\Sigma(A)=AA^{\mathsf T}+\operatorname{diag}(1-\|a_i\|^2)=\Sigma-\operatorname{diag}\delta+\operatorname{diag}\delta=\Sigma$, and $T_i=\theta_i+a_i^{\mathsf T}Z+\sqrt{1-\|a_i\|^2}\varepsilon_i$ ($m=N$) is a [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) whose law is $\mathcal N_N(\theta,\Sigma)$. The p-values $p_i=\overline\Phi(T_i)$ are a fixed function of $T$, ordinary BH is a deterministic function of $p$ and $q$, and $I_0=\{i:\theta_i\le0\}$ depends only on $\theta$. Therefore $(\mathcal R_q,R,V)$ has the same law under the representation as in the original model, and
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)=\mathbb E\!\left[\frac{|\mathcal R_q\cap I_0|}{R\vee1}\right]
$$
computed in the representation, with the same labels, the same full procedure and the same denominator. No square root of an inverse is taken, so singular $\Sigma$ is included. Below $r_i=\|a_i\|$, $\gamma_i$ are the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md) of this representation, and $w_i=a_i/r_i$ when $r_i>0$.

**Step 2 (constants).** L2 supplies universal $\kappa_2>0$, $C_2\ge1$, $A_2<\infty$, $q_2\in(0,1/2)$. Put $\kappa=2\kappa_2>0$ and $C=C_2\ge1$; L3 at $(\kappa,C)$ supplies $A_3=A_3(2\kappa_2,C_2)$ and $q_3\in(0,1/2)$, again universal since $\kappa_2,C_2$ are. Define
$$
q_0=\min\bigl\{q_2,\ q_3,\ \overline\Phi(\max\{1,6\kappa_2/\pi\}),\ e^{-9}\bigr\}\in(0,1/2).
$$
For $0<q\le q_0$: $q<1/2$, so $u=\overline\Phi^{-1}(q)>0$; $u\ge\max\{1,6\kappa_2/\pi\}$ by monotonicity of $\overline\Phi$, so $2\kappa_2/u\le\pi/3$; $u\ge\sqrt{\log(1/q)}$ by (G2); $u\le\sqrt{2\log(1/q)}$ by (G1). Fix such a $q$ from now on.

**Step 3 (rare part).** Let $I_{\mathrm{rare}}=\{i\in I_0:r_i>0,\ \mu_i<q^{C_2}\}$ with $\mu_i$ exactly as in L2 for this representation (scale $\kappa_2/u$, normalization $1/m=1/N$), and $I_{\mathrm{hv}}=I_0\setminus I_{\mathrm{rare}}$. Since $|\mathcal R_q\cap I_0|=|\mathcal R_q\cap I_{\mathrm{rare}}|+|\mathcal R_q\cap I_{\mathrm{hv}}|$ pointwise and the denominator $R\vee1$ is common,
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}=\mathbb E\!\left[\frac{|\mathcal R_q\cap I_{\mathrm{rare}}|}{R\vee1}\right]+\mathbb E\!\left[\frac{|\mathcal R_q\cap I_{\mathrm{hv}}|}{R\vee1}\right].
$$
All hypotheses of L2 hold (a multifactor representation, any $d$, means and loadings; $0<q\le q_2$; the same ordinary BH), so the first term is at most $A_2q(1+u)$.

**Step 4 (covering of heavy directions).** If $I_{\mathrm{hv}}=\varnothing$ the second term is $0$; skip to Step 7 with heavy contribution $0$. Otherwise note $I_{\mathrm{hv}}=\{i\in I_0:r_i=0\}\sqcup H^+$ with $H^+=\{i\in I_0:r_i>0,\ \mu_i\ge q^{C_2}\}$.

Case $H^+=\varnothing$: put $J=1$, $C_1=I_{\mathrm{hv}}$ (nonempty, all members have $r_i=0$), and $v_1$ any unit vector of $\mathbb R^d$ ($d=N\ge1$).

Case $H^+\ne\varnothing$: put $\tau=\kappa_2/u\in(0,\pi/6]$. Since $H^+$ is finite, choose (greedily) a maximal subset $\{c_1,\ldots,c_J\}\subseteq H^+$ with $\angle(w_{c_j},w_{c_l})>2\tau$ for $j\ne l$; $J\ge1$. Let $B_j=\{k\in I_0:r_k>0,\ \angle(w_k,w_{c_j})\le\tau\}$. As $\tau\le\pi$, $w_k^{\mathsf T}w_{c_j}\ge\cos\tau$ iff $\angle(w_k,w_{c_j})\le\tau$, so $|B_j|/m=\mu_{c_j}\ge q^{C_2}$ because $c_j\in H^+$. If $k\in B_j\cap B_l$ with $j\ne l$, the triangle inequality gives $\angle(w_{c_j},w_{c_l})\le2\tau$, a contradiction; so the $B_j$ are pairwise disjoint subsets of $I_0$ and $Jq^{C_2}\le\sum_j|B_j|/m\le1$, i.e.
$$
J\le q^{-C_2}.
$$
By maximality, every $i\in H^+$ has $\angle(w_i,w_{c_j})\le2\tau$ for some $j$ (otherwise $i$ could be added). Assign $i$ to the least such $j$; let $C_j$ be the set of $i\in H^+$ assigned to $j$, and add all $i\in I_{\mathrm{hv}}$ with $r_i=0$ to $C_1$. The $C_j$ partition $I_{\mathrm{hv}}$. Each $C_j$ is nonempty: $c_j$ is at angle $0\le2\tau$ from $w_{c_j}$ and at angle $>2\tau$ from every other centre, so $c_j\in C_j$. Put $v_j=w_{c_j}$. For $i\in C_j$ with $r_i>0$ we have $\angle(w_i,v_j)\le2\tau=2\kappa_2/u\le\pi/3$, hence
$$
a_i^{\mathsf T}v_j=r_i\cos\angle(w_i,v_j)\ge r_i\cos(2\kappa_2/u)\ge r_i/2 .
$$
In both cases $J\le q^{-C_2}$ (in the first $J=1\le q^{-C_2}$), the $C_j$ are nonempty and partition $I_{\mathrm{hv}}$, the $v_j$ are unit vectors, and every member with $r_i>0$ satisfies $a_i^{\mathsf T}v_j\ge r_i\cos(2\kappa_2/u)$.

**Step 5 (milestone; not used by the target).** Take $I_*=I_{\mathrm{hv}}\neq\varnothing$ with the partition of Step 4, $\pi_j=|C_j|/m$, and $\beta_j=\overline\Phi^{-1}(x_j)$ with $x_j=q\max\{\pi_j,q^{C_2}\}\in[q^{1+C_2},q]$. Then $\beta_j\ge u$ since $x_j\le q$. For $i\in C_j$ with $r_i>0$, $\rho_i=a_i^{\mathsf T}v_j/r_i=\cos\angle(w_i,v_j)\ge\cos(2\kappa_2/u)\ge1/2$ and $\sqrt{1-\rho_i^2}=\sin\angle(w_i,v_j)\le\angle(w_i,v_j)\le2\kappa_2/u$. By (G1), $\beta_j\le\sqrt{2\log(1/x_j)}\le\sqrt{2(1+C_2)\log(1/q)}$, and with $u\ge\sqrt{\log(1/q)}$,
$$
\beta_j\sqrt{1-\rho_i^2}\le\sqrt{2(1+C_2)\log(1/q)}\cdot\frac{2\kappa_2}{u}\le2\kappa_2\sqrt{2(1+C_2)}=:\kappa_1 .
$$
So L1 applies at $\kappa_1$ (with $q<1/2$). Its right side is bounded as follows: $\overline\Phi(\beta_j)=x_j$, so $\log(q/\overline\Phi(\beta_j))=\log(1/\max\{\pi_j,q^{C_2}\})\le\log(1/\pi_j)$; $\sum_j\pi_j=:\sigma\le1$ and $\sum_j\pi_j\log(1/\pi_j)\le\sigma\log(J/\sigma)\le\log J+1/e$ (Jensen for the concave $\log$, and $\sigma\log(1/\sigma)\le1/e$); $\sum_jx_j\le q\sum_j(\pi_j+q^{C_2})\le q(1+Jq^{C_2})\le2q$; $\gamma_i\le1$. With $\log J\le C_2\log(1/q)$,
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap I_{\mathrm{hv}}|}{R\vee1}\right]\le q\Bigl[\tfrac32+A_1(\kappa_1)+C_2\log\tfrac1q+\tfrac1e+2\Bigr]+\frac{qu}{\sqrt{2\pi}}\le q\Bigl[4+A_1(\kappa_1)+C_2\log\tfrac1q\Bigr]+\frac{qu}{\sqrt{2\pi}} .
$$
Adding Step 3 and using $u\le\sqrt{2\log(1/q)}\le1+\log(1/q)$ gives $\operatorname{FDR}^{(1)}_{\mathrm{BH}}\le Aq(1+\log(1/q))$ with $A=2A_2+1+4+A_1(\kappa_1)+C_2$, universal. This checkpoint is recorded only; the target does not use it.

**Step 6 (heavy part via L3).** If $I_{\mathrm{hv}}\ne\varnothing$, apply L3 at $(\kappa,C)=(2\kappa_2,C_2)$ with $I_*=I_{\mathrm{hv}}$ and the partition and unit vectors of Step 4: $0<q\le q_3$, $J\le q^{-C}$, the $C_j$ are nonempty, and $a_i^{\mathsf T}v_j\ge r_i\cos(\kappa/u)$ for every member with $r_i>0$; members with $r_i=0$ need nothing. Hence
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap I_{\mathrm{hv}}|}{R\vee1}\right]\le A_3q\Bigl(1+u+\mathbb E\max_{j\le J}v_j^{\mathsf T}Z\Bigr).
$$
Each $G_j=v_j^{\mathsf T}Z$ is standard normal ($\|v_j\|=1$). If $J=1$, $\mathbb E\max_jG_j=0$. If $J\ge2$, for $\lambda>0$ Jensen gives $e^{\lambda\mathbb E\max G_j}\le\mathbb E e^{\lambda\max G_j}\le\sum_j\mathbb Ee^{\lambda G_j}=Je^{\lambda^2/2}$, so $\mathbb E\max G_j\le\log J/\lambda+\lambda/2$; $\lambda=\sqrt{2\log J}$ gives $\mathbb E\max_jG_j\le\sqrt{2\log J}\le\sqrt{2C_2\log(1/q)}$. Thus the heavy contribution is at most $A_3q(1+u+\sqrt{2C_2\log(1/q)})$, and this bound also holds trivially when $I_{\mathrm{hv}}=\varnothing$.

**Step 7 (conclusion).** By Steps 3 and 6 and $u\le\sqrt{2\log(1/q)}$, for every admissible $(N,\theta,\Sigma)$ and every $0<q\le q_0$,
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le A_2q(1+\sqrt2\,\ell)+A_3q(1+\sqrt2\,\ell+\sqrt{2C_2}\,\ell)\le A'q(1+\ell),\qquad \ell=\sqrt{\log(1/q)},
$$
with $A'=A_2(1+\sqrt2)+A_3(1+\sqrt2+\sqrt{2C_2})$. $A'$ and $q_0$ depend only on the universal constants of L2 and L3, not on $N$, $d$, $\theta$, $\Sigma$, its rank, the null proportion or any other model parameter, and every model parameter may depend on $q$. Taking the supremum, $F_1(q)\le A'q[1+\sqrt{\log(1/q)}]$ for $0<q\le q_0$. This is the target's sufficient finite-level conclusion with $A_1=A'$ and $\widetilde q_{0,1}=q_0$: for $q\le q_{0,1}=\min\{q_0,e^{-1}\}$ we have $\log(1/q)\ge1$, so $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$ and $F_1(q)\le C_1q\sqrt{\log(1/q)}$ with $C_1=2A'$. Remainder: none beyond the explicit charges of L2 and L3; no term equal to the FDR appears. $\blacksquare$

## Reduction verdict

confirmed

Checked as written against the statements of L2 ([gaussian_bh_rare_direction_cap](../assets/gaussian_bh_rare_direction_cap.md)) and L3 ([gaussian_bh_heavy_cluster_gaussian_width_bound](../assets/gaussian_bh_heavy_cluster_gaussian_width_bound.md)) only, used as black boxes. L1 enters only the recorded milestone (Step 5), which the target does not use.

1. Re-representation (Step 1). $\mathcal D$ is nonempty, closed and bounded, so the maximizer exists; any $\delta\in\mathcal D$ would do. $A=(\Sigma-\operatorname{diag}\delta)^{1/2}$ is symmetric, so $AA^{\mathsf T}=\Sigma-\operatorname{diag}\delta$, $\|a_i\|^2=1-\delta_i\in[0,1]$ (the definition requires $\|a_i\|\le1$), and $a_i^{\mathsf T}a_k=\Sigma_{ik}$ for $i\ne k$. The diagonal delta cancels exactly: $\Sigma(A)=\Sigma$. $T$ is linear in independent Gaussians $(Z,\varepsilon)$ with $Z\sim\mathcal N_N(0,I_N)$, so its law is $\mathcal N_N(\theta,\Sigma)$. The p-values, BH and $I_0$ are deterministic functions of $(T,q)$ and of $\theta$, so $V/(R\vee1)$ has the same law. No inverse is used, so singular $\Sigma$ is covered. This is a multifactor representation with $m=d=N$.
2. Constants (Step 2). $\kappa=2\kappa_2>0$ and $C=C_2\ge1$ are admissible inputs for L3, and $A_3,q_3$ are universal because $\kappa_2,C_2$ are. $q\le\overline\Phi(\max\{1,6\kappa_2/\pi\})$ gives $u\ge6\kappa_2/\pi$, hence $2\kappa_2/u\le\pi/3$ and $\tau\le\pi/6$. (G1) holds for $q\le q_0<1/2$. In (G2) the word "equivalent" belongs to the Mills lower bound: $q^{1/2}s/((1+s^2)\sqrt{2\pi})\ge q$ if and only if $g(s)\ge\sqrt{2\pi}$, and this suffices for $\overline\Phi(s)\ge q$. The derivative bound uses $2s/(1+s^2)\le1$ and $s+1/s\ge2$. I checked $g(3)=3e^{4.5}/10\approx27.005$. So $\sqrt{\log(1/q)}\le u\le\sqrt{2\log(1/q)}$ on $(0,q_0]$.
3. Exact FDR split (Step 3). $I_0=I_{\mathrm{rare}}\sqcup I_{\mathrm{hv}}$. The numerators add pointwise over the one common denominator $R\vee1$ of the unmodified procedure, so the split is exact, with no remainder. $I_{\mathrm{rare}}$ and $\mu_i$ are literally the objects in L2's statement (scale $\kappa_2/u$, normalization $1/m=1/N$). L2's hypotheses (any multifactor representation, $0<q\le q_2$, the same ordinary BH) hold, so the rare term is at most $A_2q(1+u)$.
4. Counting heavy centres (Step 4). $I_{\mathrm{hv}}=\{i\in I_0:r_i=0\}\sqcup H^+$ is correct. Because $\tau\le\pi$, the cosine condition in $\mu_{c_j}$ is the same as $\angle\le\tau$, so $|B_j|/m=\mu_{c_j}\ge q^{C_2}$. The triangle inequality for the geodesic angle and the $>2\tau$ separation make the $B_j\subseteq I_0$ pairwise disjoint, so $J\le q^{-C_2}$. By maximality, every $i\in H^+$ lies within $2\tau$ of some centre. Each $c_j$ has angle $0$ to itself and angle $>2\tau$ to every other centre, so the least-index assignment puts $c_j\in C_j$, and every $C_j$ is nonempty. Putting the $r_i=0$ members into $C_1$ keeps the sets a partition. The degenerate case $H^+=\varnothing$ (with $J=1$, the condition vacuous) and the case $I_{\mathrm{hv}}=\varnothing$ are handled.
5. Angle condition of L3 (Steps 4 and 6). For $r_i>0$ in $C_j$, $\angle(w_i,v_j)\le2\kappa_2/u\le\pi/3$, and cosine is decreasing on $[0,\pi]$. This gives $a_i^{\mathsf T}v_j=r_i\cos\angle(w_i,v_j)\ge r_i\cos(\kappa/u)$ with $\kappa=2\kappa_2$, which is exactly L3's hypothesis. Also $J\le q^{-C}$, $0<q\le q_3$, $I_*=I_{\mathrm{hv}}\subseteq I_0$, and the $v_j$ are unit vectors.
6. Gaussian width (Step 6). Each $v_j^{\mathsf T}Z$ is standard normal. The bound $\mathbb E\max_j\le\sqrt{2\log J}$ comes from Jensen with a union of moment generating functions, and it does not need independence. With $\log J\le C_2\log(1/q)$ the heavy term is at most $A_3q(1+u+\sqrt{2C_2\log(1/q)})$.
7. Conclusion (Step 7). $A_2(1+\sqrt2\ell)\le A_2(1+\sqrt2)(1+\ell)$, and similarly for the $A_3$ term, so $A'$ is as displayed. $A'$ and $q_0$ depend only on $(\kappa_2,C_2,A_2,q_2)$ and on $A_3,q_3$ at $(2\kappa_2,C_2)$. The bound holds for every admissible $(N,\theta,\Sigma)$ at each fixed $q\le q_0$, so taking the supremum is legitimate even when the model depends on $q$. The acceptance criterion's conversion with $q_{0,1}=\min\{q_0,e^{-1}\}$ and $C_1=2A'$ gives the target statement exactly.

Small points, none affecting validity. (a) The (G2) wording, as noted in item 2. (b) The symbol $C_1$ is used both for the first heavy cluster in Step 4 and for the target's constant in Step 7; they are different objects. (c) Step 5 needs $x_j\le1/2$ for (G1), which holds because $x_j\le q$; its constant $A$ is generous but correct. No step needs more than the lemmas' statements.
