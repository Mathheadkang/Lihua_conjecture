---
type: plan
title: >-
  Linear Gaussian Simes bound via the Schur-square variation, proved first for
  clone-block models and transferred by few-block compression
status: pending
target_asset: gaussian_simes_one_sided_uniform_linear_bound
route_lemmas:
  - gaussian_simes_clone_block_schur_variation_bound
  - gaussian_simes_schur_variation_few_block_compression
  - lib_chi2024_positive_gaussian_simes
  - gaussian_simes_fixed_level_amplification
route_title: via clone-block Schur variation and few-block compression
origin: agent
inspired_by:
  - idea_6b48b2fe25e1
  - idea_a0805e98f90d
tags:
  - route
  - schur_square_variation
route_round: 2
reduction_digest: 32ec5f40d7eefdb26c94e60554824b3880ad667ad89bd0ed53d55fd8571e9fee
reduction_inputs:
  gaussian_simes_one_sided_uniform_linear_bound: 056ac9e2897851e7a490dc0b61a7810240e679307e0595cf07ea9c09c0ec8abc
  gaussian_simes_clone_block_schur_variation_bound: 9745c7f1d8f7ae5518e033eec521fe69f3dee7d75adf2262924621d839195795
  gaussian_simes_schur_variation_few_block_compression: ae49babfdb545830e8ad7375a17d918e1fb1ba20e49b625bd07dbdd7738fee3a
  lib_chi2024_positive_gaussian_simes: ec28454a273facc776f366331e57e9607ec21259d9fb56b3c1a187d35b8007e9
  gaussian_simes_fixed_level_amplification: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
reduction_verified_digest: 32ec5f40d7eefdb26c94e60554824b3880ad667ad89bd0ed53d55fd8571e9fee
reduction_checked: true
---

## Goal

Target: [gaussian_simes_one_sided_uniform_linear_bound](../assets/gaussian_simes_one_sided_uniform_linear_bound.md)

Close the target through the variation assertion (SV) of the [Schur-square tensor-lift approach](../ideas/idea_6b48b2fe25e1.md) at one universal level: prove SV first for clone-block models (finitely many Gaussian directions, arbitrary multiplicities) with a multiplicity-free constant, then reduce the general downward variation to that model class at a block budget of order $\log(1/q)$.

## Route

- gaussian_simes_clone_block_schur_variation_bound: model case; for clone-block covariances with at most $K$ blocks, the Schur-square profile has downward variation at most $K^24^Kq$, independent of $N$, the multiplicities and the block matrix. It bounds $\mathcal M(q)$ in step 2.
- gaussian_simes_schur_variation_few_block_compression: reduction; the downward variation of an arbitrary profile is at most $\mathcal M(q)+1/8$ for $q\le q_2$. It carries the main weight of the route (step 3).
- lib_chi2024_positive_gaussian_simes: the endpoint $\Sigma\circ\Sigma$ has nonnegative correlations, so its Simes size is at most $q$ (step 4).
- gaussian_simes_fixed_level_amplification: turns the fixed-level bound $3/8$ into the linear bound (step 6).

## Plan

1. [x] Fix $q_*=q_2$ from the compression lemma, so $q_*\le1/4$. For every $N$ and $\Sigma\in\mathcal C_N$, the Schur-square path $R_t=(1-t)\Sigma+t(\Sigma\circ\Sigma)$ lies in $\mathcal C_N$ (Schur product theorem; unit diagonal is preserved), so $f_{q_*,\Sigma}(t)=F_{q_*}(R_t)$ is defined on $[0,1]$, with $f(0)=F_{q_*}(\Sigma)$ the target probability at level $q_*$.
2. [x] Model bound: put $K=K_\flat(q_*)=\max\{1,\lfloor\log(1/q_*)/(4\log4)\rfloor\}$. By the clone-block lemma (valid since $q_*<1/2$), every clone-block covariance with at most $K$ blocks has $\mathcal V_-\le K^24^Kq_*$. If $K=1$ this is at most $4q_*$, and in fact $0$ since the path is constant; otherwise $4^K\le q_*^{-1/4}$ and $K^2\le\log(1/q_*)^2/(16\log^24)$, so $K^24^Kq_*\le\log(1/q_*)^2q_*^{3/4}/(16\log^24)\le(64/9)e^{-2}/(16\log^24)<1/8$, using $\max_{L>0}L^2e^{-3L/4}=(64/9)e^{-2}$. Hence $\mathcal M(q_*)\le1/8$.
3. [x] Compression: for every $N$ and $\Sigma\in\mathcal C_N$, singular included, $\mathcal V_-(f_{q_*,\Sigma})\le\mathcal M(q_*)+1/8\le1/4$.
4. [x] Endpoint: $\Sigma\circ\Sigma\in\mathcal C_N$ has all entries $\Sigma_{ij}^2\ge0$. The p-values $\overline\Phi(Z_i)$, $Z\sim\mathcal N_N(0,\Sigma\circ\Sigma)$, are uniform and Gaussian dependent with this latent correlation, and the event $\{\exists k:p_{(k)}\le q_*k/N\}$ is $\{S_N(P)\le q_*\}$ for the Simes function. The positive Gaussian Simes theorem gives $f(1)\le q_*$.
5. [x] Variation step: the one-interval partition in the definition of $\mathcal V_-$ gives $f(0)-f(1)\le[f(0)-f(1)]_+\le\mathcal V_-(f)$. Hence $F_{q_*}(\Sigma)\le q_*+1/4\le1/2$ for all $N,\Sigma$; in particular $B(q_*)\le1/2$ in the notation of the amplification lemma.
6. [x] Amplification with $\alpha_0=q_*$, $\delta=1/2$: $B(t)\le(2\log2/q_*)\,t$ for $t\in(0,q_*/2]$. Take $q_0=q_*/2\in(0,1/2)$ and $C=2\log2/q_*$.
7. [x] BH form: with $\theta=0$ every coordinate is a one-sided true null, so $V_q^{(1)}=R_q^{(1)}$ and $V/(R\vee1)=\mathbf 1\{R_q^{(1)}\ge1\}$; and $R_q^{(1)}\ge1$ exactly when some $p_{(k)}\le qk/N$, by the largest-qualifying-rank definition. So $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)$ equals the Simes probability and obeys the same bound.

## Verification

Steps 1 to 5 give a dimension-free bound $1/2$ on the all-null one-sided Simes probability at the single level $q_*=q_2$, for every $N$ and every $\Sigma\in\mathcal C_N$ including singular ones: the clone-block lemma makes the few-block supremum at most $1/8$, the compression lemma transfers this to every covariance with slack $1/8$, the positive Gaussian Simes theorem bounds the nonnegative endpoint by $q_*\le1/4$, and the downward variation controls the drop from $t=0$ to $t=1$. No differentiability of the profile is used in the reduction; Price's formula and the signed three-face terms enter only inside the two lemmas, and the positive part is taken after summing pair contributions because the lemmas are stated for the variation of the profile itself. Step 6 converts the fixed-level bound into $\mathbb P(\exists k:p_{(k)}\le qk/N)\le Cq$ for all $0<q\le q_0$ with universal $C=2\log2/q_2$ and $q_0=q_2/2$, independent of $N$, rank and correlations; the comparisons are non-strict throughout, matching the target. Step 7 gives the equivalent BH formulation.

## Difference from failed plans

- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s1_sparse_fixed_level_cap: that route split crossings into dense and sparse at the original covariance and needed a direct sparse cap; here no dense/sparse split is used, and the original covariance is compared to the nonnegative endpoint $\Sigma\circ\Sigma$ by the variation of the Simes size along the Schur-square path.
- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s2_positive_class_cover: that route transferred the positive-dependence Simes inequality to random positive classes and needed a sparse hitting bound; here the positive-dependence theorem is used once, at the endpoint, for the whole covariance $\Sigma\circ\Sigma$, with no cover or hitting estimate.
- route_gaussian_simes_one_sided_uniform_linear_bound_r1_s3_mills_penalized_subset_acceptance: that route bounded a Mills-normalized penalized subset supremum; this route never passes to a subset supremum or union over subsets, and the only uniform estimate needed is on the downward variation of one probability profile.
- plan_one_sided_order_three_face_noise_packing_20261106: that budget maximized against a covariance velocity independent of the original covariance and dropped the small-correlation factor. Here the velocity is the actual Schur-square contraction $\rho_{ij}^2-\rho_{ij}=-\rho_{ij}(1-\rho_{ij})$, exact clones stay tied with their multiplicities, the model bound is counted per block pair with corner levels at most $q$, and the general case is reduced to finitely many blocks rather than bounded by summing pair magnitudes in unrestricted dimension.

## Reduction

Each lemma and dependency below is used only through its statement. Notation: for $q\in(0,1)$, a positive integer $N$ and $R\in\mathcal C_N$, $F_q(R)$ is the probability, for $Z\sim\mathcal N_N(0,R)$ and $p_i=\overline\Phi(Z_i)$, of $E_q=\{\exists k\in\{1,\ldots,N\}:p_{(k)}\le qk/N\}$ (order statistics with multiplicities, non-strict comparisons). For $\Sigma\in\mathcal C_N$, $R_t^\Sigma=(1-t)\Sigma+t(\Sigma\circ\Sigma)$ and $f_{q,\Sigma}(t)=F_q(R_t^\Sigma)$ on $[0,1]$; $\mathcal V_-$, clone-block covariances, $K_\flat$ and $\mathcal M$ are as in the statements of [gaussian_simes_clone_block_schur_variation_bound](../assets/gaussian_simes_clone_block_schur_variation_bound.md) and [gaussian_simes_schur_variation_few_block_compression](../assets/gaussian_simes_schur_variation_few_block_compression.md), which use identical definitions (the second restates the first). With $T\sim\mathcal N_N(0,\Sigma)$ and $p^{(1)}_i=\overline\Phi(T_i)$, the probability in the target is exactly $F_q(\Sigma)$, and it is the quantity $\mathbb P_{N,0,\Sigma}(E_q)$ of [gaussian_simes_fixed_level_amplification](../assets/gaussian_simes_fixed_level_amplification.md), whose supremum over $N$ and $\Sigma\in\mathcal C_N$ is $B(q)$.

**Step 1 (level and path).** Let $q_2\in(0,1/4]$ be the universal constant of the compression lemma and put $q_*=q_2$. Fix $N\ge1$ and $\Sigma\in\mathcal C_N$, singular or not. By the Schur product theorem $\Sigma\circ\Sigma$ is positive semidefinite; it is symmetric with $(\Sigma\circ\Sigma)_{ii}=\Sigma_{ii}^2=1$. For $t\in[0,1]$, $R_t^\Sigma$ is a convex combination of two elements of $\mathcal C_N$, hence symmetric, positive semidefinite and with unit diagonal, so $R_t^\Sigma\in\mathcal C_N$. Thus $f=f_{q_*,\Sigma}$ is a well-defined function $[0,1]\to[0,1]$ with $f(0)=F_{q_*}(\Sigma)$ and $f(1)=F_{q_*}(\Sigma\circ\Sigma)$.

**Step 2 ($\mathcal M(q_*)\le1/8$).** Put $K=K_\flat(q_*)$ and $L=\log(1/q_*)\ge\log4>0$. Let $N'\ge1$ and let $\Sigma'\in\mathcal C_{N'}$ be clone-block with at most $K$ blocks, $\Sigma'_{ij}=\Gamma_{a(i)a(j)}$.

- If $K=1$: then $\Gamma\in\mathcal C_1$, so $\Gamma=(1)$ and $\Sigma'_{ij}=1$ for all $i,j$. Hence $\Sigma'\circ\Sigma'=\Sigma'$, $R_t^{\Sigma'}=\Sigma'$ for all $t$, $f_{q_*,\Sigma'}$ is constant, and every sum in the definition of $\mathcal V_-$ vanishes: $\mathcal V_-(f_{q_*,\Sigma'})=0\le1/8$.
- If $K\ge2$: then $K=\lfloor L/(4\log4)\rfloor\le L/(4\log4)$, so $4^K=e^{K\log4}\le e^{L/4}=q_*^{-1/4}$ and $K^2\le L^2/(16\log^24)$. Since $q_*\le1/4<1/2$, the clone-block lemma applies with this $K$ and $q=q_*$ and gives
$$
\mathcal V_-(f_{q_*,\Sigma'})\le K^24^Kq_*\le\frac{L^2q_*^{3/4}}{16\log^24}=\frac{L^2e^{-3L/4}}{16\log^24}.
$$
The function $g(L)=L^2e^{-3L/4}$ on $(0,\infty)$ has $g'(L)=L(2-3L/4)e^{-3L/4}$, so its maximum is $g(8/3)=(64/9)e^{-2}<0.963$. As $16\log^24>30.7$, the right side is below $0.032<1/8$.

In both cases $\mathcal V_-(f_{q_*,\Sigma'})\le1/8$; taking the supremum over $N'$ and $\Sigma'$ gives $\mathcal M(q_*)\le1/8$.

**Step 3 (compression).** Since $q_*\in(0,q_2]$, the compression lemma gives, for the $N$ and $\Sigma$ of Step 1,
$$
\mathcal V_-(f)\le\mathcal M(q_*)+\tfrac18\le\tfrac14 .
$$

**Step 4 (nonnegative endpoint).** Let $Z\sim\mathcal N_N(0,\Sigma\circ\Sigma)$ and $P_i=\overline\Phi(Z_i)$. The latent vector $Z$ is jointly Gaussian with unit (positive) marginal variances, so its correlation matrix is $\Sigma\circ\Sigma$, and the transforms $\overline\Phi$ are all nonincreasing and measurable; hence $P$ is Gaussian dependent with latent correlation $\Sigma\circ\Sigma$, i.e. $P\in\mathcal G_{\Sigma\circ\Sigma}$ ([definition](../library/chi2024_negative_dependence/definitions/lib_chi2024_gaussian_dependence.md); degenerate latent vectors are allowed). Each $Z_i\sim\mathcal N(0,1)$, so $P_i=\overline\Phi(Z_i)$ is uniform on $[0,1]$ and $P\in\mathcal U^N$. Off-diagonal entries of $\Sigma\circ\Sigma$ are $\Sigma_{ij}^2\ge0$. With the Simes function $S_N(p)=\min_{1\le k\le N}(N/k)p_{(k)}$, a minimum over finitely many terms,
$$
\{S_N(P)\le q_*\}=\{\exists k:(N/k)P_{(k)}\le q_*\}=\{\exists k:P_{(k)}\le q_*k/N\}.
$$
By [lib_chi2024_positive_gaussian_simes](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) with $K=N$ and $\alpha=q_*\in(0,1)$, $f(1)=F_{q_*}(\Sigma\circ\Sigma)=\mathbb P(S_N(P)\le q_*)\le q_*$.

**Step 5 (fixed-level bound).** The partition $0=t_0<t_1=1$ ($m=1$) is admissible in the definition of $\mathcal V_-$, so $f(0)-f(1)\le[f(0)-f(1)]_+\le\mathcal V_-(f)$. By Steps 3 and 4,
$$
F_{q_*}(\Sigma)=f(0)\le f(1)+\mathcal V_-(f)\le q_*+\tfrac14\le\tfrac12 .
$$
As $N\ge1$ and $\Sigma\in\mathcal C_N$ (singular included) were arbitrary, $B(q_*)\le1/2$.

**Step 6 (amplification).** Apply the amplification lemma with $\alpha_0=q_*\in(0,1)$ and $\delta=1/2\in(0,1)$; the hypothesis $B(\alpha_0)\le1-\delta$ is Step 5. Hence $B(t)\le(2\log2/q_*)\,t$ for every $t\in(0,q_*/2]$. Put $q_0=q_*/2\in(0,1/8]\subset(0,1/2)$ and $C=2\log2/q_*\in(0,\infty)$; both depend only on the universal constant $q_2$. For every $N\ge1$, every $\Sigma\in\mathcal C_N$ including singular ones, and every $0<q\le q_0$,
$$
\mathbb P_{N,0,\Sigma}\Bigl(\exists k:p^{(1)}_{(k)}\le\frac{qk}{N}\Bigr)=F_q(\Sigma)\le B(q)\le Cq,
$$
which is the first display of the target, with non-strict comparisons, and with $N,\Sigma$ allowed to depend on $q$ because $B(q)$ is a supremum over all of them at each fixed $q$.

**Step 7 (BH form).** With $\theta=0$, $I_0^{(1)}(0)=\{i:0\le0\}=[N]$, so $V_q^{(1)}=|\mathcal R_q^{(1)}\cap[N]|=R_q^{(1)}$ and $V_q^{(1)}/(R_q^{(1)}\vee1)=\mathbf 1\{R_q^{(1)}\ge1\}$; hence $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,0,\Sigma)=\mathbb P_{N,0,\Sigma}(R_q^{(1)}\ge1)$. If some $k$ has $p^{(1)}_{(k)}\le qk/N$, then $\widehat k_q\ge1$ and $p^{(1)}_{(\widehat k_q)}\le q\widehat k_q/N$, so at least $\widehat k_q$ indices satisfy $p^{(1)}_i\le q\widehat k_q/N$ and $R_q^{(1)}\ge\widehat k_q\ge1$. If no $k$ qualifies, $\widehat k_q=0$ and $\mathcal R_q^{(1)}=\varnothing$. So $\{R_q^{(1)}\ge1\}=E_q$, and the FDR equals the Simes probability and satisfies the same bound $Cq$ for $0<q\le q_0$.

Hence the target holds with the universal constants $C=2\log2/q_2$ and $q_0=q_2/2$, given the clone-block variation bound, the few-block compression lemma, the positive Gaussian Simes theorem, and the fixed-level amplification lemma, each as stated. $\square$

## Reduction verdict

confirmed

1. Notation. The definitions of $F_q$, $f_{q,\Sigma}$, $\mathcal V_-$, clone-block covariances, $K_\flat$ and $\mathcal M$ in the reduction match the two new lemmas' statements word for word. $F_q(\Sigma)$ is exactly the target probability, and it is $\mathbb P_{N,0,\Sigma}(E_q)$ in the amplification lemma, so $B(q)=\sup_N\sup_{\Sigma\in\mathcal C_N}F_q(\Sigma)$.
2. Step 1. $q_*=q_2\in(0,1/4]$ is universal. $R_t^\Sigma\in\mathcal C_N$ by the Schur product theorem and convexity of $\mathcal C_N$, and $f(0)$, $f(1)$ are as claimed.
3. Step 2. If $K_\flat(q_*)=1$, then $\Gamma=(1)$, the path is constant and $\mathcal V_-=0$. If $K\ge2$, then $K=\lfloor L/(4\log4)\rfloor$, so $4^K\le q_*^{-1/4}$ and $K^2\le L^2/(16\log^24)$. The clone-block lemma applies because $q_*\le1/4<1/2$, $K$ is a positive integer and $\Sigma'$ has at most $K$ blocks in the lemma's sense. I rechecked the numbers: $\max_L L^2e^{-3L/4}=(64/9)e^{-2}\approx0.9624$, $16\log^24\approx30.75$, and the quotient is about $0.0313<1/8$. Taking the supremum gives $\mathcal M(q_*)\le1/8$, and in particular $\mathcal M(q_*)$ is finite.
4. Step 3. The compression lemma's hypotheses are $q\in(0,q_2]$, any $N\ge1$ and any $\Sigma\in\mathcal C_N$ including singular ones. With $q=q_*=q_2$ they hold, so $\mathcal V_-(f)\le1/4$. The quantifier order is right: $q_2$ is fixed before $N$ and $\Sigma$.
5. Step 4. I checked the library definitions (`show lib_chi2024_gaussian_dependence`, `lib_chi2024_simes_function_uniform_pvalues`). Gaussian dependence allows measurable transforms that are all nonincreasing, a degenerate latent vector, and positive latent marginal variances. Here $Z\sim\mathcal N_N(0,\Sigma\circ\Sigma)$ has unit variances, so $P=\overline\Phi(Z)\in\mathcal G_{\Sigma\circ\Sigma}\cap\mathcal U^N$, and the off-diagonal entries $\Sigma_{ij}^2\ge0$. The event identity $\{S_N(P)\le q_*\}=E_{q_*}$ holds because the minimum is over finitely many terms. The theorem with $\alpha=q_*\in(0,1)$ gives $f(1)\le q_*$.
6. Step 5. The trivial partition gives $f(0)-f(1)\le\mathcal V_-(f)$. Hence $F_{q_*}(\Sigma)\le q_*+1/4\le1/2$ for every $N$ and every $\Sigma$, and so $B(q_*)\le1/2$.
7. Step 6. The amplification lemma applies with $\alpha_0=q_*\in(0,1)$ and $\delta=1/2$ and gives $B(t)\le(2\log2/q_*)t$ on $(0,q_*/2]$. The constants are $q_0=q_2/2\in(0,1/8]\subset(0,1/2)$ and $C=2\log2/q_2$. Both are universal and fixed before $N$ and $\Sigma$, which may depend on $q$, as the target allows.
8. Step 7. With $\theta=0$ every index is a true null, so FDR $=\mathbb P(R_q^{(1)}\ge1)$. Under the stated BH definition, $\{R_q^{(1)}\ge1\}=E_q$: the order statistic at $\widehat k_q$ gives at least $\widehat k_q$ rejections. So the second display follows from the first.

Each lemma is used only through its statement, with every hypothesis checked. I found no gap. All of the mathematical weight rests on the two draft lemmas, the few-block compression lemma and the clone-block variation bound, which remain unproved.
