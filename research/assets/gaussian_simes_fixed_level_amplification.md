---
type: lemma
title: Fixed-level all-null Gaussian Simes bound implies a uniform linear bound
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes_positive_cover_route
---

# Fixed-level all-null Gaussian Simes bound implies a uniform linear bound

## Statement

For $\alpha\in(0,1)$, a positive integer $N$ and $\Sigma\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), let $T\sim\mathcal N_N(0,\Sigma)$, form the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$ with order statistics $p_{(1)}\le\cdots\le p_{(N)}$ (including multiplicities), and put
$$
E_\alpha=\Bigl\{\exists k\in\{1,\ldots,N\}:p_{(k)}\le\frac{\alpha k}{N}\Bigr\},
\qquad
B(\alpha)=\sup_{N\ge1}\ \sup_{\Sigma\in\mathcal C_N}\mathbb P_{N,0,\Sigma}(E_\alpha).
$$
If $\alpha_0\in(0,1)$ and $\delta\in(0,1)$ satisfy $B(\alpha_0)\le1-\delta$, then
$$
B(t)\le\frac{2\log(1/\delta)}{\alpha_0}\,t\qquad\text{for every }t\in(0,\alpha_0/2].
$$
Singular covariance matrices are included in every supremum, and the comparisons in $E_\alpha$ are non-strict.

## Proof

Throughout, for a model of size $N$ write $p_i=\overline\Phi(T_i)$ and let $p_{(1)}\le\cdots\le p_{(N)}$ be the order statistics counted with multiplicity, so that for every $r$ and every real $c$,
$$
p_{(r)}\le c\iff\#\{i\in[N]:p_i\le c\}\ge r .
$$

**Step 1 (well-posedness and monotonicity).** The map $x\mapsto x_{(k)}=\min_{|S|=k}\max_{i\in S}x_i$ from $\mathbb R^N$ to $\mathbb R$ is continuous, and $\overline\Phi$ is continuous. Hence each $p_{(k)}$ is a continuous function of $T$, and $E_\alpha=\bigcup_{k=1}^N\{p_{(k)}\le\alpha k/N\}$ is a finite union of closed subsets of $\mathbb R^N$, hence a Borel event of $T$. Thus $\mathbb P_{N,0,\Sigma}(E_\alpha)\in[0,1]$ and $0\le B(\alpha)\le1$ for every $\alpha\in(0,1)$. If $0<s\le\alpha<1$, then $p_{(k)}\le sk/N$ implies $p_{(k)}\le\alpha k/N$, so $E_s\subseteq E_\alpha$ in every model, and taking suprema over $N$ and $\Sigma$ gives
$$
B(s)\le B(\alpha)\qquad(0<s\le\alpha<1).
$$

**Step 2 (block replication is admissible).** Fix integers $M,n\ge1$ and $\Sigma\in\mathcal C_n$, possibly singular. Put $N=Mn$ and let $\Sigma^{(M)}=\mathrm{diag}(\Sigma,\ldots,\Sigma)$ be the block-diagonal matrix with $M$ diagonal blocks equal to $\Sigma$. It is symmetric with unit diagonal, and for $x=(x_1,\ldots,x_M)$ with $x_j\in\mathbb R^n$ we have $x^{\mathsf T}\Sigma^{(M)}x=\sum_{j=1}^Mx_j^{\mathsf T}\Sigma x_j\ge0$. Hence $\Sigma^{(M)}\in\mathcal C_N$.

Since $\Sigma$ is positive semidefinite, write $\Sigma=AA^{\mathsf T}$ (for instance $A=\Sigma^{1/2}$), take independent standard normal vectors $Z^{(1)},\ldots,Z^{(M)}$ in $\mathbb R^n$, and put $T^{(j)}=AZ^{(j)}$ and $T=(T^{(1)},\ldots,T^{(M)})\in\mathbb R^N$. For $u\in\mathbb R^n$, $u^{\mathsf T}T^{(j)}=(A^{\mathsf T}u)^{\mathsf T}Z^{(j)}$ is centered normal with variance $|A^{\mathsf T}u|^2=u^{\mathsf T}\Sigma u$ (the constant zero if this vanishes), so each $T^{(j)}\sim\mathcal N_n(0,\Sigma)$, and the blocks are independent. For $a=(a_1,\ldots,a_M)\in\mathbb R^N$, the variable $a^{\mathsf T}T=\sum_ja_j^{\mathsf T}T^{(j)}$ is a sum of independent centered normals, hence centered normal with variance $\sum_ja_j^{\mathsf T}\Sigma a_j=a^{\mathsf T}\Sigma^{(M)}a$ (the constant zero when this is zero). So $T\sim\mathcal N_N(0,\Sigma^{(M)})$ in the sense of the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md). The law of a random vector is determined by the laws of all its linear functionals (Cramér–Wold), so $\mathbb P_{N,0,\Sigma^{(M)}}(E)=\mathbb P(T\in E)$ for every Borel set $E$, computed with this construction; likewise $\mathbb P_{n,0,\Sigma}(F)=\mathbb P(T^{(j)}\in F)$ for each $j$ and Borel $F\subseteq\mathbb R^n$.

**Step 3 (event inclusion).** Let $p^{(j)}_i=\overline\Phi(T^{(j)}_i)$ for $i\in[n]$, with order statistics $p^{(j)}_{(1)}\le\cdots\le p^{(j)}_{(n)}$, and let
$$
E^{(j)}=\Bigl\{\exists r\in[n]:p^{(j)}_{(r)}\le\frac{(\alpha_0/M)\,r}{n}\Bigr\}
$$
be the event $E_{\alpha_0/M}$ of the size-$n$ model computed from block $j$. The global p-values of $T$ are the concatenation of the $p^{(j)}$. On $E^{(j)}$ pick such an $r$; then $c:=p^{(j)}_{(r)}\le\alpha_0r/(Mn)=\alpha_0r/N$, and block $j$ contains at least $r$ coordinates with p-value $\le c$. These are also global coordinates, so $\#\{i\in[N]:p_i\le c\}\ge r$, i.e. $p_{(r)}\le c\le\alpha_0r/N$ with $r\le n\le N$. Hence $E_{\alpha_0}$ holds with $k=r$, and
$$
\bigcup_{j=1}^ME^{(j)}\subseteq E_{\alpha_0}\quad\text{(global model of size }N=Mn\text{)}.
$$

**Step 4 (product inequality).** Note $\alpha_0/M\in(0,1)$. Put $b=\mathbb P_{n,0,\Sigma}(E_{\alpha_0/M})$. By Step 2 each $E^{(j)}$ is the event $\{T^{(j)}\in F\}$ for the same Borel set $F$ (Step 1), so $\mathbb P(E^{(j)})=b$, and the events $E^{(1)},\ldots,E^{(M)}$ are independent because they are determined by the independent blocks. By Step 3,
$$
1-\delta\ge B(\alpha_0)\ge\mathbb P_{N,0,\Sigma^{(M)}}(E_{\alpha_0})\ge\mathbb P\Bigl(\bigcup_{j=1}^ME^{(j)}\Bigr)=1-\prod_{j=1}^M\bigl(1-\mathbb P(E^{(j)})\bigr)=1-(1-b)^M .
$$
Hence $(1-b)^M\ge\delta$ for every $n\ge1$ and every $\Sigma\in\mathcal C_n$.

**Step 5 (passing to the supremum).** Fix $M\ge1$ and $\varepsilon>0$. Since $B(\alpha_0/M)\le1$ is a supremum, there are $n\ge1$ and $\Sigma\in\mathcal C_n$ with $b=\mathbb P_{n,0,\Sigma}(E_{\alpha_0/M})\ge B(\alpha_0/M)-\varepsilon$; no attainment is needed. Then $0\le1-b\le1-B(\alpha_0/M)+\varepsilon$, and since $u\mapsto u^M$ is nondecreasing on $[0,\infty)$, Step 4 gives
$$
\bigl(1-B(\alpha_0/M)+\varepsilon\bigr)^M\ge(1-b)^M\ge\delta .
$$
Letting $\varepsilon\downarrow0$ and using continuity of $u\mapsto u^M$ yields $(1-B(\alpha_0/M))^M\ge\delta$. As $1-B(\alpha_0/M)\ge0$, taking $M$-th roots gives
$$
B(\alpha_0/M)\le1-\delta^{1/M}.
$$

**Step 6 (exponential bound).** Put $x=\log(1/\delta)/M>0$, so $\delta^{1/M}=e^{-x}$. Since $e^{-x}\ge1-x$ for all real $x$ (convexity of the exponential), $1-\delta^{1/M}=1-e^{-x}\le x$. Therefore
$$
B(\alpha_0/M)\le\frac{\log(1/\delta)}{M}\qquad\text{for every integer }M\ge1.
$$

**Step 7 (choice of $M$ and monotonicity).** Let $t\in(0,\alpha_0/2]$, put $y=\alpha_0/t\ge2$ and $M=\lfloor y\rfloor\ge2$. From $M\le y$ we get $t\le\alpha_0/M$, and both $t$ and $\alpha_0/M$ lie in $(0,1)$. From $M>y-1\ge y/2$ (the last inequality because $y\ge2$) we get $1/M<2/y=2t/\alpha_0$. By Step 1 and Step 6,
$$
B(t)\le B(\alpha_0/M)\le\frac{\log(1/\delta)}{M}\le\frac{2\log(1/\delta)}{\alpha_0}\,t .
$$
This holds for every $t\in(0,\alpha_0/2]$, which is the claim. Singular covariances were allowed throughout (Step 2 accepts singular $\Sigma$ and produces a member of $\mathcal C_{Mn}$; Step 5 uses only the definition of the supremum over all of $\mathcal C_n$), and all comparisons were non-strict, as in $E_\alpha$. $\blacksquare$
