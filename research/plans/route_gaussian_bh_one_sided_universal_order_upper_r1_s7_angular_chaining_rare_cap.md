---
type: plan
title: >-
  Universal one-sided order via angular null clusters, heavy-cluster chaining
  and a rare-cluster cap
status: pending
target_asset: gaussian_bh_one_sided_universal_order_upper
route_lemmas:
  - gaussian_bh_angular_cluster_partial_entropy_bound
  - gaussian_bh_separated_rare_cluster_cap
  - gaussian_bh_heavy_cluster_strip_chaining_bound
route_title: 'via angular clusters, chaining and a rare-cluster cap'
origin: agent
inspired_by:
  - idea_2251f0ebf933
  - idea_c5bacf260246
  - idea_75d71c7756b4
tags:
  - angular_chaining_route
route_round: 1
reduction_digest: b19cd2d2d6a330e651c585ce4d4b2bbe26f9d418fbd2c585abf789d42d74288e
reduction_inputs:
  gaussian_bh_one_sided_universal_order_upper: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
  gaussian_bh_fractional_frame_surface_kernel: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
  gaussian_bh_conditional_compound_calibration: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
  gaussian_bh_negative_null_boundary_strip: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
  gaussian_bh_conditional_subpoisson_calibration: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
  gaussian_bh_angular_cluster_partial_entropy_bound: 736750aaadb60109c2ce46215b308676bc7a0cd9e89173948fa97978fa8123b1
  gaussian_bh_separated_rare_cluster_cap: 41a2d96d4641af88c2627a7dc0e53cf74e3004654a2cb9353183aff244b71a7d
  gaussian_bh_heavy_cluster_strip_chaining_bound: 3fd13849b9262639666b479775189284e60eadc807612cd102e9eafe287c1b32
reduction_verified_digest: b19cd2d2d6a330e651c585ce4d4b2bbe26f9d418fbd2c585abf789d42d74288e
reduction_checked: true
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement: finite universal $C_1$ and $q_{0,1}$ with $F_1(q)\le C_1q\sqrt{\log(1/q)}$ for $0<q\le q_{0,1}$, over every finite $N$, every $\theta$, every unit-diagonal PSD $\Sigma$ (singular allowed), with $I_0=\{i:\theta_i\le0\}$, largest qualifying rank and non-strict comparisons. This route follows [Route 1: directional entropy to multi-scale chaining with a rare-cluster cap](../ideas/idea_2251f0ebf933.md), continuing [the chaining proposal](../ideas/idea_c5bacf260246.md). The approved [directional-entropy bound](../assets/directional_entropy_one_sided_fdr_bound.md) needs null loadings on exactly the same ray. Here null directions are grouped at angular scale $\kappa/u$ instead, and the target is split into three explicit inequalities, each at the scale $q(1+u)$ or $q\pi(1+\log(1/\pi))$:

- off-strip control of one cluster (angular stability, scale $1/u$);
- a cap on all rare clusters together (separation plus competition at the single BH cutoff);
- a joint strip bound on the heavy clusters (generic chaining over at most $q^{-C}$ centers).

**Remainders stated before execution (saturation check).** These three lemmas are the only unproved inequalities. None is an identity, and none is the FDR rewritten. Zero-mean independent nulls ($w_i$ orthonormal on $I_0$) are a check case. The greedy net then gives singletons of mass $1/m$. If $m\ge q^{-C_2}$, every cluster is rare, and the cap must give $O(q(1+u))$; BH under independence gives $q\pi_0$, so this case is consistent. If $m<q^{-C_2}$, every cluster is heavy and lemma 1(a) charges $q\pi_0$. The strip sum is charged $q(1+u)$, whereas the one-scale entropy charge would be $q\log m$, up to $C_2q\log(1/q)$. The chaining lemma is exactly where $\log$ improves to $\sqrt{\log}$. Now take the representation $w_i=$ rows of $\Sigma^{1/2}$ for the small-null-loading lower family reconstructed in [the failed FDP-entropy plan](plan_one_sided_order_fdp_entropy_mills_coherence_20261107.md) (P4a–P4b, not an approved node). Its null directions are nearly orthogonal, so all of them can be rare while $F\ge c\,qU$. For this reason the cap is stated at $q(1+u)$, not at the $O(q)$ of the source idea; an $O(q)$ cap for arbitrary unit-direction representations would contradict that family. The [one-null staircase](../ideas/idea_75d71c7756b4.md) shows that a single cluster can attain its full entropy charge, so the cap must use competition between clusters, not a per-cluster bound.

## Route

- gaussian_bh_angular_cluster_partial_entropy_bound: off the strip $u<Y_h\le b_h$, a heavy cluster of angular radius $\kappa/u$ costs $O(q\pi_h)$ (step 5). Its part (b) gives the dimension-free $q\log(1/q)$ fallback (step 8).
- gaussian_bh_separated_rare_cluster_cap: all clusters of mass below $q^{C_2}$ together cost $O(q(1+u))$ (step 4).
- gaussian_bh_heavy_cluster_strip_chaining_bound: the strip parts of all heavy clusters together cost $O(q(1+u))$ instead of $q\sum_h\pi_h\log(1/\pi_h)$ (step 6).

## Plan

1. [x] Unit-direction representation. Given admissible $(N,\theta,\Sigma)$, let $w_i$ be the $i$-th row of the PSD square root $\Sigma^{1/2}$ ($d=N$). Then $\|w_i\|^2=\Sigma_{ii}=1$ and $w_i^{\mathsf T}w_j=\Sigma_{ij}$, so $T'=\theta+\Sigma^{1/2}Z$ has the law $\mathcal N_N(\theta,\Sigma)$. Since $\mathrm{FDR}^{(1)}_{\mathrm{BH}}$ depends only on the law of $T$, with the same $I_0$ and the same BH map, it equals the FDR of the unit-direction model $T_i'=\theta_i+w_i^{\mathsf T}Z$ used in all three lemmas.
2. [x] Greedy separated net. Fix $\kappa=\kappa_2$ and $C=C_2$ from the rare-cluster cap, and $0<q\le q_*:=\min\{q_1(\kappa_2,C_2),q_2,q_3(\kappa_2,C_2)\}<1/2$. Order $I_0$. Repeatedly take the first unassigned null $i$, set $v=w_i$, and assign to its cluster every unassigned $j\in I_0$ with $\|w_j-v\|\le\kappa/u$. Every null then lies within $\kappa/u$ of its center. A later center was unassigned when each earlier center was chosen, so the centers are pairwise more than $\kappa/u$ apart. This is a separated angular partition at scale $\kappa_2$ in the sense of the cap lemma.
3. [x] Decomposition. $\mathrm{FDP}=\sum_hV_h/(R\vee1)$. Split $h$ into rare ($\pi_h<q^{C_2}$) and heavy ($\pi_h\ge q^{C_2}$). For heavy $h$, write $1=\mathbf 1\{Y_h\le u\}+\mathbf 1\{Y_h>b_h\}+\mathbf 1\{u<Y_h\le b_h\}$, an exact pointwise identity since $b_h\ge u$.
4. [x] Rare clusters: by gaussian_bh_separated_rare_cluster_cap, $\sum_{\mathrm{rare}}\mathbb E[V_h/(R\vee1)]\le A_2q(1+u)$.
5. [x] Heavy off-strip: each heavy $(G_h,v_h)$ is an angular cluster at scale $\kappa_2$ with $\pi_h\ge q^{C_2}$. By gaussian_bh_angular_cluster_partial_entropy_bound (a) and $\sum_h\pi_h\le\pi_0\le1$, the off-strip terms total at most $A_1q$.
6. [x] Heavy strip: the heavy clusters, with their centers, form a heavy separated angular family at scale $\kappa_2$ and exponent $C_2$, because separation is inherited from step 2. By gaussian_bh_heavy_cluster_strip_chaining_bound, the strip terms total at most $A_3q(1+u)$.
7. [x] Conclusion. Adding steps 4–6 gives $\mathrm{FDR}\le(A_1+A_2+A_3)\,q\,(1+u)$ for all $0<q\le q_*$ and every model. The Chernoff bound in the approved directional-entropy proof gives $u\le\sqrt{2\log(1/q)}$, so $\mathrm{FDR}\le\sqrt2(A_1+A_2+A_3)\,q\,[1+\sqrt{\log(1/q)}]$.
8. [x] Fallback milestone, not needed for step 7. Suppose the chaining lemma fails but the other two hold. Part (b) of the cluster lemma bounds the heavy strip terms by $A_1q\sum_h\pi_h(1+C_2\log(1/q))\le A_1q(1+C_2\log(1/q))$. With steps 4–5 this gives a dimension-free bound $F_1(q)\le A\,q\log(1/q)$, the milestone named in the source idea. If the cap is proved only at scale $q\log(1/q)$, the same milestone still follows.

Guidance for the lemma stages, not part of the reduction:

- Cluster lemma: reuse the leave-one-out conditional bound of the approved entropy proof, conditioning on all of $Z$. Write $w_i^{\mathsf T}Z=\cos\alpha_iY_G+\sin\alpha_i W_i$ with $\alpha_i\lesssim\kappa/u$. On $Y_G\le b_G\le c_Cu$, the shift $\sin\alpha_iW_i$ changes $1/\overline\Phi$ by a factor $e^{O(b_G\alpha_i|W_i|)}$, bounded in mean. Locate exactly where the approved proof uses "same ray".
- Cap: the rare clusters have deep cutoffs $b_h\ge\overline\Phi^{-1}(q^{1+C_2})\approx\sqrt{1+C_2}\,u$ and centers with correlation at most $1-\kappa^2/(2u^2)$. A null of cluster $h$ at strip level $y$ needs the single BH threshold $qR/m\approx\overline\Phi(y)$, so the rare clusters compete for one scalar cutoff. Candidate tools are the approved [compound calibration](../assets/gaussian_bh_conditional_compound_calibration.md) applied to the rare null subset, which puts the level supremum outside the sum, and the [sub-Poisson calibration](../assets/gaussian_bh_conditional_subpoisson_calibration.md). Neither tool's hypotheses have been checked for this use.
- Chaining lemma: the strip charge of a cluster is a tilt functional of $Y_h$. Two centers at distance $\delta$ have tilts that cannot be separated beyond a factor $e^{O(u\delta)}$. Use Talagrand's generic chaining over the at most $q^{-C}$ centers in the chordal metric, whose $\gamma_2$ is $O(\sqrt{C\log(1/q)})=O(u)$; first test the two-level form CH-2 of idea_c5bacf260246.
- Failure criterion (from the source idea): a family with many clusters at angle about $1/u$ and FDR$/(q\log(1/q))$ unbounded refutes the cap at that scale. The route then yields only a structured class.

## Verification

Steps 1–2 hold for every admissible finite model, including singular $\Sigma$, arbitrary $\theta$, negative null means and $q$-dependent parameters. Step 1 preserves the law of $T$, the labels and the BH map exactly. The decomposition in step 3 is a pointwise identity for the actual largest-rank BH procedure; no coordinate is removed or relabeled. Each lemma is applied with its hypotheses checked in steps 2, 5 and 6, for the fixed universal pair $(\kappa_2,C_2)$. All constants $A_1(\kappa_2,C_2),A_2,A_3(\kappa_2,C_2)$ and $q_*$ are therefore universal. Step 7 gives $F_1(q)\le A_1'q[1+\sqrt{\log(1/q)}]$ on $0<q\le q_*$ with $A_1'=\sqrt2(A_1+A_2+A_3)$. This is the sufficient finite-level conclusion in the target's acceptance criterion: take $q_{0,1}=\min\{q_*,e^{-1}\}$ and $C_1=2A_1'$.

## Difference from failed plans

- plan_252211621cea: no signed path accounting or switch-sum cancellation; the remainders are inequalities over angular clusters, not a masked switch sum equal to the FDR.
- plan_503f8fddcbb5: no global shift, record partition or Stein facet allocation; the external input is angular stability plus chaining over null directions.
- plan_ee2f7b97740a: no rank-chain transport or Hall-cut maximum; clusters are formed geometrically from null directions, not from rank cells.
- plan_one_sided_order_actual_mean_global_flux_20261106: no crossing or positive-flux counting; the BH rank enters only through the leave-one-out conditional bound and the single-cutoff competition in the cap.
- plan_one_sided_order_common_anchor_rotation_20261107: no rotation interpolation or integrated facet flux, whose terminal terms cancel back to the FDR.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: no convex proxy or activation flux; BH itself is analysed by grouping null labels.
- plan_one_sided_order_fdp_entropy_mills_coherence_20261107: no trace-versus-coherence certificate. Its low-coherence counterfamily is the reason the cap here is stated at scale $q(1+u)$, a scale that family respects.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no covariance interpolation or SDP completion; nothing is charged per face, so no polynomial face multiplicity arises.
- plan_one_sided_order_mixed_trace_replica_cells_20261108: no replica cells or cross-face pairing; the sum over clusters uses a metric on directions (chaining), not cell faces.
- plan_one_sided_order_three_face_noise_packing_20261106: no Gram-energy budget maximized over a free covariance. Its $\log N$ obstruction came from a budget detached from $\Sigma$; here the charges are functions of the actual directions $w_i$ and the number of heavy centers is at most $q^{-C}$.
- plan_one_sided_order_negative_contact_transport_20261106: no negative-covariance contact transport or diagonal allocation, and no inverse-noise terms.
- plan_one_sided_order_peeling_history_kernel_20261107: no peeling histories or terminal potential, which saturated to the FDR; each remainder here is a stated inequality with an independent Gaussian input.

## Reduction

The target follows from the three route lemmas, each used as a black box by its statement: [the partial entropy bound](../assets/gaussian_bh_angular_cluster_partial_entropy_bound.md) (approved), [the rare-cluster cap](../assets/gaussian_bh_separated_rare_cluster_cap.md) and [the heavy-cluster chaining bound](../assets/gaussian_bh_heavy_cluster_strip_chaining_bound.md) (both draft). No other dependency of the target is used. Nothing else is assumed beyond the elementary Chernoff bound proved in step 7.

**Constants.** Let $\kappa_2\in(0,1]$, $C_2\ge1$, $A_2<\infty$, $q_2\in(0,1/2)$ be the universal constants of the rare-cluster cap. Since $\kappa_2\in(0,1]$ and $C_2\ge1$, the partial entropy bound with $(\kappa,C)=(\kappa_2,C_2)$ supplies finite $A_1:=A_1(\kappa_2,C_2)$ and $q_1:=q_1(\kappa_2,C_2)\in(0,1/2)$. The chaining bound with the same pair supplies finite $A_3:=A_3(\kappa_2,C_2)$ and $q_3:=q_3(\kappa_2,C_2)\in(0,1/2)$. Put
$$
q_*=\min\{q_1,q_2,q_3\}\in(0,1/2).
$$
All of $A_1,A_2,A_3,q_*$ are universal numbers, because $(\kappa_2,C_2)$ is a fixed universal pair. Fix $0<q\le q_*$ and put $u=\overline\Phi^{-1}(q)$. Since $q<1/2$, $u>0$.

**Step 1 (unit-direction representation).** Fix an admissible model $(N,\theta,\Sigma)$: $N\ge1$, $\theta\in\mathbb R^N$, $\Sigma$ symmetric PSD with unit diagonal, singular allowed. Let $S=\Sigma^{1/2}$ be the symmetric PSD square root, and let $w_i\in\mathbb R^N$ be its $i$-th row ($d=m=N$). Then $w_i^{\mathsf T}w_j=(SS^{\mathsf T})_{ij}=(S^2)_{ij}=\Sigma_{ij}$, so in particular $\|w_i\|^2=\Sigma_{ii}=1$ and every $w_i$ is a unit vector. For $Z\sim\mathcal N_N(0,I_N)$, the vector $T'=\theta+SZ$ with coordinates $T'_i=\theta_i+w_i^{\mathsf T}Z$ is Gaussian with mean $\theta$ and covariance $SS^{\mathsf T}=\Sigma$, so $T'\sim\mathcal N_N(\theta,\Sigma)$ (the definition of joint Gaussianity allows singular $\Sigma$). The quantity $V^{(1)}_q/(R^{(1)}_q\vee1)$ is a fixed Borel function of the score vector, through $p_i=\overline\Phi(T_i)$ and the deterministic BH map, with the deterministic null set $I_0=\{i:\theta_i\le0\}$. Hence its expectation depends only on the law of the scores, and
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)=\mathbb E\!\left[\frac{V}{R\vee1}\right],
$$
where now $R$, $V$ are the rejection and false-rejection counts of ordinary BH at level $q$ applied to $p_i=\overline\Phi(T'_i)$, $i=1,\ldots,N$, with the original labels $I_0$, the largest qualifying rank and non-strict comparisons. This is exactly the setting of all three lemmas with $m=N$, $d=N$, the same $\theta$ and these unit vectors $w_i$. If $I_0=\varnothing$ then $V=0$ and the FDR is $0$, so the bound below holds trivially; assume $I_0\ne\varnothing$.

**Step 2 (greedy separated net).** Order $I_0$ as $i_1<i_2<\cdots<i_{m_0}$. Start with all of $I_0$ unassigned and $h=0$. While some null is unassigned: increase $h$ by one, let $c_h$ be the first unassigned null in this order, put $v_h=w_{c_h}$, and let
$$
G_h=\{j\in I_0\text{ unassigned}:\ \|w_j-v_h\|\le\kappa_2/u\};
$$
mark the elements of $G_h$ as assigned. Since $c_h$ itself is unassigned and $\|w_{c_h}-v_h\|=0$, we have $c_h\in G_h$, so each round assigns at least one new null. The procedure therefore stops after some $H\le m_0$ rounds. The sets $G_1,\ldots,G_H$ are nonempty, pairwise disjoint (each null is assigned once) and cover $I_0$ (the procedure stops only when none is unassigned). They therefore partition $I_0$. Each $v_h$ is a unit vector by step 1, and $\|w_i-v_h\|\le\kappa_2/u$ for every $i\in G_h$ by construction. For separation, let $h<k$. The null $c_k$ is unassigned at the start of round $k$, hence also after round $h$, so $c_k\notin G_h$ although $c_k$ was unassigned during round $h$. By the definition of $G_h$, $\|w_{c_k}-v_h\|>\kappa_2/u$, that is, $\|v_k-v_h\|>\kappa_2/u$. Hence $(G_1,v_1),\ldots,(G_H,v_H)$ is a separated angular partition at scale $\kappa_2$ in the sense of the rare-cluster cap.

**Step 3 (decomposition).** Put $\pi_h=|G_h|/N$, $V_h=|\mathcal R_q\cap G_h|$, $Y_h=v_h^{\mathsf T}Z$ and $b_h=\overline\Phi^{-1}(q\pi_h)$. Since $0<q\pi_h\le q$ and $\overline\Phi^{-1}$ is decreasing, $b_h\ge u$. Because the $G_h$ partition $I_0$, $V=\sum_{h=1}^HV_h$ pointwise. Let $\mathcal H_{\mathrm{rare}}=\{h:\pi_h<q^{C_2}\}$ and $\mathcal H_{\mathrm{heavy}}=\{h:\pi_h\ge q^{C_2}\}$; these split $\{1,\ldots,H\}$. For heavy $h$, since $u\le b_h$, the events $\{Y_h\le u\}$, $\{u<Y_h\le b_h\}$, $\{Y_h>b_h\}$ are disjoint and cover the sample space, so their indicators sum to $1$ pointwise. Hence pointwise
$$
\frac{V}{R\vee1}
=\sum_{h\in\mathcal H_{\mathrm{rare}}}\frac{V_h}{R\vee1}
+\sum_{h\in\mathcal H_{\mathrm{heavy}}}\frac{V_h\bigl(\mathbf 1\{Y_h\le u\}+\mathbf 1\{Y_h>b_h\}\bigr)}{R\vee1}
+\sum_{h\in\mathcal H_{\mathrm{heavy}}}\frac{V_h\,\mathbf 1\{u<Y_h\le b_h\}}{R\vee1}.
$$
Every summand is nonnegative and bounded by $1$, and there are finitely many. Taking expectations and using linearity,
$$
\operatorname{FDR}=E_{\mathrm{rare}}+E_{\mathrm{off}}+E_{\mathrm{strip}},
$$
with the three expectations of the three sums. Here $R$, $V_h$ are the counts of the one unmodified BH procedure of step 1 on all $N$ coordinates with the original labels, as all three lemmas require.

**Step 4 (rare clusters).** The family of step 2 is a separated angular partition at scale $\kappa_2$, the model is of the lemma's form (step 1), $0<q\le q_*\le q_2$, and $\mathcal H_{\mathrm{rare}}$ is exactly the lemma's set of rare clusters. The rare-cluster cap gives
$$
E_{\mathrm{rare}}=\sum_{h\in\mathcal H_{\mathrm{rare}}}\mathbb E\!\left[\frac{V_h}{R\vee1}\right]\le A_2\,q\,(1+u).
$$

**Step 5 (heavy clusters off the strip).** For each $h\in\mathcal H_{\mathrm{heavy}}$, $(G_h,v_h)$ is an angular cluster at scale $\kappa_2$ in the sense of the partial entropy bound: $\varnothing\ne G_h\subseteq I_0$, $v_h$ is a unit vector, and $\|w_i-v_h\|\le\kappa_2/u$ for $i\in G_h$. Its quantities $\pi_G,Y_G,b_G,V_G$ are $\pi_h,Y_h,b_h,V_h$, and $\pi_h\ge q^{C_2}$. With $0<q\le q_*\le q_1$, part (a) gives
$$
\mathbb E\!\left[\frac{V_h\mathbf 1\{Y_h\le u\}}{R\vee1}\right]+\mathbb E\!\left[\frac{V_h\mathbf 1\{Y_h>b_h\}}{R\vee1}\right]\le A_1\,q\,\pi_h .
$$
Summing over heavy $h$ and using $\sum_h\pi_h\le\sum_{h=1}^H|G_h|/N=|I_0|/N\le1$ gives $E_{\mathrm{off}}\le A_1q$.

**Step 6 (heavy clusters on the strip).** The family $(G_h,v_h)_{h\in\mathcal H_{\mathrm{heavy}}}$ (relabelled $1,\ldots,|\mathcal H_{\mathrm{heavy}}|$) consists of pairwise disjoint nonempty subsets of $I_0$ and unit vectors with $\|w_i-v_h\|\le\kappa_2/u$ for $i\in G_h$. It has $\|v_h-v_k\|>\kappa_2/u$ for distinct $h,k$, inherited from step 2, and $\pi_h\ge q^{C_2}$. It is therefore a heavy separated angular family at scale $\kappa_2$ and exponent $C_2$; the chaining lemma does not require it to cover $I_0$. Its $Y_h,b_h,V_h$ are those of step 3. If $\mathcal H_{\mathrm{heavy}}=\varnothing$, then $E_{\mathrm{strip}}=0$. Otherwise, with $0<q\le q_*\le q_3$, the chaining bound gives
$$
E_{\mathrm{strip}}=\sum_{h\in\mathcal H_{\mathrm{heavy}}}\mathbb E\!\left[\frac{V_h\mathbf 1\{u<Y_h\le b_h\}}{R\vee1}\right]\le A_3\,q\,(1+u).
$$

**Step 7 (conclusion).** By steps 3–6, since $q\le q(1+u)$,
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le A_2q(1+u)+A_1q+A_3q(1+u)\le(A_1+A_2+A_3)\,q\,(1+u).
$$
Next we bound $u$ by a Chernoff estimate. For $\xi\sim\mathcal N(0,1)$ and $t\ge0$, Markov's inequality with $\lambda=t$ gives $\overline\Phi(t)=\mathbb P(\xi\ge t)\le e^{-\lambda t}\mathbb Ee^{\lambda\xi}=e^{-t^2/2}$. With $t=u>0$ this reads $q\le e^{-u^2/2}$, so $u\le\sqrt{2\log(1/q)}$. Hence
$$
1+u\le1+\sqrt2\sqrt{\log(1/q)}\le\sqrt2\bigl[1+\sqrt{\log(1/q)}\bigr],
$$
and
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\le A_1'\,q\bigl[1+\sqrt{\log(1/q)}\bigr],\qquad A_1'=\sqrt2(A_1+A_2+A_3).
$$
This holds for every admissible $(N,\theta,\Sigma)$ and every $0<q\le q_*$, with $A_1'$ and $q_*$ universal. Taking the supremum over the model at each fixed $q$ gives $F_1(q)\le A_1'q[1+\sqrt{\log(1/q)}]$ on $0<q\le q_*$, where $q_*\in(0,1)$. This is the sufficient finite-level conclusion of the target's acceptance criterion with $\widetilde q_{0,1}=q_*$. Concretely, put $q_{0,1}=\min\{q_*,e^{-1}\}\in(0,1)$ and $C_1=2A_1'$. For $0<q\le q_{0,1}$ we have $\log(1/q)\ge1$, so $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$ and $F_1(q)\le C_1q\sqrt{\log(1/q)}$. The constants $C_1,q_{0,1}$ depend only on $\kappa_2,C_2,A_2,q_2$ and the functions $A_1(\cdot,\cdot),q_1(\cdot,\cdot),A_3(\cdot,\cdot),q_3(\cdot,\cdot)$ at that pair. They are independent of $N$, $\theta$, $\Sigma$, the rank, the null proportion and $H$, which proves the target.

**Step 8 (fallback milestone; not used above).** Suppose only the partial entropy bound and the rare-cluster cap are available. Steps 1–5 are unchanged. For the strip terms, apply part (b) of the partial entropy bound to each heavy cluster. Since $\pi_h\ge q^{C_2}$, $\log(1/\pi_h)\le C_2\log(1/q)$, so
$$
E_{\mathrm{strip}}\le A_1q\sum_{h\in\mathcal H_{\mathrm{heavy}}}\pi_h\bigl(1+C_2\log(1/q)\bigr)\le A_1q\bigl(1+C_2\log(1/q)\bigr).
$$
With step 7's bound $u\le\sqrt{2\log(1/q)}$, and $1,\sqrt{\log(1/q)}\le\log(1/q)$ for $q\le e^{-1}$, this gives $\operatorname{FDR}\le[A_2(1+\sqrt2)+A_1+A_1(1+C_2)]\,q\log(1/q)$ for $0<q\le\min\{q_1,q_2,e^{-1}\}$. This is a dimension-free $q\log(1/q)$ bound. Suppose instead that the cap is available only at scale $A_2'q\log(1/q)$ in place of $A_2q(1+u)$; then the same computation gives the same order. This milestone is not the target and is not needed for step 7.

## Reduction verdict

confirmed

Checked against the target's statement and the three lemma statements only, each used as a black box.

- Constants and quantifiers. The rare-cluster cap fixes universal $\kappa_2\in(0,1]$, $C_2\ge1$, $A_2$, $q_2\in(0,1/2)$. The partial entropy bound and the chaining bound are stated for every $\kappa\in(0,1]$ and every $C\ge1$, so instantiating both at the fixed pair $(\kappa_2,C_2)$ is allowed and gives universal $A_1,q_1,A_3,q_3$. Then $q_*=\min\{q_1,q_2,q_3\}<1/2$ meets every lemma's range $0<q<1/2$, and $u=\overline\Phi^{-1}(q)>0$ is the same $u$ in every lemma.
- Step 1 (same-law representation). With $S=\Sigma^{1/2}$ symmetric PSD, its rows satisfy $w_i^{\mathsf T}w_j=(S^2)_{ij}=\Sigma_{ij}$, so $\|w_i\|=1$. $\theta+SZ$ has mean $\theta$ and covariance $\Sigma$ in the sense of the model definition (every linear functional is centred normal with variance $a^{\mathsf T}\Sigma a$), singular $\Sigma$ included. The FDP is a fixed Borel function of the score vector with the deterministic null set $\{\theta_i\le0\}$, so the FDR depends only on the law of the scores. The resulting model ($m=d=N$, unit $w_i$, $p_i=\overline\Phi(T_i)$, $I_0=\{\theta_i\le0\}$, one unmodified BH on all coordinates) is exactly the setting of all three lemmas. The case $I_0=\varnothing$ gives FDR $0$.
- Step 2 (greedy net). Each round assigns its centre $c_h$, so the procedure stops and the $G_h$ are nonempty, disjoint and cover $I_0$. The radius condition $\|w_i-v_h\|\le\kappa_2/u$ holds by construction and $v_h=w_{c_h}$ is a unit vector. Separation: for $h<k$, $c_k$ was unassigned during round $h$ and was not taken into $G_h$, so $\|v_k-v_h\|>\kappa_2/u$. This is word for word a separated angular partition at scale $\kappa_2$ as the cap defines it.
- Step 3 (split). $\pi_h=|G_h|/N$ matches the lemmas' $|G|/m$. $0<q\pi_h\le q$ gives $b_h\ge u$, so for heavy $h$ the events $\{Y_h\le u\}$, $\{u<Y_h\le b_h\}$, $\{Y_h>b_h\}$ partition the sample space. Since the $G_h$ partition $I_0$ and rare/heavy split the indices, each false rejection is counted in exactly one term, pointwise. The finitely many terms are bounded, so linearity of expectation applies.
- Step 4. $\mathcal H_{\mathrm{rare}}=\{\pi_h<q^{C_2}\}$ is exactly the cap's rare set for this partition, and $q\le q_2$. The cap gives $A_2q(1+u)$.
- Step 5. Each heavy $(G_h,v_h)$ is an angular cluster at scale $\kappa_2$: $\varnothing\ne G_h\subseteq I_0$, $v_h$ a unit vector, radius $\kappa_2/u$. Also $\pi_h\ge q^{C_2}$ and $q\le q_1$. Its $Y_G,b_G,V_G$ coincide with $Y_h,b_h,V_h$. Part (a) gives $A_1q\pi_h$, and $\sum_h\pi_h\le|I_0|/N\le1$.
- Step 6. The heavy subfamily is disjoint, nonempty, inside $I_0$, has radius $\kappa_2/u$, is separated (inherited from step 2) and has $\pi_h\ge q^{C_2}$. That is exactly a heavy separated angular family at scale $\kappa_2$ and exponent $C_2$, and that lemma does not require covering. With $q\le q_3$ it gives $A_3q(1+u)$. The empty heavy family is handled separately, with value $0$.
- Step 7. The Chernoff bound with $\lambda=t$ gives $\overline\Phi(t)\le e^{-t^2/2}$, so $u\le\sqrt{2\log(1/q)}$. Also $1+\sqrt2 s\le\sqrt2(1+s)$ for $s\ge0$. This gives $F_1(q)\le\sqrt2(A_1+A_2+A_3)q[1+\sqrt{\log(1/q)}]$ on $(0,q_*]$, uniformly in $(N,\theta,\Sigma)$, which is the target's sufficient finite-level criterion. Passing to $q_{0,1}=\min\{q_*,e^{-1}\}$ and $C_1=2A_1'$ is correct.
- Step 8 (fallback, not used) is also arithmetically correct: $\sum\pi_h(1+\log(1/\pi_h))\le1+C_2\log(1/q)$, and for $q\le e^{-1}$ both $1$ and $\sqrt{\log(1/q)}$ are at most $\log(1/q)$.

No gaps found. The reduction proves the exact target from the three lemma statements. What remains is proving the two draft lemmas (the separated rare-cluster cap and the heavy-cluster strip chaining bound), which carry all of the difficulty.
