---
type: plan
title: >-
  Route to gaussian_simes_one_sided_uniform_linear_bound via compact loaded
  all-null arrays, a Schur-path variation budget at maximizers and amplification
status: pending
target_asset: gaussian_simes_one_sided_uniform_linear_bound
route_lemmas:
  - gaussian_simes_fixed_level_amplification
  - gaussian_simes_schur_array_compactification
  - gaussian_simes_schur_array_maximizer_variation
route_title: Schur path at compact extremal arrays
origin: agent
inspired_by:
  - idea_6b48b2fe25e1
  - idea_a0805e98f90d
tags:
  - route
  - simes
  - schur_square_path
  - compactness
route_round: 2
reduction_digest: fccd259e326771ede7fa58a9c4df8823daefdfa4b86f3c2ea15b38a95183918e
reduction_inputs:
  gaussian_simes_one_sided_uniform_linear_bound: 056ac9e2897851e7a490dc0b61a7810240e679307e0595cf07ea9c09c0ec8abc
  gaussian_simes_fixed_level_amplification: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
  gaussian_simes_schur_array_compactification: 3ff8e143d2d88073822e605c70956af7082d952917d813001866b18b04299581
  gaussian_simes_schur_array_maximizer_variation: f01c086658ebe5ee56008da39f09da391f92f318f7cc20925eb9bfdef2f5102a
reduction_verified_digest: fccd259e326771ede7fa58a9c4df8823daefdfa4b86f3c2ea15b38a95183918e
reduction_checked: true
---

## Goal

Target: [gaussian_simes_one_sided_uniform_linear_bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md)

Prove a dimension-free bound strictly below one at one fixed level, then amplify. The bound comes from the Schur-square path $R_t=(1-t)\Sigma+t(\Sigma\circ\Sigma)$ by compactness. At a small common loading $\sigma$, all-null exchangeable arrays form a compact set. The Schur path acts continuously on this set and ends where the Simes size is at most $q$, and the loaded supremum is attained there. So it suffices to bound the downward variation along the path from a maximizer, uniformly as $\sigma\downarrow0$. That bound is the weak variant $q_*+\mathcal V_-<1$ of the assertion (SV). It is meant to be proved by contradiction: a sequence of maximizers violating it is extracted, and rigidity of the limit is used.

## Route

- gaussian_simes_fixed_level_amplification: turns $B(q_*)\le1-\delta$ into $B(t)\le(2\log(1/\delta)/q_*)\,t$ for $t\le q_*/2$ (step 4).
- gaussian_simes_schur_array_compactification: gives the compact all-null arrays, the continuous Schur path on them with endpoint value at most $q$, the attained loaded supremum $B^\sigma(q)$, and $B^\sigma(q)\to B(q)$ as $\sigma\downarrow0$ (steps 1-3).
- gaussian_simes_schur_array_maximizer_variation: bounds $q_*+\mathcal V_-$ along the Schur path from every loaded maximizer by $1-\delta$, uniformly for $\sigma\le\sigma_0$ (step 2). This is the crux.

## Plan

1. [x] Maximizers exist. Fix $q_*,\sigma_0,\delta$ from the variation lemma and let $\sigma\in(0,\sigma_0]$. Since $q_*\in(0,1/4]$, part 5 of the compactification lemma gives $P^*\in\mathfrak P_0$ with $\Phi_\sigma(P^*;q_*)=\max_{\mathfrak P_0}\Phi_\sigma(\cdot\,;q_*)=B^\sigma(q_*)$. By part 2, $f=f^\sigma_{P^*,q_*}$ is a real function on $[0,1]$ with $f(0)=\Phi_\sigma(S_0P^*;q_*)=B^\sigma(q_*)$ (part 1: $S_0P^*=P^*$). By part 3, $f(1)\le q_*$.
2. [x] Loaded fixed-level bound. The trivial partition $\{0,1\}$ gives $f(0)-f(1)\le[f(0)-f(1)]_+\le\mathcal V_-(f)$. By the variation lemma applied to $P^*$,
$$
B^\sigma(q_*)=f(0)\le f(1)+\mathcal V_-(f)\le q_*+\mathcal V_-(f)\le1-\delta,
$$
for every $\sigma\in(0,\sigma_0]$.
3. [x] Remove the loading. By part 6 of the compactification lemma at $q=q_*$, $B(q_*)=\lim_{\sigma\downarrow0}B^\sigma(q_*)\le1-\delta$. Here $B(q_*)$ is exactly the supremum $B(\alpha_0)$ of the amplification lemma at $\alpha_0=q_*$. Both are over all $N\ge1$ and all $\Sigma\in\mathcal C_N$, singular included, with the same one-sided event and non-strict comparisons.
4. [x] Amplification. Since $q_*\in(0,1)$ and $\delta\in(0,1)$, the amplification lemma gives $B(t)\le C t$ for $0<t\le q_0$. Here $C=2\log(1/\delta)/q_*\in(0,\infty)$ and $q_0=q_*/2\in(0,1/8]$, so $q_0<1/2$. Both are universal. Hence $\mathbb P_{N,0,\Sigma}(\exists k:p^{(1)}_{(k)}\le qk/N)\le B(q)\le Cq$ for every $N$, every $\Sigma\in\mathcal C_N$ and every $q\in(0,q_0]$.
5. [x] BH form. With $\theta=0$, every coordinate is a one-sided true null, so $V^{(1)}_q=R^{(1)}_q$ and the FDP is $\mathbf 1\{R^{(1)}_q\ge1\}$. By the BH definition, $\widehat k_q>0$ exactly on the Simes event, and then $R^{(1)}_q\ge\widehat k_q\ge1$; otherwise $R^{(1)}_q=0$. So $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)=\mathbb P(R^{(1)}_q\ge1)\le Cq$.

## Verification

- Steps 1-2 use only the existence of the attained maximum, the continuity of the path function (so $\mathcal V_-$ is that of a genuine real function), the Schur endpoint bound and the definition of downward variation. Together they bound the supremum $B^\sigma(q_*)$ over all finite loaded models, not a single model.
- Step 3 passes to $\sigma\downarrow0$ in value only. No continuity of the population functional at $\sigma=0$ is needed.
- Step 4 needs only $B(\alpha_0)\le1-\delta$ with $\alpha_0,\delta\in(0,1)$. Step 5 is the exact all-null identity between FDR and rejection probability.
- The constants $C$ and $q_0$ depend only on $q_*$ and $\delta$. They hold for every $N$ and every $\Sigma\in\mathcal C_N$, including singular matrices, with $N$ and $\Sigma$ allowed to depend on $q$. This is the target statement in both of its displays.
- The Schur path in the compactification is the path of the idea applied to the residual correlation. At $\sigma=0$ it is $R_t$ itself (part 4 with $\sigma\to0$), and exact clones stay tied along it.

## Difference from failed plans

No plan for this target has failed. The three round-one routes were dropped at the researcher's request (12 November 2026).

- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s1_sparse_fixed_level_cap: that route needed a direct cap on sparse crossings under arbitrary correlation. This route moves to a nonnegative-correlation endpoint along the Schur path. It needs control of the downward variation only at compact extremal objects, where maximality inequalities are available.
- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s2_positive_class_cover: that route covered sparse crossings by random positive classes. Here the positivity comes from the deterministic Schur square $\Sigma\circ\Sigma$, with no cover or hitting estimate.
- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s3_mills_penalized_subset_acceptance: that route needed acceptance for a penalized subset supremum, which clones plus independent coordinates obstruct (idea_b57684f6c514). Exact clones are fixed points of the Schur path here, and the two-clone benchmark of idea_a0805e98f90d is consistent with the budget.

## Reduction

The three route lemmas are used as black boxes, each by its statement: [the fixed-level amplification](../assets/gaussian_simes_fixed_level_amplification.md), [the Schur-path array compactification](../assets/gaussian_simes_schur_array_compactification.md) (parts 1-6), and [the maximizer variation budget](../assets/gaussian_simes_schur_array_maximizer_variation.md). Notation is that of the compactification. For $q\in(0,1)$, $N\ge1$ and $\Sigma\in\mathcal C_N$, the quantity $F_q(\Sigma)$ of the compactification is exactly $\mathbb P_{N,0,\Sigma}(E_q)$ in the amplification lemma, since both use $T\sim\mathcal N_N(0,\Sigma)$, the one-sided p-values $p_i=\overline\Phi(T_i)$, order statistics with multiplicity and non-strict comparisons $p_{(k)}\le qk/N$. Hence the supremum $B(q)$ of the compactification coincides with the supremum $B(q)$ of the amplification lemma, both being taken over all $N\ge1$ and all $\Sigma\in\mathcal C_N$, singular included. It is also the supremum of the probability on the left of the target's first display.

**Step 1 (maximizers exist).** Let $q_*\in(0,1/4]$, $\sigma_0\in(0,1)$ and $\delta\in(0,1)$ be the constants given by the variation lemma. Fix $\sigma\in(0,\sigma_0]$. Then $\sigma\in(0,1)$ and $q_*\in(0,1/4]$, so the compactification lemma applies at $(\sigma,q_*)$. By its part 5 the maximum of $\Phi_\sigma(\cdot\,;q_*)$ over $\mathfrak P_0$ exists and equals $B^\sigma(q_*)$. Choose $P^*\in\mathfrak P_0$ attaining it:
$$
\Phi_\sigma(P^*;q_*)=\max_{P\in\mathfrak P_0}\Phi_\sigma(P;q_*)=B^\sigma(q_*).
$$
By part 2, $f:=f^\sigma_{P^*,q_*}$, $f(t)=\Phi_\sigma(S_tP^*;q_*)$, is a well-defined real (indeed continuous) function on $[0,1]$. By part 1, $S_0P^*=P^*$, so $f(0)=\Phi_\sigma(P^*;q_*)=B^\sigma(q_*)$. By part 3 applied to $P^*$, $f(1)=\Phi_\sigma(S_1P^*;q_*)\le q_*$.

**Step 2 (loaded fixed-level bound).** In the definition of $\mathcal V_-$ take the partition with $m=1$, $t_0=0$, $t_1=1$. This gives
$$
f(0)-f(1)\le[f(0)-f(1)]_+\le\mathcal V_-(f).
$$
The maximizer $P^*$ satisfies the hypothesis of the variation lemma at the level $q_*$ and loading $\sigma\in(0,\sigma_0]$, so $q_*+\mathcal V_-(f)\le1-\delta$; in particular $\mathcal V_-(f)<\infty$. Combining with Step 1,
$$
B^\sigma(q_*)=f(0)\le f(1)+\mathcal V_-(f)\le q_*+\mathcal V_-(f)\le1-\delta .
$$
This holds for every $\sigma\in(0,\sigma_0]$, with $\delta$ independent of $\sigma$.

**Step 3 (removal of the loading).** By part 6 of the compactification lemma at $q=q_*$, $\lim_{\sigma\downarrow0}B^\sigma(q_*)=B(q_*)$. The limit runs along $\sigma\in(0,\sigma_0]$, where Step 2 gives $B^\sigma(q_*)\le1-\delta$, so
$$
B(q_*)\le1-\delta .
$$
Only the limit of values is used.

**Step 4 (amplification).** Put $\alpha_0=q_*$. Then $\alpha_0\in(0,1/4]\subset(0,1)$, $\delta\in(0,1)$, and by Step 3 and the identification of the two suprema, $B(\alpha_0)\le1-\delta$. The amplification lemma gives
$$
B(t)\le\frac{2\log(1/\delta)}{q_*}\,t\qquad\text{for every }t\in(0,q_*/2].
$$
Set
$$
C=\frac{2\log(1/\delta)}{q_*},\qquad q_0=\frac{q_*}{2}.
$$
Since $\delta\in(0,1)$, $\log(1/\delta)\in(0,\infty)$, so $0<C<\infty$. Also $q_0\in(0,1/8]\subset(0,1/2)$. Both depend only on the constants $q_*,\delta$ of the variation lemma, so they are universal. Now let $N\ge1$, $\Sigma\in\mathcal C_N$ (singular allowed, and possibly depending on $q$) and $q\in(0,q_0]$. Then
$$
\mathbb P_{N,0,\Sigma}\Bigl(\exists k\in\{1,\ldots,N\}:p^{(1)}_{(k)}\le\frac{qk}{N}\Bigr)=F_q(\Sigma)\le B(q)\le Cq .
$$
This is the target's first display.

**Step 5 (BH form).** Keep $N$, $\Sigma$ and $q\in(0,q_0]\subset(0,1)$. With $\theta=0$, every index satisfies $\theta_i=0\le0$, so $I_0^{(1)}(0)=\{1,\ldots,N\}$ and $V^{(1)}_q=|\mathcal R^{(1)}_q\cap I_0^{(1)}(0)|=R^{(1)}_q$. Hence $V^{(1)}_q/(R^{(1)}_q\vee1)=\mathbf 1\{R^{(1)}_q\ge1\}$ and
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)=\mathbb P_{N,0,\Sigma}(R^{(1)}_q\ge1).
$$
By the BH definition applied to $p^{(1)}$, $\widehat k_q>0$ exactly when some $k$ satisfies $p^{(1)}_{(k)}\le qk/N$, that is, on the Simes event. If $\widehat k_q=0$ the rejection set is empty and $R^{(1)}_q=0$. If $\widehat k_q=\widehat k>0$, then $p^{(1)}_{(j)}\le p^{(1)}_{(\widehat k)}\le q\widehat k/N$ for $j=1,\ldots,\widehat k$, so the indices carrying the $\widehat k$ smallest order statistics (counted with multiplicity) are all rejected, and $R^{(1)}_q\ge\widehat k\ge1$. Thus $\{R^{(1)}_q\ge1\}$ equals the Simes event, and by Step 4
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)=\mathbb P_{N,0,\Sigma}(R^{(1)}_q\ge1)\le Cq .
$$
This is the target's second display, with the same universal constants $C$ and $q_0$, independent of $N$, the rank of $\Sigma$, and every other model parameter. $\square$

The dependencies of the compactification lemma (the approved array compactification and the positive-Gaussian Simes theorem) enter only through its statement; the reduction uses no further result.

## Reduction verdict

confirmed

Checked against the statements alone, step by step.

- Identification. $F_q(\Sigma)$ in the compactification, $\mathbb P_{N,0,\Sigma}(E_q)$ in the amplification lemma, and the probability in the target's first display are the same event: one-sided p-values $\overline\Phi(T_i)$, order statistics with multiplicity, non-strict comparisons $p_{(k)}\le qk/N$, $T\sim\mathcal N_N(0,\Sigma)$. So the two suprema $B(q)$ are the same quantity: a supremum over all $N\ge1$ and all $\Sigma\in\mathcal C_N$, singular included.
- Step 1. The variation lemma gives $q_*\in(0,1/4]$, $\sigma_0\in(0,1)$ and $\delta\in(0,1)$. For $\sigma\in(0,\sigma_0]$ the compactification's hypotheses $\sigma\in(0,1)$ and $q\in(0,1/4]$ hold at $(\sigma,q_*)$. Part 5 gives a maximizer $P^*$ with value $B^\sigma(q_*)$. Part 2 makes $f=f^\sigma_{P^*,q_*}$ a well-defined real function. Part 1 ($S_0P=P$) gives $f(0)=B^\sigma(q_*)$, and part 3 gives $f(1)\le q_*$.
- Step 2. The one-interval partition $0=t_0<t_1=1$ is admissible in the definition of $\mathcal V_-$, so $f(0)-f(1)\le\mathcal V_-(f)$. $P^*$ meets the variation lemma's only hypothesis (it attains $\max_{\mathfrak P_0}\Phi_\sigma(\cdot\,;q_*)$ with $\sigma\le\sigma_0$). Hence $B^\sigma(q_*)\le q_*+\mathcal V_-(f)\le1-\delta$, with $\delta$ independent of $\sigma$ and $P^*$. The inequalities point the right way.
- Step 3 (removal of the loading, the point flagged for scrutiny). In the compactification, $B^\sigma(q)$ is *defined* as the finite-model supremum $\sup_N\sup_{\Sigma}F_q((1-\sigma^2)\Sigma+\sigma^2\mathbf 1\mathbf 1^{\mathsf T})$, and $B(q)$ as the unloaded finite-model supremum $\sup_N\sup_\Sigma F_q(\Sigma)$. Part 6 states $\lim_{\sigma\downarrow0}B^\sigma(q)=B(q)$. So the limit is the unloaded finite-model supremum itself, not an array or population value at $\sigma=0$. Part 5 is used only to produce a maximizer for the loaded value at each fixed $\sigma>0$. A limit of numbers that are all at most $1-\delta$ on $(0,\sigma_0]$ is at most $1-\delta$, so $B(q_*)\le1-\delta$. The bound $B^\sigma\le B$ in part 6 points the useless way; the reduction correctly uses the limit statement. Part 6 is stated under the lemma's heading "Fix $\sigma$"; as written it is a claim about the function $\sigma\mapsto B^\sigma(q)$ at fixed $q$, which does not depend on the fixed $\sigma$, so reading it at $q=q_*$ is legitimate.
- Step 4. The amplification lemma's hypotheses hold: $\alpha_0=q_*\in(0,1)$, $\delta\in(0,1)$, and $B(\alpha_0)\le1-\delta$. It gives $B(t)\le Ct$ for $t\in(0,q_*/2]$ with $C=2\log(1/\delta)/q_*\in(0,\infty)$ and $q_0=q_*/2\in(0,1/8]\subset(0,1/2)$. The constants depend only on the variation lemma's fixed constants, so they are universal. Quantifier order matches the target: the constants come first, then the bound holds for every $N$, every $\Sigma$ (possibly chosen depending on $q$) and every $q\le q_0$, because it is a pointwise bound by the supremum $B(q)$.
- Step 5. With $\theta=0$, $I_0^{(1)}(0)=[N]$, so $V=R$ and $\operatorname{FDP}=\mathbf 1\{R\ge1\}$. From the BH definition, $\widehat k_q>0$ exactly on the Simes event. If $\widehat k>0$, then at least $\widehat k$ p-values lie at or below $q\widehat k/N$, so $R\ge1$; if $\widehat k_q=0$, then $R=0$. This gives the second display with the same constants.

No step needs more than the statement of a lemma. Of the compactification's parts, only 1 ($S_0P=P$), 2, 3, 5 and 6 are used.
