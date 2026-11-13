---
type: plan
title: >-
  Fixed-level amplification by independent block replication, a product
  inequality, and monotonicity in the level
status: succeeded
target_asset: gaussian_simes_fixed_level_amplification
origin: agent
inspired_by:
  - idea_7d0a17e5c13c
  - idea_8699fa13f1f6
proof_digest: dc9b60ff28737d1d94ef2ab1ecdaabf12bd235f0dc9875c52fbece270fd3184b
statement_digest: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
verified_proof_digest: dc9b60ff28737d1d94ef2ab1ecdaabf12bd235f0dc9875c52fbece270fd3184b
---

## Goal

Target: [asset](../assets/gaussian_simes_fixed_level_amplification.md)

Prove the fixed-level-to-linear implication directly from the definitions. The proof replicates a near-worst model at level $\alpha_0/M$ in $M$ independent blocks, notes that any local Simes rejection is a global Simes rejection at level $\alpha_0$, and finishes with $1-e^{-x}\le x$ and monotonicity of $B$ in the level. No dependency is cited. The library analogues (positive-dependence Simes, uniform integrability, Gaussian isoperimetry, Danskin, Dovbysh-Sudakov) are not needed: the argument is elementary and the premise $B(\alpha_0)\le1-\delta$ carries all the Gaussian content.

## Plan

1. [x] **Well-posedness and monotonicity.** For each $N$, $\Sigma\in\mathcal C_N$ and $\alpha$, the event $E_\alpha$ is a finite union of closed sets in $T$, since each $p_{(k)}$ is a continuous function of $T$. So it is measurable, and $0\le B(\alpha)\le1$. If $0<s\le\alpha<1$, then $p_{(k)}\le sk/N$ implies $p_{(k)}\le\alpha k/N$. So $E_s\subseteq E_\alpha$ pointwise for every model, and taking suprema gives $B(s)\le B(\alpha)$.
2. [x] **Block replication is admissible.** Fix integers $M,n\ge1$ and $\Sigma\in\mathcal C_n$ (possibly singular). Put $N=Mn$ and $\Sigma^{(M)}=\mathrm{diag}(\Sigma,\ldots,\Sigma)$ ($M$ blocks). Then $\Sigma^{(M)}$ is symmetric with unit diagonal, and $x^{\mathsf T}\Sigma^{(M)}x=\sum_j x_j^{\mathsf T}\Sigma x_j\ge0$ for $x=(x_1,\ldots,x_M)$. So $\Sigma^{(M)}\in\mathcal C_N$. Let $T^{(1)},\ldots,T^{(M)}$ be independent with each $T^{(j)}\sim\mathcal N_n(0,\Sigma)$, and let $T=(T^{(1)},\ldots,T^{(M)})$. For $a=(a_1,\ldots,a_M)$, independence gives that $a^{\mathsf T}T=\sum_j a_j^{\mathsf T}T^{(j)}$ is a sum of independent centered normals (variance zero meaning the constant zero) with variance $a^{\mathsf T}\Sigma^{(M)}a$. So $T\sim\mathcal N_N(0,\Sigma^{(M)})$ in the sense of the definition, and $\mathbb P_{N,0,\Sigma^{(M)}}(E)$ may be computed with this construction for every Borel event $E$ of $T$.
3. [x] **Event inclusion.** Let $E^{(j)}$ be the Simes event of block $j$ at level $\alpha_0/M$, computed from $p^{(j)}_i=\overline\Phi(T^{(j)}_i)$ with block size $n$. Claim: $\bigcup_{j=1}^M E^{(j)}\subseteq E_{\alpha_0}$ for the global model of size $N=Mn$. Proof: on $E^{(j)}$ some $r\in\{1,\ldots,n\}$ has $p^{(j)}_{(r)}\le(\alpha_0/M)r/n=\alpha_0r/N$. Block $j$ contains at least $r$ coordinates whose p-values are $\le p^{(j)}_{(r)}$. These are also global coordinates, so the global order statistic satisfies $p_{(r)}\le p^{(j)}_{(r)}\le\alpha_0r/N$, with $r\le N$. Hence $E_{\alpha_0}$ holds with $k=r$.
4. [x] **Product inequality.** The events $E^{(j)}$ are functions of independent blocks, each with probability $b:=\mathbb P_{n,0,\Sigma}(E_{\alpha_0/M})$. By Steps 2 and 3, $\mathbb P_{N,0,\Sigma^{(M)}}(E_{\alpha_0})\ge1-(1-b)^M$. The left side is at most $B(\alpha_0)\le1-\delta$, so $(1-b)^M\ge\delta$.
5. [x] **Pass to the supremum.** Given $\varepsilon>0$, choose $n$ and $\Sigma\in\mathcal C_n$ with $b\ge B(\alpha_0/M)-\varepsilon$ (possible since $B(\alpha_0/M)\le1$ is a finite supremum; no attainment is assumed). Then $0\le1-b\le1-B(\alpha_0/M)+\varepsilon$, and Step 4 gives $(1-B(\alpha_0/M)+\varepsilon)^M\ge\delta$. Letting $\varepsilon\downarrow0$ gives $(1-B(\alpha_0/M))^M\ge\delta$, so $B(\alpha_0/M)\le1-\delta^{1/M}$. Note that $\alpha_0/M\in(0,1)$, so this is an admissible level.
6. [x] **Exponential bound.** With $x=\log(1/\delta)/M>0$, $\delta^{1/M}=e^{-x}$ and $1-e^{-x}\le x$. So $B(\alpha_0/M)\le\log(1/\delta)/M$ for every integer $M\ge1$.
7. [x] **Choice of $M$ and monotonicity.** For $t\in(0,\alpha_0/2]$, let $y=\alpha_0/t\ge2$ and $M=\lfloor y\rfloor\ge2$. Then $M\le y$ gives $t\le\alpha_0/M$, and $M>y-1\ge y/2$ (since $y\ge2$) gives $1/M\le2t/\alpha_0$. Step 1 and Step 6 give $B(t)\le B(\alpha_0/M)\le\log(1/\delta)/M\le2\log(1/\delta)\,t/\alpha_0$.

## Verification

Step 7 is exactly the displayed conclusion for every $t\in(0,\alpha_0/2]$, under the sole hypothesis $B(\alpha_0)\le1-\delta$ with $\alpha_0,\delta\in(0,1)$. The suprema range over all $N$ and all of $\mathcal C_N$, including singular matrices: Step 2 allows singular local $\Sigma$ and produces a member of $\mathcal C_{Mn}$, and Step 5 uses only the definition of the supremum. The comparisons are non-strict throughout, matching $E_\alpha$. Order statistics count multiplicities, which Step 3 respects, because it counts at least $r$ coordinates at or below $p^{(j)}_{(r)}$.

## Assumed definitions

None beyond the approved definitions [gaussian_multiple_testing_model](../definitions/gaussian_multiple_testing_model.md) and [gaussian_test_pvalues](../definitions/gaussian_test_pvalues.md), track $s=1$, all means zero. No unproved dependency is used. The ideas in `inspired_by` are draft observations: their argument is reproved in Steps 1 to 7 rather than assumed.

## Outcome

Succeeded. The complete proof is under `## Proof` in [the target asset](../assets/gaussian_simes_fixed_level_amplification.md), following Steps 1 to 7 of this plan in order. Nothing is assumed beyond the approved definitions [gaussian_multiple_testing_model](../definitions/gaussian_multiple_testing_model.md) and [gaussian_test_pvalues](../definitions/gaussian_test_pvalues.md); no dependency is cited. Small additions in the written proof: the explicit construction $T^{(j)}=AZ^{(j)}$ with $\Sigma=AA^{\mathsf T}$ (so the independent blocks exist for singular $\Sigma$), the Cramér–Wold remark that probabilities depend only on the law, and the counting characterization of order statistics with multiplicity used in Step 3.

## Verdict

confirmed

Checked each step against the statement and the two approved definitions. Step 1: $x_{(k)}=\min_{|S|=k}\max_{i\in S}x_i$ is continuous, so $E_\alpha$ is closed in $T$ and $E_s\subseteq E_\alpha$ for $s\le\alpha$ gives monotonicity of $B$. Step 2: $\Sigma^{(M)}$ is symmetric, PSD and has unit diagonal, so it lies in $\mathcal C_{Mn}$. The construction $T^{(j)}=AZ^{(j)}$ gives the joint Gaussian law in the definition's linear-functional sense, singular $\Sigma$ included. Step 3: the threshold $(\alpha_0/M)r/n=\alpha_0r/N$ matches exactly, and $r$ block p-values $\le c$ give $p_{(r)}\le c$ by the counting characterization, so $\bigcup_jE^{(j)}\subseteq E_{\alpha_0}$. Step 4: the blocks are independent and $\Sigma^{(M)}$ is admissible, so $B(\alpha_0)\ge\mathbb P(\bigcup_j E^{(j)})=1-(1-b)^M$. Step 5: the approximation argument works even when $B(\alpha_0/M)-\varepsilon<0$, and the $M$-th root is legitimate because $1-B\ge0$. Step 6: $1-e^{-x}\le x$, with $\log(1/\delta)>0$ since $\delta\in(0,1)$. Step 7: with $y=\alpha_0/t\ge2$ and $M=\lfloor y\rfloor\ge2$ we get $t\le\alpha_0/M<1$ and $M>y-1\ge y/2$, so $1/M<2t/\alpha_0$. The inequality directions and the constant $2\log(1/\delta)/\alpha_0$ agree with the statement. I found no gaps.
