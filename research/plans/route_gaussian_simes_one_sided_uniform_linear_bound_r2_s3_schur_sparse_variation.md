---
type: plan
title: >-
  Route to gaussian_simes_one_sided_uniform_linear_bound via the dense tilt
  bound, a Schur-square downward-variation budget for sparse crossings, the
  positive-Gaussian Simes endpoint and amplification
status: pending
target_asset: gaussian_simes_one_sided_uniform_linear_bound
route_lemmas:
  - gaussian_simes_fixed_level_amplification
  - gaussian_simes_dense_crossing_tilt_bound
  - lib_chi2024_positive_gaussian_simes
  - gaussian_simes_schur_square_sparse_variation_budget
route_title: Schur-square path for sparse crossings
origin: agent
inspired_by:
  - idea_6b48b2fe25e1
  - idea_a0805e98f90d
  - idea_ec681eb191fb
tags:
  - route
  - simes
  - schur_square_path
route_round: 2
reduction_digest: 99dbda4fcb53e2cf97d540c9c2dac4ee7a3152009690c638482bcec9b22a2778
reduction_inputs:
  gaussian_simes_one_sided_uniform_linear_bound: 056ac9e2897851e7a490dc0b61a7810240e679307e0595cf07ea9c09c0ec8abc
  gaussian_simes_fixed_level_amplification: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
  gaussian_simes_dense_crossing_tilt_bound: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
  lib_chi2024_positive_gaussian_simes: ec28454a273facc776f366331e57e9607ec21259d9fb56b3c1a187d35b8007e9
  gaussian_simes_schur_square_sparse_variation_budget: 86f7bdd265309432fe20f975ae839c30202be6cc9ff8b792c372f7c4362c61e9
reduction_verified_digest: 99dbda4fcb53e2cf97d540c9c2dac4ee7a3152009690c638482bcec9b22a2778
reduction_checked: true
---

## Goal

Target: [gaussian_simes_one_sided_uniform_linear_bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md)

Prove a dimension-free bound strictly below one at one fixed level and amplify it. Split the Simes event into dense and sparse crossings. Dense crossings cost order $q$ under every correlation (approved). Sparse crossings are transported along the Schur-square path $R_t=(1-t)\Sigma+t(\Sigma\circ\Sigma)$ to a nonnegative correlation, where the positive-Gaussian Simes theorem gives size at most $q$. The only new input is a uniform bound below one on the downward variation of the sparse-crossing probability along that path.

## Route

- gaussian_simes_fixed_level_amplification: turns $B(\alpha_0)\le1-\delta$ at one level into $B(t)\le(2\log(1/\delta)/\alpha_0)\,t$ for $t\le\alpha_0/2$ (step 6).
- gaussian_simes_dense_crossing_tilt_bound: with $\delta=1$, bounds the dense part $D_{q,1}$ by $C_Dq$ at the starting matrix $\Sigma$ (step 5).
- lib_chi2024_positive_gaussian_simes: bounds the full Simes event, hence the sparse part, by $q$ at the endpoint $\Sigma\circ\Sigma$, whose entries are nonnegative (step 3).
- gaussian_simes_schur_square_sparse_variation_budget: the crux; bounds the downward variation of $t\mapsto\mathbb P_{R_t}(S_q)$ by $1-\eta$, so the sparse part at $\Sigma$ exceeds its endpoint value by at most $1-\eta$ (step 4).

## Plan

1. [x] Event split. With $N_k=\#\{i:p_i\le qk/N\}$, $p_{(k)}\le qk/N$ iff $N_k\ge k$ (multiplicities counted), so $E_q=\bigcup_k\{N_k\ge k\}$. Splitting the ranks by $qk/N\ge\overline\Phi(u_q+1)$ or $qk/N<\overline\Phi(u_q+1)$ gives $E_q=D_{q,1}\cup\{T\in S_q\}$ exactly, with $D_{q,1}$ as in the dense lemma at $\delta=1$ and $S_q$ the set of the variation lemma, for every $N$, every $\Sigma\in\mathcal C_N$ and every $q\in(0,1)$. In particular $\{T\in S_q\}\subseteq E_q$.
2. [x] Path admissibility. For $\Sigma=(\rho_{ij})\in\mathcal C_N$, the Schur product theorem gives $\Sigma\circ\Sigma\succeq0$; its diagonal is one and its entries $\rho_{ij}^2$ are nonnegative. Every $R_t=(1-t)\Sigma+t(\Sigma\circ\Sigma)$ is a convex combination of elements of $\mathcal C_N$, hence lies in $\mathcal C_N$; $R_0=\Sigma$ and $R_1=\Sigma\circ\Sigma$.
3. [x] Endpoint bound. Let $Y\sim\mathcal N_N(0,\Sigma\circ\Sigma)$ and $P_i=\overline\Phi(Y_i)$. Then $P$ is Gaussian dependent with latent correlation $\Sigma\circ\Sigma$ (all transforms nonincreasing; degenerate latent vectors allowed), with uniform margins, and $\{S_N(P)\le q\}=E_q$ for the Simes function $S_N(p)=\min_k Np_{(k)}/k$. The library theorem, whose hypothesis $(\Sigma\circ\Sigma)_{ij}\ge0$ holds, gives $f_{q,\Sigma}(1)=\mathbb P_{R_1}(T\in S_q)\le\mathbb P_{R_1}(E_q)\le q$ by step 1.
4. [x] Variation transfer. The trivial partition $\{0,1\}$ in the definition of $\mathcal V_-$ gives $f_{q,\Sigma}(0)-f_{q,\Sigma}(1)\le[f_{q,\Sigma}(0)-f_{q,\Sigma}(1)]_+\le\mathcal V_-(f_{q,\Sigma})$. With the variation lemma and step 3, for $q\le q_V$: $\mathbb P_{N,0,\Sigma}(T\in S_q)=f_{q,\Sigma}(0)\le q+1-\eta$. No regularity of $f_{q,\Sigma}$ is used.
5. [x] Fixed-level bound. For $q\le\min(q_D,q_V)$, steps 1 and 4 and the dense lemma (with $\delta=1$) give $\mathbb P_{N,0,\Sigma}(E_q)\le C_Dq+q+1-\eta$ for all $N$ and $\Sigma$, singular included. Put $\alpha_0=\min\bigl(q_D,q_V,\eta/(2(C_D+1))\bigr)$; then $B(\alpha_0)\le1-\eta/2$, with $B$ the supremum of the amplification lemma.
6. [x] Amplification. Since $\alpha_0\in(0,1/4]$ and $\eta/2\in(0,1)$, the amplification lemma with $\delta=\eta/2$ gives $B(t)\le Ct$ for $0<t\le q_0$, where $C=2\log(2/\eta)/\alpha_0$ and $q_0=\alpha_0/2\in(0,1/8]$; both are universal.
7. [x] BH form. All coordinates are true nulls, so $V_q^{(1)}=R_q^{(1)}$ and $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)=\mathbb P(R_q^{(1)}\ge1)=\mathbb P(E_q)\le Cq$, because $\widehat k_q>0$ exactly on $E_q$.

## Reduction

Every lemma is used only through its statement. Fix the universal constants $C_D<\infty$, $q_D\in(0,1/4]$ of [gaussian_simes_dense_crossing_tilt_bound](../assets/gaussian_simes_dense_crossing_tilt_bound.md) and $q_V\in(0,1/4]$, $\eta\in(0,1)$ of [gaussian_simes_schur_square_sparse_variation_budget](../assets/gaussian_simes_schur_square_sparse_variation_budget.md). Since a probability is nonnegative, the dense bound stays true with $C_D$ replaced by $C_D^+=\max(C_D,0)$, and we use $C_D^+$ below. Throughout, $N\ge1$, $\Sigma\in\mathcal C_N$ (singular allowed), $T\sim\mathcal N_N(0,\Sigma)$, $p_i=\overline\Phi(T_i)$ (the one-sided p-values $p_i^{(1)}$ of the target), $u_q=\overline\Phi^{-1}(q)$, and
$$
E_q=\Bigl\{\exists k\in[N]:p_{(k)}\le\frac{qk}{N}\Bigr\},\qquad N_k(c)=\#\{i\in[N]:p_i\le c\}.
$$
$E_q$ is literally the event of the target and the event $E_\alpha$ of [gaussian_simes_fixed_level_amplification](../assets/gaussian_simes_fixed_level_amplification.md) at $\alpha=q$.

**Step 1 (event split).** For any $c\in\mathbb R$ and $k\in[N]$, $p_{(k)}\le c$ if and only if $N_k(c)\ge k$: if $p_{(k)}\le c$ then $p_{(1)},\ldots,p_{(k)}$ are $k$ entries (with multiplicity) at most $c$; conversely, if at least $k$ entries are at most $c$, the $k$-th smallest entry is at most $c$. Hence $E_q=\bigcup_{k\in[N]}\{N_k(qk/N)\ge k\}$. Each rank $k$ satisfies exactly one of $qk/N\ge\overline\Phi(u_q+1)$ or $qk/N<\overline\Phi(u_q+1)$. The union over the first group of ranks is, by definition, the event $D_{q,1}$ of the dense lemma with $\delta=1$. The union over the second group is $\{T\in S_q\}$, with $S_q$ the set of the variation lemma, because $\overline\Phi(T_i)=p_i$. Therefore, for every $q\in(0,1)$,
$$
E_q=D_{q,1}\cup\{T\in S_q\},\qquad\text{in particular }\{T\in S_q\}\subseteq E_q .
$$
This holds pointwise for every realisation, hence under every law of $T$, in particular under $\mathcal N_N(0,R)$ for any $R\in\mathcal C_N$.

**Step 2 (path admissibility).** Write $\Sigma=(\rho_{ij})$. By the Schur product theorem $\Sigma\circ\Sigma\succeq0$; it is symmetric with diagonal entries $\rho_{ii}^2=1$, so $\Sigma\circ\Sigma\in\mathcal C_N$, and its entries $\rho_{ij}^2$ are nonnegative. Since $\mathcal C_N$ is convex (the defining conditions are linear equalities and the closed convex condition $x^{\mathsf T}\Sigma x\ge0$), $R_t^\Sigma=(1-t)\Sigma+t(\Sigma\circ\Sigma)\in\mathcal C_N$ for every $t\in[0,1]$, with $R_0^\Sigma=\Sigma$ and $R_1^\Sigma=\Sigma\circ\Sigma$. (The variation lemma records the same fact in its statement.) Thus $f_{q,\Sigma}(t)=\mathbb P_{N,0,R_t^\Sigma}(T\in S_q)$ is defined on $[0,1]$, and $f_{q,\Sigma}(0)=\mathbb P_{N,0,\Sigma}(T\in S_q)$.

**Step 3 (endpoint bound).** Let $Y\sim\mathcal N_N(0,\Sigma\circ\Sigma)$ and $P_i=\overline\Phi(Y_i)$. Each $Y_i$ has variance $(\Sigma\circ\Sigma)_{ii}=1>0$, so the latent correlation matrix of $Y$ is $\Sigma\circ\Sigma$, and $Y$ is jointly Gaussian (possibly degenerate, which the [Gaussian dependence definition](../library/chi2024_negative_dependence/definitions/lib_chi2024_gaussian_dependence.md) allows). The transforms $f_i=\overline\Phi$ are measurable and all nonincreasing, so $P\in\mathcal G_{\Sigma\circ\Sigma}$. Since $Y_i\sim\mathcal N(0,1)$ and $\overline\Phi$ is a continuous strictly decreasing bijection onto $(0,1)$, $\mathbb P(P_i\le s)=\mathbb P(Y_i\ge\overline\Phi^{-1}(s))=s$ for $s\in(0,1)$, so each $P_i$ is uniform on $[0,1]$ and $P\in\mathcal U^N$. With the Simes function $S_N(p)=\min_k Np_{(k)}/k$ of the [Simes function definition](../library/chi2024_negative_dependence/definitions/lib_chi2024_simes_function_uniform_pvalues.md), $S_N(P)\le q$ if and only if $Np_{(k)}/k\le q$ for some $k$, i.e. $P_{(k)}\le qk/N$ for some $k$; this is the event $E_q$ computed from $Y$ in place of $T$. The off-diagonal entries $\rho_{ij}^2$ of $\Sigma\circ\Sigma$ are nonnegative, so [lib_chi2024_positive_gaussian_simes](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) with $K=N$ and $\alpha=q\in(0,1)$ gives $\mathbb P_{N,0,\Sigma\circ\Sigma}(E_q)\le q$. By Step 1 under this law,
$$
f_{q,\Sigma}(1)=\mathbb P_{N,0,\Sigma\circ\Sigma}(T\in S_q)\le\mathbb P_{N,0,\Sigma\circ\Sigma}(E_q)\le q .
$$

**Step 4 (variation transfer).** The trivial partition $0=t_0<t_1=1$ ($m=1$) is admissible in the supremum defining $\mathcal V_-$, so
$$
f_{q,\Sigma}(0)-f_{q,\Sigma}(1)\le\bigl[f_{q,\Sigma}(0)-f_{q,\Sigma}(1)\bigr]_+\le\mathcal V_-(f_{q,\Sigma}).
$$
For $q\in(0,q_V]$ the variation lemma, applied to the given $\Sigma$ itself, gives $\mathcal V_-(f_{q,\Sigma})\le1-\eta$. With Step 3,
$$
\mathbb P_{N,0,\Sigma}(T\in S_q)=f_{q,\Sigma}(0)\le f_{q,\Sigma}(1)+1-\eta\le q+1-\eta\qquad(0<q\le q_V).
$$
No continuity or other regularity of $f_{q,\Sigma}$ is used.

**Step 5 (fixed-level bound).** Let $0<q\le\min(q_D,q_V)$. By Step 1, the union bound, the dense lemma with $\delta=1\in(0,1]$ (valid since $q\le q_D$), and Step 4,
$$
\mathbb P_{N,0,\Sigma}(E_q)\le\mathbb P_{N,0,\Sigma}(D_{q,1})+\mathbb P_{N,0,\Sigma}(T\in S_q)\le C_D^+q+q+1-\eta ,
$$
for every $N\ge1$ and every $\Sigma\in\mathcal C_N$, singular included. Put
$$
\alpha_0=\min\Bigl(q_D,\ q_V,\ \frac{\eta}{2(C_D^++1)}\Bigr).
$$
Then $0<\alpha_0\le q_D\le1/4$, and $(C_D^++1)\alpha_0\le\eta/2$, so $\mathbb P_{N,0,\Sigma}(E_{\alpha_0})\le1-\eta/2$ for every $N$ and $\Sigma\in\mathcal C_N$. Taking suprema, $B(\alpha_0)\le1-\eta/2$, with $B$ as in the amplification lemma.

**Step 6 (amplification).** We have $\alpha_0\in(0,1)$ and $\delta:=\eta/2\in(0,1/2)\subset(0,1)$ with $B(\alpha_0)\le1-\delta$. The amplification lemma gives
$$
B(t)\le\frac{2\log(2/\eta)}{\alpha_0}\,t\qquad\text{for every }t\in(0,\alpha_0/2].
$$
Set $C=2\log(2/\eta)/\alpha_0$ and $q_0=\alpha_0/2$. Since $\eta<1$, $\log(2/\eta)>\log2>0$, so $0<C<\infty$; and $q_0\in(0,1/8]\subset(0,1/2)$. Both depend only on $C_D,q_D,q_V,\eta$, hence are universal. For every $N\ge1$, every $\Sigma\in\mathcal C_N$ (singular included) and every $0<q\le q_0$,
$$
\mathbb P_{N,0,\Sigma}\Bigl(\exists k\in[N]:p^{(1)}_{(k)}\le\frac{qk}{N}\Bigr)=\mathbb P_{N,0,\Sigma}(E_q)\le B(q)\le Cq ,
$$
which is the first display of the target. As $q_0$ and $C$ do not depend on $N$ or $\Sigma$, these may vary arbitrarily with $q$.

**Step 7 (BH form).** With $\theta=0$, the one-sided true-null set is $I_0^{(1)}(0)=\{i:\theta_i\le0\}=[N]$, so $V_q^{(1)}=|\mathcal R_q^{(1)}\cap[N]|=R_q^{(1)}$ and
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,0,\Sigma)=\mathbb E\Bigl[\frac{R_q^{(1)}}{R_q^{(1)}\vee1}\Bigr]=\mathbb P_{N,0,\Sigma}(R_q^{(1)}\ge1),
$$
since the integrand is $1$ when $R_q^{(1)}\ge1$ and $0$ otherwise. By the BH definition, $\widehat k_q>0$ exactly when some $k$ has $p_{(k)}\le qk/N$, i.e. on $E_q$. If $\widehat k_q=0$ the rejection set is empty. If $\widehat k=\widehat k_q>0$, then $p_{(\widehat k)}\le q\widehat k/N$, so the indices of $p_{(1)},\ldots,p_{(\widehat k)}$ all lie in $\mathcal R_q^{(1)}$ and $R_q^{(1)}\ge\widehat k\ge1$. Hence $\{R_q^{(1)}\ge1\}=E_q$, and Step 6 gives $\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,0,\Sigma)\le Cq$ for all $N$, $\Sigma\in\mathcal C_N$ and $0<q\le q_0$.

This proves [gaussian_simes_one_sided_uniform_linear_bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md) from the four route lemmas, with $q_0=\alpha_0/2$ and $C=2\log(2/\eta)/\alpha_0$, where $\alpha_0=\min(q_D,q_V,\eta/(2(\max(C_D,0)+1)))$. $\square$

## Verification

Step 6 gives $\mathbb P_{N,0,\Sigma}(E_q)\le B(q)\le Cq$ for every $N$, every $\Sigma\in\mathcal C_N$ including singular matrices, and every $0<q\le q_0$, with $q_0\in(0,1/2)$ and $C<\infty$ depending only on the universal constants $C_D,q_D$ of the dense lemma and $q_V,\eta$ of the variation lemma. The event $E_q$ of the target, the event $E_\alpha$ of the amplification lemma at $\alpha=q$, and the Simes event of the library theorem coincide, all with non-strict comparisons and multiplicities. Step 7 gives the equivalent BH form. The variation lemma is applied to the given $\Sigma$ itself, singular or not, so no regularization enters the reduction; regularization is only a tool inside that lemma's proof. The endpoint bound uses only that $\Sigma\circ\Sigma$ has nonnegative entries, which holds for every starting $\Sigma$, whatever the signs of its correlations.

## Difference from failed plans

- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s1_sparse_fixed_level_cap: that route asked for a direct cap $\mathbb P_\Sigma(S_q)\le1-\eta$ at the original correlation via the Gibbs (min-entropy) penalty. Here the sparse event is never bounded at $\Sigma$ directly: it is bounded at the nonnegative endpoint $\Sigma\circ\Sigma$ by the library theorem, and only the signed downward variation along the Schur-square path is new.
- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s2_positive_class_cover: that route needed a prior over positive classes of $\Sigma$ that hits sparse crossings. Here no class cover is chosen: the covariance itself is moved into the nonnegative cone, its positive classes growing monotonically along the path, and the positive-dependence theorem is used once, at the endpoint.
- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s3_mills_penalized_subset_acceptance: that route reduced crossings to a Mills-normalized subset supremum, which clones plus independent coordinates defeat. Here exact positive clones stay tied along the path with their multiplicities, and independent blocks stay independent, so neither degeneracy is distorted.
- plan_one_sided_order_three_face_noise_packing_20261106: its budget maximized against a covariance unrelated to the original and dropped the small-correlation factor. Here the velocity is the actual $\Delta_{ij}=-\rho_{ij}(1-\rho_{ij})$ of $\Sigma$, the three-face pair terms are summed with signs before the positive part, and the event is restricted to sparse crossings, whose corner thresholds all lie above $u_q+1$.

## Reduction verdict

confirmed

1. Event split (Step 1). The rank-wise identity $p_{(k)}\le c\iff N_k(c)\ge k$ is correct with multiplicities, so $E_q=\bigcup_k\{N_k(qk/N)\ge k\}$. The dense event $D_{q,1}$ of the approved tilt bound uses the condition $qk/N\ge\overline\Phi(u_q+1)$ and the sparse set $S_q$ of the variation lemma uses the strict complement $qk/N<\overline\Phi(u_q+1)$, with the same non-strict count; so $E_q=D_{q,1}\cup\{T\in S_q\}$ holds pointwise, hence under every law, including $\mathcal N_N(0,\Sigma\circ\Sigma)$. $E_q$ is literally the target's event and the amplification lemma's $E_\alpha$ at $\alpha=q$.
2. Path (Step 2). $\Sigma\circ\Sigma\in\mathcal C_N$ by the Schur product theorem, and $\mathcal C_N$ is convex, so $f_{q,\Sigma}$ is defined on $[0,1]$ with $f_{q,\Sigma}(0)=\mathbb P_{N,0,\Sigma}(T\in S_q)$. The variation lemma also states this.
3. Endpoint (Step 3). The hypotheses of lib_chi2024_positive_gaussian_simes are checked against the two library definitions: $Y\sim\mathcal N_N(0,\Sigma\circ\Sigma)$ is jointly Gaussian (degenerate allowed) with unit variances, so its latent correlation is $\Sigma\circ\Sigma$, whose off-diagonal entries $\rho_{ij}^2$ are nonnegative; the transforms $\overline\Phi$ are measurable and all nonincreasing, so $P=\overline\Phi(Y)\in\mathcal G_{\Sigma\circ\Sigma}$; each $P_i$ is uniform, so $P\in\mathcal U^N$; and $\{S_N(P)\le q\}$ with $S_N(p)=\min_k(N/k)p_{(k)}$ is exactly $E_q$ computed from $Y$. With $K=N$ and $\alpha=q\in(0,1)$ this gives $\mathbb P_{N,0,\Sigma\circ\Sigma}(E_q)\le q$, so $f_{q,\Sigma}(1)\le q$ by the inclusion of Step 1.
4. Variation (Step 4). The one-interval partition $0=t_0<t_1=1$ is admissible in $\mathcal V_-$, so $f(0)-f(1)\le\mathcal V_-(f)\le1-\eta$ for $q\in(0,q_V]$, applied to the given $\Sigma$, exactly as the lemma is quantified (for every $q\le q_V$, $N$, $\Sigma$, singular included). No regularity of $f$ is needed.
5. Fixed level (Step 5). The dense lemma is used with $\delta=1\in(0,1]$ and $q\le q_D$, giving $C_Dq$; replacing $C_D$ by $\max(C_D,0)$ is harmless. The union bound gives $\mathbb P(E_q)\le(C_D^++1)q+1-\eta$ for $q\le\min(q_D,q_V)$, and the choice $\alpha_0=\min(q_D,q_V,\eta/(2(C_D^++1)))$ gives $0<\alpha_0\le1/4$ and $B(\alpha_0)\le1-\eta/2$, with the supremum over all $N$ and all $\Sigma\in\mathcal C_N$ as in the amplification lemma's $B$.
6. Amplification (Step 6). The hypotheses $\alpha_0\in(0,1)$ and $\delta=\eta/2\in(0,1)$ hold, so $B(t)\le(2\log(2/\eta)/\alpha_0)t$ for $t\in(0,\alpha_0/2]$. Then $C=2\log(2/\eta)/\alpha_0\in(0,\infty)$ because $\eta<1$, and $q_0=\alpha_0/2\in(0,1/8]\subset(0,1/2)$. Both depend only on the universal constants $C_D,q_D,q_V,\eta$, and they are chosen before $N,\Sigma,q$, which is the target's quantifier order.
7. BH form (Step 7). With $\theta=0$ every index is a one-sided true null, so $V=R$ and the FDR equals $\mathbb P(R_q^{(1)}\ge1)$. Also $\{R_q^{(1)}\ge1\}=\{\widehat k_q>0\}=E_q$, since $\widehat k>0$ puts the indices of $p_{(1)},\ldots,p_{(\widehat k)}$ in the rejection set. The p-values lie in $(0,1)\subset[0,1]$, as the BH definition requires.

Every lemma is used only through its statement, the constants are uniform, and singular $\Sigma$ is covered at every step because each cited statement admits singular matrices. All the mathematical weight remains on the draft lemma gaussian_simes_schur_square_sparse_variation_budget.
