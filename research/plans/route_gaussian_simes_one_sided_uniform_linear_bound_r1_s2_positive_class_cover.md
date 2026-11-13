---
type: plan
title: >-
  Linear Gaussian Simes bound via a random positive-class cover adapted from the
  positive Gaussian Simes inequality
status: abandoned
target_asset: gaussian_simes_one_sided_uniform_linear_bound
route_lemmas:
  - gaussian_simes_fixed_level_amplification
  - gaussian_simes_positive_class_cover_transfer
  - gaussian_simes_dense_crossing_tilt_bound
  - gaussian_simes_sparse_positive_class_hitting
route_title: via a random positive-class cover at a fixed level
origin: agent
inspired_by:
  - idea_665151fb5a87
  - idea_7d0a17e5c13c
  - idea_8699fa13f1f6
  - idea_a2ee64f07126
  - idea_c36aadbe5f06
  - idea_b2631a978a30
tags:
  - simes_positive_cover_route
route_round: 1
reduction_digest: 82734295223da04ffdf6e14c1a320c7aac8274dd063c6808463c0d4e91e71c48
reduction_inputs:
  gaussian_simes_one_sided_uniform_linear_bound: 056ac9e2897851e7a490dc0b61a7810240e679307e0595cf07ea9c09c0ec8abc
  gaussian_simes_fixed_level_amplification: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
  gaussian_simes_positive_class_cover_transfer: 6f5e1db93cf32b89012029bd947a756bef6f729d9d2aea6b980ed9894daae7fb
  gaussian_simes_dense_crossing_tilt_bound: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
  gaussian_simes_sparse_positive_class_hitting: 890cfc3a9c9940c136cc16ee0457d5a898e3cb8394ae61c9b578e3710d695ad7
reduction_verified_digest: 82734295223da04ffdf6e14c1a320c7aac8274dd063c6808463c0d4e91e71c48
reduction_checked: true
---

# Linear Gaussian Simes bound via a random positive-class cover

## Goal

Target: [gaussian_simes_one_sided_uniform_linear_bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md)

Adapt the closest library analogue, [the positive Gaussian Simes inequality and its mixture extension](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md), to arbitrary correlation signs. A random positive class $S$, drawn from a deterministic prior $\pi$ over null sub-populations with nonnegative internal correlations, is a mixture of positive Gaussian laws, so its Simes test has size at most its level. When $S$ hits the actual BH rejection set in proportion to its own size, the global crossing forces a crossing of $S$ at the same level up to a constant. This is the indicator (PAC-Bayes) form of the maximal null tilt: a prior over null sub-populations, Markov on the prior average, and no union over threshold windows. Dense crossings are paid for by the log-convex tilt with Lehec's bound, and everything is done at one fixed level, then amplified.

## Route

- gaussian_simes_fixed_level_amplification: turns a fixed-level size bound $B(\alpha_0)\le3/4$ into the linear bound at small levels (step 4).
- gaussian_simes_positive_class_cover_transfer: bounds the crossings that the prior $\pi$ hits proportionally by $\alpha_0/(c_{\mathrm{hit}}c_*)$, using the library positive Gaussian Simes inequality on each class with the normalization $|S|$, not $N$ (step 3).
- gaussian_simes_dense_crossing_tilt_bound: bounds the dense crossings $D_{\alpha_0,\delta_0}$ by $C_D\alpha_0$ through the log-convex mixture of exponential tilts and Lehec's semilogconvex tail bound, for any correlation signs (step 3).
- gaussian_simes_sparse_positive_class_hitting: the crux. Sparse crossings that no positive-class prior hits proportionally have probability at most $1/4$ at small fixed levels. Its hitting condition only asks $|\mathcal A\cap S|\ge\max(1,c|S|r/N)$, so sparse crossings may use positive classes of vanishing density $|S|/N\approx1/r$. Pairwise-nonpositive or weakly correlated crossers fall into the bad event and need only a fixed bound there, not a linear one (step 3).

## Plan

1. [x] Constants. Take $\delta_0,c_{\mathrm{hit}},c_*,\alpha_1$ from gaussian_simes_sparse_positive_class_hitting and $C_D,q_D$ from gaussian_simes_dense_crossing_tilt_bound. Set $\alpha_0=\min\{\alpha_1,\ q_D,\ 1/(4C_D),\ c_{\mathrm{hit}}c_*/4\}$. Then $0<\alpha_0\le1/4$ and $\alpha_0<c_{\mathrm{hit}}$; all of these are universal.
2. [x] Decomposition. Fix $N$ and $\Sigma\in\mathcal C_N$, and let $\pi=\pi_{\alpha_0,N,\Sigma}$ be the prior given by the sparse hitting lemma. With $h=h_{\alpha_0,\pi,c_{\mathrm{hit}}}$, the event inclusion
$$
E_{\alpha_0}\subseteq D_{\alpha_0,\delta_0}\ \cup\ \bigl(E_{\alpha_0}\cap\{h\ge c_*\}\bigr)\ \cup\ \bigl(E_{\alpha_0}\setminus D_{\alpha_0,\delta_0},\ h<c_*\bigr)
$$
holds pointwise. The hitting mass $h$ in the sparse lemma and in the transfer lemma is the same function, with $q=\alpha_0$ and $c=c_{\mathrm{hit}}$.
3. [x] Three bounds. By the dense lemma with $q=\alpha_0\le q_D$ and $\delta=\delta_0\in(0,1]$, the first event has probability at most $C_D\alpha_0\le1/4$. By the transfer lemma with $q=\alpha_0<c=c_{\mathrm{hit}}$, the second has probability at most $\alpha_0/(c_{\mathrm{hit}}c_*)\le1/4$. By the sparse lemma with $\alpha=\alpha_0\le\alpha_1$, the third has probability at most $1/4$. Hence $\mathbb P_{N,0,\Sigma}(E_{\alpha_0})\le3/4$ for every $N$ and $\Sigma$, that is, $B(\alpha_0)\le3/4$.
4. [x] Amplification. Apply gaussian_simes_fixed_level_amplification with $\delta=1/4$: $B(t)\le(2\log4/\alpha_0)\,t$ for all $t\in(0,\alpha_0/2]$.
5. [x] Conclusion. Put $q_0=\alpha_0/2\in(0,1/2)$ and $C=2\log4/\alpha_0$. For every $N$, $\Sigma\in\mathcal C_N$ and $0<q\le q_0$, the target event $\{\exists k:p^{(1)}_{(k)}\le qk/N\}$ is $E_q$, so its probability is at most $B(q)\le Cq$. For the BH form, $\widehat k_q\ge1$ exactly on $E_q$, so $R_q^{(1)}\ge1$ exactly on $E_q$. With $\theta=0$ every index is a one-sided true null, so $V=R$ and $\mathrm{FDP}=\mathbf 1\{R_q^{(1)}\ge1\}$, which gives $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)=\mathbb P(R_q^{(1)}\ge1)\le Cq$.

## Verification

Step 3 bounds the size at the single level $\alpha_0$ uniformly over all $N$ and $\Sigma\in\mathcal C_N$, singular ones included: each lemma is stated for every unit-diagonal PSD matrix, and the sparse lemma's prior is chosen after $\Sigma$ but independently of $T$, which is what the transfer lemma requires. Step 4 converts this into the linear bound at every $q\le q_0$, with $C$ and $q_0$ depending only on $\alpha_0$, which is universal. The target's event uses non-strict comparisons and multiplicities, as do the definitions of $E_\alpha$ and of $\mathcal R_q$ in all four lemmas. Step 5 identifies the Simes event with $\{R_q^{(1)}\ge1\}$ and with the all-null FDR. So the target statement follows exactly, with the universal constants $C=2\log4/\alpha_0$ and $q_0=\alpha_0/2<1/2$.

## Difference from failed plans

There are no failed plan IDs. The two earlier plan stages ended with no plan:
- The first used the log-convex tilt with a union over about $\log N$ threshold windows for sparse crossings. Here the tilt is used only on dense crossings, and sparse crossings are charged once, at one level, through the prior average of the class Simes events. That average is bounded by the library inequality with no sum over windows or ranks.
- The second used Gibbs and hinge kernels, which lose a Mills factor or need a scale-summable ratio bound. Here the kernel is the exact indicator Simes event of each positive class, whose size is known to be at most its level, so no Mills factor arises. The open part is moved into a fixed-level hitting statement (bad probability at most $1/4$, not $O(q)$).
- Unlike the bounded-sparsity cover of idea_665151fb5a87 and the fixed partition of idea_b2631a978a30, the cover is normalized by $|S|$, so hitting is needed only in proportion to $|S|r/N$, not with a fixed inclusion probability. The prior may depend on the level. Non-hit sparse crossings need only a fixed bound, not one linear in $q$.

## Reduction

The four route lemmas are used as black boxes by their statements: [gaussian_simes_fixed_level_amplification](../assets/gaussian_simes_fixed_level_amplification.md), [gaussian_simes_positive_class_cover_transfer](../assets/gaussian_simes_positive_class_cover_transfer.md), [gaussian_simes_dense_crossing_tilt_bound](../assets/gaussian_simes_dense_crossing_tilt_bound.md) and [gaussian_simes_sparse_positive_class_hitting](../assets/gaussian_simes_sparse_positive_class_hitting.md). Throughout, $p_i=\overline\Phi(T_i)$ are the one-sided p-values $p_i^{(1)}$.

**Preliminary: the two forms of the crossing event agree.** Fix $N$, $\alpha\in(0,1)$ and $p\in[0,1]^N$. Let $E_\alpha^{\exists}=\{\exists k\in[N]:p_{(k)}\le\alpha k/N\}$ (the form used in the target and in the amplification lemma) and $E_\alpha^{R}=\{|\mathcal R_\alpha(p)|\ge1\}$ (the form used in the sparse lemma; the transfer lemma states the two are equal). If some $k$ satisfies $p_{(k)}\le\alpha k/N$, then $\widehat k_\alpha(p)\ge k\ge1$; since $p_{(\widehat k_\alpha)}\le\alpha\widehat k_\alpha/N$, the $\widehat k_\alpha$ indices carrying the order statistics $p_{(1)},\ldots,p_{(\widehat k_\alpha)}$ all lie in $\mathcal R_\alpha(p)$, so $|\mathcal R_\alpha(p)|\ge\widehat k_\alpha\ge1$. Conversely, $\mathcal R_\alpha(p)\neq\varnothing$ forces $\widehat k_\alpha(p)>0$ by the definition of the rejection set, and then $k=\widehat k_\alpha$ qualifies. Hence $E_\alpha^{\exists}=E_\alpha^{R}=\{\widehat k_\alpha\ge1\}$ pointwise, and we write $E_\alpha$ for this event.

**Step 1 (constants).** Let $\delta_0\in(0,1]$, $c_{\mathrm{hit}}\in(0,1]$, $c_*\in(0,1]$, $\alpha_1\in(0,1/4]$ be the universal constants of the sparse hitting lemma and $C_D<\infty$, $q_D\in(0,1/4]$ those of the dense lemma. Enlarging $C_D$ keeps the dense lemma true, so we may and do assume $C_D\ge1$. Put
$$
\alpha_0=\min\Bigl\{\alpha_1,\ q_D,\ \frac1{4C_D},\ \frac{c_{\mathrm{hit}}c_*}{4}\Bigr\}.
$$
Each entry is positive and finite, so $\alpha_0>0$; also $\alpha_0\le\alpha_1\le1/4$, and $\alpha_0\le c_{\mathrm{hit}}c_*/4\le c_{\mathrm{hit}}/4<c_{\mathrm{hit}}$. The number $\alpha_0$ depends only on universal constants.

**Step 2 (decomposition).** Fix $N\ge1$ and $\Sigma\in\mathcal C_N$, singular or not. Since $\alpha_0\in(0,\alpha_1]$, the sparse lemma provides a probability measure $\pi=\pi_{\alpha_0,N,\Sigma}$ on the positive classes of $\Sigma$, depending only on $(\alpha_0,N,\Sigma)$ and not on $T$. Let $h=h_{\alpha_0,\pi,c_{\mathrm{hit}}}$ be its hitting mass. With $q=\alpha_0$ and $c=c_{\mathrm{hit}}$, the hitting mass $h(T)$ of the transfer lemma for this same $\pi$ is the same function of $T$: both use $\mathcal A=\mathcal R_{\alpha_0}(p)$, $r=|\mathcal A|$, the same set $\{S:|\mathcal A\cap S|\ge\max(1,c_{\mathrm{hit}}|S|r/N)\}$ on $E_{\alpha_0}$, and the value $0$ off $E_{\alpha_0}$ (the two descriptions of $E_{\alpha_0}$ agree by the preliminary). Also the event $D_{\alpha_0,\delta_0}$ of the sparse lemma is literally the event $D_{q,\delta}$ of the dense lemma at $q=\alpha_0$, $\delta=\delta_0$. Every sample point of $E_{\alpha_0}$ either lies in $D_{\alpha_0,\delta_0}$, or lies outside it and has $h(T)\ge c_*$ or $h(T)<c_*$. Hence, pointwise,
$$
E_{\alpha_0}\subseteq D_{\alpha_0,\delta_0}\ \cup\ \bigl(E_{\alpha_0}\cap\{h(T)\ge c_*\}\bigr)\ \cup\ \Bigl(\bigl(E_{\alpha_0}\setminus D_{\alpha_0,\delta_0}\bigr)\cap\{h(T)<c_*\}\Bigr).
$$
All these sets are Borel in $T$: $p$ is continuous in $T$, $E_{\alpha_0}$ and $D_{\alpha_0,\delta_0}$ are finite Boolean combinations of sets $\{p_i\le t\}$, and $h(T)$ is a finite sum, over the finitely many positive classes $S$, of $\pi(\{S\})$ times the indicator of an event of the same kind.

**Step 3 (three bounds).** (a) The dense lemma applies with $q=\alpha_0\in(0,q_D]$ and $\delta=\delta_0\in(0,1]$, for every $N$ and every $\Sigma\in\mathcal C_N$:
$$
\mathbb P_{N,0,\Sigma}(D_{\alpha_0,\delta_0})\le C_D\alpha_0\le\frac14.
$$
(b) The transfer lemma applies with $q=\alpha_0\in(0,1)$, $c=c_{\mathrm{hit}}\in(0,1]$, $q<c$ (Step 1), the deterministic probability measure $\pi$ on positive classes of $\Sigma$ from Step 2, and $c_*\in(0,1]$:
$$
\mathbb P_{N,0,\Sigma}\bigl(E_{\alpha_0}\cap\{h(T)\ge c_*\}\bigr)\le\frac{\alpha_0}{c_{\mathrm{hit}}c_*}\le\frac14 .
$$
(c) The sparse lemma, with $\alpha=\alpha_0\in(0,\alpha_1]$ and the measure $\pi=\pi_{\alpha_0,N,\Sigma}$ it provides, gives
$$
\mathbb P_{N,0,\Sigma}\bigl(E_{\alpha_0}\setminus D_{\alpha_0,\delta_0},\ h(T)<c_*\bigr)\le\frac14 .
$$
By the inclusion of Step 2 and the union bound, $\mathbb P_{N,0,\Sigma}(E_{\alpha_0})\le3/4$. Since $N$ and $\Sigma\in\mathcal C_N$ were arbitrary, and $E_{\alpha_0}$ is the event of the amplification lemma by the preliminary,
$$
B(\alpha_0)=\sup_{N\ge1}\sup_{\Sigma\in\mathcal C_N}\mathbb P_{N,0,\Sigma}(E_{\alpha_0})\le\frac34 .
$$

**Step 4 (amplification).** The amplification lemma applies with $\alpha_0\in(0,1)$ (indeed $\alpha_0\le1/4$) and $\delta=1/4\in(0,1)$, since $B(\alpha_0)\le3/4=1-\delta$. It gives
$$
B(t)\le\frac{2\log 4}{\alpha_0}\,t\qquad\text{for every }t\in(0,\alpha_0/2].
$$

**Step 5 (conclusion).** Put $q_0=\alpha_0/2$ and $C=2\log4/\alpha_0$. Then $0<q_0\le1/8<1/2$ and $0<C<\infty$, and both depend only on the universal constants of the route lemmas, so they are independent of $N$, $\Sigma$, its rank and its correlations. Let $N\ge1$, $\Sigma\in\mathcal C_N$ (singular allowed) and $0<q\le q_0$. The target event $\{\exists k\in[N]:p^{(1)}_{(k)}\le qk/N\}$, with non-strict comparisons and order statistics counted with multiplicity, is exactly $E_q$ of the amplification lemma. Therefore
$$
\mathbb P_{N,0,\Sigma}\Bigl(\exists k\in[N]:p^{(1)}_{(k)}\le\frac{qk}{N}\Bigr)=\mathbb P_{N,0,\Sigma}(E_q)\le B(q)\le Cq .
$$
For the BH form: $q\in(0,1)$, so $\mathcal R_q^{(1)}=\mathcal R_q(p^{(1)})$ is defined, and by the preliminary $R_q^{(1)}\ge1$ exactly on $E_q$. With $\theta=0$ every index satisfies $\theta_i\le0$, so $I_0^{(1)}(0)=[N]$, $V_q^{(1)}=|\mathcal R_q^{(1)}\cap[N]|=R_q^{(1)}$, and $V_q^{(1)}/(R_q^{(1)}\vee1)=\mathbf 1\{R_q^{(1)}\ge1\}$. Taking expectations,
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,0,\Sigma)=\mathbb P_{N,0,\Sigma}(R_q^{(1)}\ge1)=\mathbb P_{N,0,\Sigma}(E_q)\le Cq .
$$
This is the target statement with the universal constants $C=2\log4/\alpha_0$ and $q_0=\alpha_0/2$. $\square$

## Reduction verdict

confirmed

1. Preliminary. For $p\in[0,1]^N$ and $\alpha\in(0,1)$, the identity $\{\exists k:p_{(k)}\le\alpha k/N\}=\{\widehat k_\alpha\ge1\}=\{|\mathcal R_\alpha(p)|\ge1\}$ follows directly from the BH definition: the maximal qualifying rank $\widehat k_\alpha$ is at least any qualifying $k$, and the indices of $p_{(1)},\ldots,p_{(\widehat k_\alpha)}$ all lie below $\alpha\widehat k_\alpha/N$. So the event $E_\alpha$ means the same thing in the target, the amplification lemma, the transfer lemma and the sparse lemma. The one-sided p-values lie in $(0,1)$.
2. Step 1. Every entry of the minimum defining $\alpha_0$ is a positive universal constant. The four inequalities used later all hold: $\alpha_0\le\alpha_1$, $\alpha_0\le q_D$, $C_D\alpha_0\le1/4$, and $\alpha_0/(c_{\mathrm{hit}}c_*)\le1/4$. Also $\alpha_0\le c_{\mathrm{hit}}c_*/4<c_{\mathrm{hit}}$, which is the transfer lemma's strict hypothesis $q<c$. Assuming $C_D\ge1$ is harmless and is not actually needed.
3. Step 2. The sparse lemma's $\pi_{\alpha_0,N,\Sigma}$ is a deterministic probability measure on positive classes. The two lemmas define a positive class identically: nonempty, with $\Sigma_{ij}\ge0$ on $S$. So $\pi$ is admissible in the transfer lemma, which allows dependence on $N$, $\Sigma$ and constants. The two hitting masses are literally the same function of $T$: the same $\mathcal A=\mathcal R_{\alpha_0}(p)$, $r$, threshold $\max(1,c_{\mathrm{hit}}|S|r/N)$, and value $0$ off $E_{\alpha_0}$. The dense and sparse events $D_{\alpha_0,\delta_0}$ coincide, with the same $u_{\alpha_0}=\overline\Phi^{-1}(\alpha_0)$ and the same non-strict conditions. The three-way inclusion is a tautology: split $E_{\alpha_0}$ by $D$, then split the part outside $D$ by $h\ge c_*$ versus $h<c_*$. The measurability remark is correct, since every event is a finite Boolean combination of sets $\{p_i\le t\}$.
4. Step 3. (a) The dense lemma needs $\delta\in(0,1]$ and $q\in(0,q_D]$, and both hold. (b) The transfer lemma needs $q\in(0,1)$, $c\in(0,1]$, $q<c$, a deterministic $\pi$ and $c_*\in(0,1]$, and all hold. (c) The sparse lemma needs $\alpha\in(0,\alpha_1]$ and is applied with its own $\pi$, the same $\pi$ used in (b). Note the quantifier order: there the constants come first and then $\pi$ for each $(\alpha,N,\Sigma)$, which is exactly how it is used. The union bound gives $\mathbb P(E_{\alpha_0})\le3/4$ for every $N$ and $\Sigma$, singular included, hence $B(\alpha_0)\le3/4$.
5. Step 4. The amplification lemma applies with $\alpha_0\in(0,1)$ and $\delta=1/4$, since $B(\alpha_0)\le1-\delta$. It yields $B(t)\le(2\log4/\alpha_0)t$ on $(0,\alpha_0/2]$.
6. Step 5. The constants are $q_0=\alpha_0/2\in(0,1/8]\subset(0,1/2)$ and $C=2\log4/\alpha_0\in(0,\infty)$; both are universal. For $0<q\le q_0$ the target event, with non-strict comparisons and multiplicities, is exactly $E_q$, so $\mathbb P(E_q)\le B(q)\le Cq$. For the BH/FDR form, $I_0^{(1)}(0)=[N]$ because $\theta_i=0\le0$. Then $V_q^{(1)}=R_q^{(1)}$ and $V/(R\vee1)=\mathbf 1\{R\ge1\}$, so the FDR equals $\mathbb P(R_q^{(1)}\ge1)=\mathbb P(E_q)$ by the preliminary.

Every lemma is used only through its statement, and the exact target statement follows. The mathematical weight lies entirely in the sparse positive-class hitting lemma and the cover transfer lemma, not in this reduction.

## Dropped

The researcher asked (12 November 2026) to replace the stuck routes with a round built on the Schur-square tensor-lift idea; this route waits on a lemma that was set aside.
