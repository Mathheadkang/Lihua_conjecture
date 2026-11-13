---
type: plan
title: >-
  Route to gaussian_simes_one_sided_uniform_linear_bound via a dense tilt bound,
  a fixed-level sparse-crossing cap and amplification
status: abandoned
target_asset: gaussian_simes_one_sided_uniform_linear_bound
route_lemmas:
  - gaussian_simes_fixed_level_amplification
  - gaussian_simes_dense_crossing_tilt_bound
  - gaussian_simes_sparse_crossing_fixed_level_cap
route_title: dense tilt plus fixed-level sparse cap
origin: agent
inspired_by:
  - idea_c36aadbe5f06
  - idea_7d0a17e5c13c
  - idea_8699fa13f1f6
  - idea_a2ee64f07126
  - idea_9dc45fd77c4b
  - idea_10f14a1fa91d
  - idea_fc8702e63d1e
  - idea_4d3b81529002
tags:
  - route
  - simes
route_round: 1
reduction_digest: 7fb6a3852e7c68823c427b2b8dcd98fae24130587bfa9754fe05c000807ce9db
reduction_inputs:
  gaussian_simes_one_sided_uniform_linear_bound: 056ac9e2897851e7a490dc0b61a7810240e679307e0595cf07ea9c09c0ec8abc
  gaussian_simes_fixed_level_amplification: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
  gaussian_simes_dense_crossing_tilt_bound: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
  gaussian_simes_sparse_crossing_fixed_level_cap: e02ea4068f860cd39643c688ca2deec7a6b3a9f5aedc920fd92281c915d2d7f4
reduction_verified_digest: 7fb6a3852e7c68823c427b2b8dcd98fae24130587bfa9754fe05c000807ce9db
reduction_checked: true
---

## Goal

Target: [gaussian_simes_one_sided_uniform_linear_bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md)

Prove the uniform linear Simes bound by establishing a dimension-free bound strictly below one at a single fixed level, and then amplifying it. At that level, every crossing is either dense, with threshold within one unit of $u_q=\overline\Phi^{-1}(q)$, or sparse. Dense crossings are paid by the log-convex tilt. Sparse crossings need only a uniform cap below one, not a rate.

## Route

- gaussian_simes_fixed_level_amplification: turns $B(\alpha_0)\le1-\delta$ at one level into $B(t)\le(2\log(1/\delta)/\alpha_0)\,t$ for $t\le\alpha_0/2$ (step 4).
- gaussian_simes_dense_crossing_tilt_bound: with $\delta=1$, bounds the dense part $D_{q,1}$ of the Simes event by $C_Dq$ (step 2).
- gaussian_simes_sparse_crossing_fixed_level_cap: bounds the complementary sparse part $S_q$ by $1-\eta$ uniformly (step 2). It is the crux. Its motivation explains why it should be attacked with the hard (min-entropy) penalty rather than the exponential Gibbs kernel, which loses the Mills factor.

## Plan

1. [x] Event split. Write $N_k=\#\{i:p_i\le qk/N\}$. Since order statistics are counted with multiplicity, $p_{(k)}\le qk/N$ holds if and only if $N_k\ge k$, so $E_q=\{\exists k:N_k\ge k\}$. Every $k$ satisfies exactly one of $qk/N\ge\overline\Phi(u_q+1)$ and $qk/N<\overline\Phi(u_q+1)$. Hence $E_q=D_{q,1}\cup S_q$, with $D_{q,1}$ as in the dense lemma at $\delta=1$ and $S_q$ as in the sparse lemma, for every $N$, every $\Sigma\in\mathcal C_N$ and every $q\in(0,1)$.
2. [x] Fixed-level bound. For $q\le\min(q_D,q_S)$, step 1 and the two lemmas give $\mathbb P_{N,0,\Sigma}(E_q)\le C_Dq+1-\eta$ for all $N$ and $\Sigma$. Set $\alpha_0=\min(q_D,q_S,\eta/(2C_D))$. Then $B(\alpha_0)\le1-\eta/2$, where $B$ is the supremum in the amplification lemma.
3. [x] Admissibility check. $\alpha_0\in(0,1/4]$ and $\eta/2\in(0,1)$, so the amplification lemma applies with $\delta=\eta/2$. Its supremum ranges over the same class $\mathcal C_N$, singular matrices included, and its event uses the same non-strict comparisons as the target.
4. [x] Amplification. The lemma gives $B(t)\le C t$ for $0<t\le q_0$, with $C=2\log(2/\eta)/\alpha_0$ and $q_0=\alpha_0/2\in(0,1/8]$. These constants are universal because $C_D,q_D,q_S,\eta$ are.
5. [x] BH form. All coordinates are true nulls, so $V_q^{(1)}=R_q^{(1)}$ and $V/(R\vee1)=\mathbf 1\{R_q^{(1)}\ge1\}$. In the BH definition, $\widehat k_q>0$ exactly on $E_q$, and then $R_q^{(1)}\ge\widehat k_q\ge1$. So $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)=\mathbb P(R_q^{(1)}\ge1)=\mathbb P(E_q)\le Cq$.

## Reduction

Throughout, the three route lemmas [gaussian_simes_fixed_level_amplification](../assets/gaussian_simes_fixed_level_amplification.md), [gaussian_simes_dense_crossing_tilt_bound](../assets/gaussian_simes_dense_crossing_tilt_bound.md) and [gaussian_simes_sparse_crossing_fixed_level_cap](../assets/gaussian_simes_sparse_crossing_fixed_level_cap.md) are used as black boxes, by their statements only. Let $C_D,q_D$ be the universal constants of the dense lemma and $q_S,\eta$ those of the sparse lemma. Enlarging $C_D$ keeps the dense lemma true, so we may and do assume $C_D\ge1$. Fix a positive integer $N$ and $\Sigma\in\mathcal C_N$ (singular matrices allowed), let $T\sim\mathcal N_N(0,\Sigma)$ and $p_i=p_i^{(1)}=\overline\Phi(T_i)$, with order statistics $p_{(1)}\le\cdots\le p_{(N)}$ counted with multiplicity. For $q\in(0,1)$ put $u_q=\overline\Phi^{-1}(q)$,
$$
N_k=\#\Bigl\{i\in[N]:p_i\le\frac{qk}{N}\Bigr\},\qquad
E_q=\Bigl\{\exists k\in[N]:p_{(k)}\le\frac{qk}{N}\Bigr\}.
$$
This $E_q$ is the event of the target and coincides with the event $E_\alpha$ of the amplification lemma at $\alpha=q$, both with non-strict comparisons.

**Step 1 (event split).** For each $k\in[N]$ and each realization, $p_{(k)}\le qk/N$ if and only if $N_k\ge k$. Indeed, if $p_{(k)}\le qk/N$ then the $k$ values $p_{(1)},\ldots,p_{(k)}$, which come from $k$ distinct indices because multiplicities are counted, are all at most $p_{(k)}\le qk/N$, so $N_k\ge k$. Conversely, if $N_k\ge k$ then at least $k$ indices have $p_i\le qk/N$, so the $k$-th smallest value satisfies $p_{(k)}\le qk/N$. Hence $E_q=\bigcup_{k\in[N]}\{N_k\ge k\}$. Split $[N]=K_{\mathrm d}\sqcup K_{\mathrm s}$ with $K_{\mathrm d}=\{k:qk/N\ge\overline\Phi(u_q+1)\}$ and $K_{\mathrm s}=\{k:qk/N<\overline\Phi(u_q+1)\}$; this is a partition because the two conditions are complementary. By the definitions in the two lemmas (the dense one with $\delta=1$),
$$
D_{q,1}=\bigcup_{k\in K_{\mathrm d}}\{N_k\ge k\},\qquad S_q=\bigcup_{k\in K_{\mathrm s}}\{N_k\ge k\},
$$
so $E_q=D_{q,1}\cup S_q$ exactly, for every $N$, every $\Sigma\in\mathcal C_N$ and every $q\in(0,1)$.

**Step 2 (fixed-level bound).** Let $0<q\le\min(q_D,q_S)$. The dense lemma applies with $\delta=1\in(0,1]$ and $q\in(0,q_D]$, and the sparse lemma applies with $q\in(0,q_S]$. By step 1 and the union bound,
$$
\mathbb P_{N,0,\Sigma}(E_q)\le\mathbb P_{N,0,\Sigma}(D_{q,1})+\mathbb P_{N,0,\Sigma}(S_q)\le C_Dq+1-\eta .
$$
Set
$$
\alpha_0=\min\Bigl(q_D,\ q_S,\ \frac{\eta}{2C_D}\Bigr).
$$
Then $\alpha_0>0$ since $q_D,q_S,\eta>0$ and $C_D<\infty$, and $\alpha_0\le\min(q_D,q_S)$, so the display applies at $q=\alpha_0$ and gives $\mathbb P_{N,0,\Sigma}(E_{\alpha_0})\le C_D\alpha_0+1-\eta\le\eta/2+1-\eta=1-\eta/2$. This holds for every $N\ge1$ and every $\Sigma\in\mathcal C_N$, because the constants of both lemmas are free of $N$, $\Sigma$, the signs of the correlations and the rank. Taking the supremum,
$$
B(\alpha_0)=\sup_{N\ge1}\ \sup_{\Sigma\in\mathcal C_N}\mathbb P_{N,0,\Sigma}(E_{\alpha_0})\le1-\frac{\eta}{2}.
$$

**Step 3 (admissibility).** We have $0<\alpha_0\le q_D\le1/4<1$, so $\alpha_0\in(0,1)$, and $\delta:=\eta/2\in(0,1/2)\subset(0,1)$ because $\eta\in(0,1)$. The supremum $B$ in the amplification lemma is over all $N\ge1$ and all $\Sigma\in\mathcal C_N$, singular matrices included, and its event $E_\alpha$ is the event $E_q$ above with non-strict comparisons, the same as in the target. Thus the hypothesis $B(\alpha_0)\le1-\delta$ of the amplification lemma is exactly what step 2 established.

**Step 4 (amplification).** The amplification lemma gives
$$
B(t)\le\frac{2\log(1/\delta)}{\alpha_0}\,t=\frac{2\log(2/\eta)}{\alpha_0}\,t\qquad\text{for every }t\in(0,\alpha_0/2].
$$
Put $C=2\log(2/\eta)/\alpha_0$ and $q_0=\alpha_0/2$. Since $2/\eta>2$, $\log(2/\eta)>0$, so $0<C<\infty$; and $0<q_0\le1/8$, so $q_0\in(0,1/2)$. Both depend only on $C_D,q_D,q_S,\eta$, hence are universal. For every $N$, every $\Sigma\in\mathcal C_N$ and every $0<q\le q_0$,
$$
\mathbb P_{N,0,\Sigma}\Bigl(\exists k\in[N]:p^{(1)}_{(k)}\le\frac{qk}{N}\Bigr)=\mathbb P_{N,0,\Sigma}(E_q)\le B(q)\le Cq,
$$
which is the first display of the target.

**Step 5 (BH form).** With $\theta=0$, the one-sided true-null set is $I_0^{(1)}(0)=\{i:0\le0\}=[N]$, so $V_q^{(1)}=|\mathcal R_q^{(1)}\cap[N]|=R_q^{(1)}$ and $V_q^{(1)}/(R_q^{(1)}\vee1)=\mathbf 1\{R_q^{(1)}\ge1\}$ (it is $0$ when $R_q^{(1)}=0$ and $R/R=1$ otherwise). By the BH definition, $\widehat k_q>0$ if and only if some $k\in[N]$ has $p_{(k)}\le qk/N$, that is, exactly on $E_q$. If $\widehat k_q=0$ the rejection set is empty and $R_q^{(1)}=0$. If $\widehat k_q>0$, then $p_{(\widehat k_q)}\le q\widehat k_q/N$, so by step 1 (with $k=\widehat k_q$) at least $\widehat k_q$ indices satisfy $p_i\le q\widehat k_q/N$, and all of them lie in $\mathcal R_q^{(1)}$; hence $R_q^{(1)}\ge\widehat k_q\ge1$. Therefore $\{R_q^{(1)}\ge1\}=E_q$, and for $0<q\le q_0$,
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,0,\Sigma)=\mathbb E_{N,0,\Sigma}\bigl[\mathbf 1\{R_q^{(1)}\ge1\}\bigr]=\mathbb P_{N,0,\Sigma}(R_q^{(1)}\ge1)=\mathbb P_{N,0,\Sigma}(E_q)\le Cq .
$$
This is the second display of the target, with the same universal constants $C$ and $q_0$, valid for every $N$ and every $\Sigma\in\mathcal C_N$, with $N$ and $\Sigma$ allowed to depend on $q$. The target follows from the three route lemmas. $\square$

## Verification

Step 1 is an exact set identity, so no rank or threshold window is double-counted or lost. The dense lemma holds for every $\delta\in(0,1]$ and $q\le q_D$; the sparse lemma holds for every $q\le q_S$. Both hold for every $N$ and every $\Sigma\in\mathcal C_N$ with constants free of $N$, $\Sigma$ and signs, so step 2 bounds the supremum $B(\alpha_0)$ and not just a fixed model. The amplification lemma needs only $B(\alpha_0)\le1-\delta$ with $\delta\in(0,1)$ and does not need the supremum to be attained. Steps 4 and 5 then give the displayed bound $\mathbb P_{N,0,\Sigma}(\exists k:p^{(1)}_{(k)}\le qk/N)\le Cq$ and its BH reformulation for all $0<q\le q_0$, with $q_0<1/2$. That is the exact statement of the target.

## Difference from failed plans

There are no failed plan IDs; the two earlier attempts ended with no plan.

- First no-plan report (dense tilt settled, sparse crossings cost about $q$ per window over $\log N$ windows): this route never sums over windows. Through the all-or-nothing law, sparse crossings need only a uniform cap $1-\eta$ at one level, which is isolated as the single crux lemma.
- Second no-plan report (the Gibbs exponential kernel loses a $\sqrt{\log N}$ Mills factor; the hinge tail needs a summable $C/a$ estimate over scales): the crux needs neither a tail rate nor a sum over scales. It is restricted to sparse thresholds above $u_q+1$, since the reused dense lemma removes the rest. Its motivation records why the hard min-entropy penalty, rather than the Kullback penalty, is the form of the Gibbs variational supremum to use.

## Reduction verdict

confirmed

- Step 1: the identity $\{p_{(k)}\le qk/N\}=\{N_k\ge k\}$ is correct with multiplicities counted, in both directions and with non-strict comparisons. The rank split $K_{\mathrm d}$ / $K_{\mathrm s}$ uses complementary conditions ($\ge$ and $<$ against $\overline\Phi(u_q+1)$). Unioning over each part gives exactly the event $D_{q,1}$ of the dense lemma (at $\delta=1$) and the event $S_q$ of the sparse lemma, as those statements write them. So $E_q=D_{q,1}\cup S_q$ holds for every $N$, every $\Sigma$ and every $q\in(0,1)$.
- Step 2: the hypotheses of both lemmas hold: $\delta=1\in(0,1]$, $q\le q_D$ and $q\le q_S$. The union bound gives $C_Dq+1-\eta$. Taking $C_D\ge1$ is legitimate, because enlarging the constant keeps an upper bound true, and it makes $\eta/(2C_D)$ well defined. Then $\alpha_0>0$ and $C_D\alpha_0\le\eta/2$, which gives $1-\eta/2$ for every $(N,\Sigma)$. Because the constants are uniform, the bound passes to the supremum $B(\alpha_0)$.
- Step 3: $\alpha_0\le q_D\le1/4$ gives $\alpha_0\in(0,1)$, and $\eta\in(0,1)$ gives $\delta=\eta/2\in(0,1)$. The event $E_\alpha$ and the supremum $B$ in the amplification lemma are the same objects as in the target: one-sided p-values, non-strict comparisons, singular $\Sigma$ included, all $N\ge1$. So that lemma's hypothesis is met as stated.
- Step 4: the conclusion $B(t)\le(2\log(2/\eta)/\alpha_0)t$ for $t\in(0,\alpha_0/2]$ gives $C=2\log(2/\eta)/\alpha_0\in(0,\infty)$ (since $\log(2/\eta)>0$) and $q_0=\alpha_0/2\le1/8$, so $q_0\in(0,1/2)$. Both depend only on the lemmas' universal constants. For each fixed $(N,\Sigma)$ and $q\le q_0$, $\mathbb P_{N,0,\Sigma}(E_q)\le B(q)\le Cq$. This is the first display, with the target's quantifier order: the constants come first, and then $N$ and $\Sigma$ may depend on $q$.
- Step 5: with $\theta=0$, $I_0^{(1)}(0)=[N]$, so $V=R$ and $V/(R\vee1)=\mathbf 1\{R\ge1\}$. From the BH definition, $\widehat k_q>0$ exactly on $E_q$. In that case Step 1 applied at $k=\widehat k_q$ gives $R\ge\widehat k_q\ge1$; otherwise $R=0$. So $\{R_q^{(1)}\ge1\}=E_q$, and the FDR form follows with the same constants.
- Each lemma is used only through its statement, and no step rests on an idea node. Amplification comes from the lemma, not from idea_8699fa13f1f6. The whole weight of the route sits on the unproved sparse cap lemma, which is outside what this check covers.

## Dropped

The researcher asked (12 November 2026) to replace the stuck routes with a round built on the Schur-square tensor-lift idea; this route waits on a lemma that was set aside.
