---
type: plan
title: >-
  Linear one-sided Gaussian Simes bound via fixed-level acceptance of a
  Mills-normalized penalized subset supremum
status: abandoned
target_asset: gaussian_simes_one_sided_uniform_linear_bound
route_lemmas:
  - gaussian_simes_fixed_level_amplification
  - gaussian_simes_mills_penalized_subset_reduction
  - gaussian_mills_penalized_subset_supremum_acceptance
route_title: via a Mills-normalized penalized subset supremum
origin: agent
inspired_by:
  - idea_7d0a17e5c13c
  - idea_8699fa13f1f6
  - idea_e1c816206945
  - idea_9dc45fd77c4b
  - idea_b57684f6c514
  - idea_4d3b81529002
  - idea_a2ee64f07126
  - idea_10f14a1fa91d
tags:
  - simes
  - global_null
  - hinge_form
route_round: 1
reduction_digest: 3ab3aa743c7534bccf8e73d9c77092c8be126984908a56c312539c8e4fce95a7
reduction_inputs:
  gaussian_simes_one_sided_uniform_linear_bound: 056ac9e2897851e7a490dc0b61a7810240e679307e0595cf07ea9c09c0ec8abc
  gaussian_simes_fixed_level_amplification: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
  gaussian_simes_mills_penalized_subset_reduction: d8696dc0ee5040d69e3a44c44fe818131df421b54610842f2b5ca99f0ec56f89
  gaussian_mills_penalized_subset_supremum_acceptance: d3f1947df037516732eca7aa1a62191594e52c4d36ea06fed769788d4ec0bb33
reduction_verified_digest: 3ab3aa743c7534bccf8e73d9c77092c8be126984908a56c312539c8e4fce95a7
reduction_checked: true
---

# Linear one-sided Gaussian Simes bound via a Mills-normalized penalized subset supremum

## Goal

Target: [gaussian_simes_one_sided_uniform_linear_bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md).

Prove the uniform linear bound by reducing it, through one deterministic structure lemma and independent-block amplification, to a single fixed-level acceptance estimate for a scale-invariant penalized supremum over null sub-populations.

## Route

- gaussian_simes_fixed_level_amplification: turns a worst-case rejection bound $B(\alpha_0)\le1-\delta$ at one level into $B(t)\le 2\log(1/\delta)\,t/\alpha_0$ for $t\le\alpha_0/2$ (step 4).
- gaussian_simes_mills_penalized_subset_reduction: deterministic inclusion $E_q\subseteq\{M_A(T)\ge\frac12\sqrt{\log(1/(Aq))}-1\}$ for $q\le e^{-1}/A$ (step 2).
- gaussian_mills_penalized_subset_supremum_acceptance: universal $A,s_0,\delta_0$ with $\mathbb P(M_A(T)\le s_0)\ge\delta_0$ for every Gaussian model (step 3); this is the crux, where sparse crossings are handled.

## Plan

1. [x] Fix the universal constants $A\ge2$, $s_0\ge0$, $\delta_0\in(0,1]$ given by gaussian_mills_penalized_subset_supremum_acceptance, and set $q_*=A^{-1}\exp(-4(s_0+1)^2-1)$. Then $q_*\le e^{-1}/A<1/2$ and $\frac12\sqrt{\log(1/(Aq_*))}-1>s_0$.
2. [x] For every $N$, $\Sigma\in\mathcal C_N$ and every realization of $T\sim\mathcal N_N(0,\Sigma)$, gaussian_simes_mills_penalized_subset_reduction applied to $t=T$ with $q=q_*$ gives $E_{q_*}\subseteq\{M_A(T)>s_0\}$, where $E_q$ is the event of the target with $p_i^{(1)}=\overline\Phi(T_i)$.
3. [x] By step 2 and gaussian_mills_penalized_subset_supremum_acceptance, $\mathbb P_{N,0,\Sigma}(E_{q_*})\le1-\mathbb P_{N,0,\Sigma}(M_A(T)\le s_0)\le1-\delta_0$ for every $N$ and every $\Sigma\in\mathcal C_N$, singular included.
4. [x] Put $\delta=\min\{\delta_0,1/2\}\in(0,1)$. Step 3 gives $B(q_*)\le1-\delta$ for the worst-case size $B$ of gaussian_simes_fixed_level_amplification. Apply that lemma with $\alpha_0=q_*\in(0,1)$: $B(t)\le 2\log(1/\delta)\,t/q_*$, hence $\mathbb P_{N,0,\Sigma}(E_t)\le 2\log(1/\delta)\,t/q_*$ for every $N$, $\Sigma\in\mathcal C_N$ and $t\in(0,q_*/2]$.
5. [x] Set $q_0=q_*/2\in(0,1/2)$ and $C=2\log(1/\delta)/q_*$. Both depend only on the universal $A,s_0,\delta_0$, so step 4 gives $\mathbb P_{N,0,\Sigma}(E_q)\le Cq$ for all $0<q\le q_0$, all $N$ and all $\Sigma\in\mathcal C_N$.
6. [x] Record the equivalence with the BH form: with all coordinates centered, $E_q=\{R_q^{(1)}\ge1\}$ by the definition of the largest qualifying rank, and the FDR equals $\mathbb P(R_q^{(1)}\ge1)$ because every rejection is false and $V/(R\vee1)=1$ on $\{R\ge1\}$.

## Verification

Steps 1 to 5 give exactly the displayed inequality of the target, with non-strict comparisons $p_{(k)}^{(1)}\le qk/N$ as in both lemma statements, with constants $C$ and $q_0\in(0,1/2)$ free of $N$, $\Sigma$, its rank and signs. Step 6 gives the stated equivalent BH and FDR form from the definitions of the [ordinary BH step-up procedure](../definitions/benjamini_hochberg_step_up.md), the [false discovery rate](../definitions/false_discovery_rate.md) and the [Gaussian BH notation](../definitions/gaussian_worst_case_bh_fdr.md). The amplification lemma is used only with the uniform hypothesis supplied by step 3, and the reduction lemma is deterministic, so no measurability or attainment issue arises beyond $M_A$ being a finite maximum of affine functions of $T$.

Status of the crux: a short layer-cake comparison (as in the reverse comparison of [the convex hinge acceptance region](../ideas/idea_9dc45fd77c4b.md), using $h(h-\mathrm{id})<1$) suggests that $\{M_A(T)>s_0\}$ is contained in a Simes event at level $1/(A(1+s_0))$; if verified, the acceptance lemma is implied by the target and is not stronger than needed. That comparison is unverified and is not used by the reduction.

## Difference from failed plans

- First earlier report (no plan written; dense crossings via the log-convex tilt and Lehec, sparse crossings costing about $q$ per threshold window over $\log N$ windows): here no union over threshold windows is taken. The reduction lemma charges any crossing, dense or sparse, to one functional $M_A$ whose gain $\frac12\sqrt{\log(1/(Aq))}$ is uniform over rank scales, and only one fixed level is needed.
- Second earlier report (no plan written; the exponential Gibbs kernel loses a Mills factor, and the hinge ratio $X(x)/\psi(x)$ needed a scale-summable $1/a$ tail): $M_A$ keeps the hinge geometry of subset averages against Gaussian top-fraction means, so no exponential-kernel Mills loss, but multiplies the excess by $\tau_A(K)$, which removes the shrinking sparse-scale gap $\log a/x$. The crux asks only for a positive acceptance probability at one penalty level, not a $1/a$ tail summed over dyadic scales, a bounded mean (ruled out for the hinge ratio by idea_4d3b81529002) or a nonpositive mean (ruled out by idea_b57684f6c514).

## Reduction

The three route lemmas are used as black boxes by their statements. For $\alpha\in(0,1)$, $N\ge1$, $\Sigma\in\mathcal C_N$ and $T\sim\mathcal N_N(0,\Sigma)$ write $p_i^{(1)}=\overline\Phi(T_i)$ and
$$
E_\alpha=\Bigl\{\exists k\in\{1,\ldots,N\}:p_{(k)}^{(1)}\le\frac{\alpha k}{N}\Bigr\}.
$$
This is literally the event in the target and the event $E_\alpha$ of gaussian_simes_fixed_level_amplification (same p-values, same order statistics with multiplicities, same non-strict comparison). It is a Borel event, since the order statistics are continuous functions of $T$, and $M_A$ is a maximum of finitely many affine functions of $t$, hence continuous; so all probabilities below are defined. The functional $M_A$ is defined by the same formula in gaussian_simes_mills_penalized_subset_reduction and gaussian_mills_penalized_subset_supremum_acceptance (same $\kappa_K$, $z_K$, $\tau_A(K)=h(z_K)$, $X_K$, maximum over nonempty $K$).

**Step 1 (constants).** Let $A\ge2$, $s_0\ge0$, $\delta_0\in(0,1]$ be the universal constants of gaussian_mills_penalized_subset_supremum_acceptance, and put
$$
q_*=A^{-1}\exp\bigl(-4(s_0+1)^2-1\bigr).
$$
Then $Aq_*=\exp(-4(s_0+1)^2-1)\le e^{-1}$, so $0<q_*\le e^{-1}/A\le e^{-1}/2<1/2$. Moreover $\log(1/(Aq_*))=4(s_0+1)^2+1>4(s_0+1)^2$, so $\sqrt{\log(1/(Aq_*))}>2(s_0+1)$ and
$$
\tfrac12\sqrt{\log\tfrac1{Aq_*}}-1>s_0 .
$$

**Step 2 (deterministic inclusion).** Fix $N\ge1$, $\Sigma\in\mathcal C_N$, and a realization $t=T(\omega)\in\mathbb R^N$. The hypotheses of gaussian_simes_mills_penalized_subset_reduction hold with this $N$, this $t$, the $A\ge2$ of step 1 and $q=q_*$, because $0<q_*\le e^{-1}/A$. Its p-values $\overline\Phi(t_i)$ are exactly $p_i^{(1)}(\omega)$. Hence if $\omega\in E_{q_*}$, there is $k$ with $p_{(k)}^{(1)}\le q_*k/N$, and the lemma gives $M_A(t)\ge\frac12\sqrt{\log(1/(Aq_*))}-1>s_0$ by step 1. As this holds pointwise, ties included,
$$
E_{q_*}\subseteq\{M_A(T)>s_0\}.
$$

**Step 3 (fixed-level size bound).** By step 2 and gaussian_mills_penalized_subset_supremum_acceptance, which applies to every $N$ and every $\Sigma\in\mathcal C_N$ (singular and mixed-sign included),
$$
\mathbb P_{N,0,\Sigma}(E_{q_*})\le\mathbb P_{N,0,\Sigma}(M_A(T)>s_0)=1-\mathbb P_{N,0,\Sigma}(M_A(T)\le s_0)\le1-\delta_0 .
$$

**Step 4 (amplification).** Put $\delta=\min\{\delta_0,1/2\}$, so $\delta\in(0,1/2]\subset(0,1)$ and $1-\delta_0\le1-\delta$. Taking the supremum in step 3 over $N\ge1$ and $\Sigma\in\mathcal C_N$ gives $B(q_*)\le1-\delta_0\le1-\delta$, with $B$ as in gaussian_simes_fixed_level_amplification. That lemma applies with $\alpha_0=q_*\in(0,1)$ and this $\delta$, and gives
$$
\mathbb P_{N,0,\Sigma}(E_t)\le B(t)\le\frac{2\log(1/\delta)}{q_*}\,t\qquad\text{for all }N\ge1,\ \Sigma\in\mathcal C_N,\ t\in(0,q_*/2].
$$

**Step 5 (constants of the target).** Set $q_0=q_*/2$ and $C=2\log(1/\delta)/q_*$. Then $q_0\in(0,1/4)\subset(0,1/2)$ and $0<C<\infty$, since $\log(1/\delta)\ge\log2>0$ and $q_*>0$. Both are functions of $A,s_0,\delta_0$ only, hence universal: they do not depend on $N$, $\Sigma$, its rank or its signs. For $0<q\le q_0$, step 4 with $t=q$ gives
$$
\mathbb P_{N,0,\Sigma}\Bigl(\exists k\in\{1,\ldots,N\}:p_{(k)}^{(1)}\le\frac{qk}{N}\Bigr)=\mathbb P_{N,0,\Sigma}(E_q)\le Cq
$$
for every $N\ge1$ and every $\Sigma\in\mathcal C_N$, which is the displayed inequality of the target.

**Step 6 (BH and FDR form).** Let $0<q\le q_0$, so $q\in(0,1)$ and the [ordinary BH step-up procedure](../definitions/benjamini_hochberg_step_up.md) is defined at level $q$. By its definition, $\widehat k_q(p^{(1)})>0$ exactly on $E_q$. If $\widehat k_q>0$, then $p_{(\widehat k_q)}^{(1)}\le q\widehat k_q/N$, so the index carrying this order statistic lies in $\mathcal R_q(p^{(1)})$ and $R_q^{(1)}\ge1$; if $\widehat k_q=0$, then $\mathcal R_q=\varnothing$. Hence $\{R_q^{(1)}\ge1\}=E_q$. With $\theta=0$, the one-sided true-null set of the [Gaussian test p-values](../definitions/gaussian_test_pvalues.md) is $I_0^{(1)}(0)=\{i:0\le0\}=\{1,\ldots,N\}$, so $V_q^{(1)}=R_q^{(1)}$ and $V_q^{(1)}/(R_q^{(1)}\vee1)=\mathbf 1\{R_q^{(1)}\ge1\}$. By the [false discovery rate](../definitions/false_discovery_rate.md) and the [Gaussian BH notation](../definitions/gaussian_worst_case_bh_fdr.md),
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,0,\Sigma)=\mathbb P_{N,0,\Sigma}(R_q^{(1)}\ge1)=\mathbb P_{N,0,\Sigma}(E_q)\le Cq,
$$
which is the equivalent form stated in the target. This completes the reduction: the target follows from gaussian_simes_mills_penalized_subset_reduction, gaussian_mills_penalized_subset_supremum_acceptance and gaussian_simes_fixed_level_amplification as stated.

## Reduction verdict

confirmed

Checked against the statements alone of gaussian_simes_mills_penalized_subset_reduction, gaussian_mills_penalized_subset_supremum_acceptance and gaussian_simes_fixed_level_amplification, and against the approved definitions.

- Setup. The event $E_\alpha$ is the target's event: same p-values $\overline\Phi(T_i)$, order statistics with multiplicities, non-strict comparison. It also matches the event in the amplification lemma. The two lemmas define $M_A$ by the same formula: $\kappa_K$, $z_K=\overline\Phi^{-1}(\kappa_K/A)$, $\tau_A(K)=h(z_K)$, and a maximum over nonempty $K$. Here $\kappa_K/A\in(0,1/2]$, so $z_K$ is well defined. $\tau_A(K)$ depends only on $|K|$, so $M_A$ is a maximum of finitely many affine functions and hence continuous. This makes the measurability claim correct.
- Step 1. $Aq_*=\exp(-4(s_0+1)^2-1)\le e^{-1}$, so $q_*\le e^{-1}/A$, which is the reduction lemma's hypothesis. $\log(1/(Aq_*))=4(s_0+1)^2+1$ gives $\tfrac12\sqrt{\log(1/(Aq_*))}-1>s_0$ strictly. The arithmetic is right.
- Step 2. The reduction lemma holds for every $A\ge2$. It is applied with the $A$ from the acceptance lemma and $q=q_*$, pointwise in $t$, ties included. This gives $E_{q_*}\subseteq\{M_A(T)>s_0\}$. The strict inequality from step 1 is exactly what is needed to pass to the complement of $\{M_A\le s_0\}$.
- Step 3. Taking complements and applying the acceptance lemma, which is uniform over all $N$ and all $\Sigma\in\mathcal C_N$, gives $\mathbb P(E_{q_*})\le1-\delta_0$.
- Step 4. The lemma allows $\delta_0=1$, but amplification needs $\delta\in(0,1)$. Setting $\delta=\min\{\delta_0,1/2\}$ handles this correctly. The bound for each model passes to the supremum $B(q_*)\le1-\delta$. All hypotheses of the amplification lemma hold, with $\alpha_0=q_*\in(0,1)$.
- Step 5. $q_0=q_*/2\in(0,1/2)$ and $C=2\log(1/\delta)/q_*\in(0,\infty)$. Both depend only on $(A,s_0,\delta_0)$. The order of quantifiers matches the target: constants first, then every $N$, $\Sigma$ (singular included) and $q\in(0,q_0]$. Also $\mathbb P(E_q)\le B(q)$ by the definition of $B$.
- Step 6. Under the BH definition, $\widehat k_q>0$ exactly on $E_q$, and $\widehat k_q>0$ if and only if $\mathcal R_q\neq\varnothing$: the index carrying $p_{(\widehat k_q)}$ is rejected. With $\theta=0$ we have $I_0^{(1)}=[N]$, so $V=R$ and the FDR equals $\mathbb P(R_q^{(1)}\ge1)=\mathbb P(E_q)$. The level satisfies $q\le q_0<1$, so BH is defined.

No gaps found. As the route says, all the weight rests on the acceptance lemma, which this check takes as given.

## Dropped

The researcher asked (12 November 2026) to replace the stuck routes with a round built on the Schur-square tensor-lift idea; this route waits on a lemma that was set aside.
