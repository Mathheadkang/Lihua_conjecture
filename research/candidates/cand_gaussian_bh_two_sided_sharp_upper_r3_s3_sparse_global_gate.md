---
type: candidate
title: A single singular global gate at vanishing alternative proportion
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:19:50.244Z'
extension_version: 0.0.4
---

## Object

For each $q\in(0,e^{-1})$, let
$$
L=\log(1/q),\qquad m=\lceil e^{L^2}\rceil,\qquad N=m+1,
$$
and let $Z_1,\ldots,Z_m$ be independent standard normal random variables. Set
$$
T_i=Z_i\quad(1\leq i\leq m),\qquad
T_N=-\sqrt{2L}+\frac1{\sqrt m}\sum_{i=1}^m Z_i.
$$
The first $m$ coordinates are true nulls. The last coordinate is the only alternative and is an exactly singular global gate depending on every null coordinate. Its mean diverges and its correlation with each individual null tends to zero, while the null proportion tends to one and the dimension grows faster than every fixed power of $1/q$. Apply the specified two-sided p-values and ordinary global BH procedure to all $N$ coordinates.

This tests an alternative-sparsity boundary with an unbounded number of distinct null p-values, rather than repeating a bounded collection of null signals.

## Checks

### H1

At every $q\in(0,e^{-1})$, $m$ and $N$ are finite positive integers. Their prescribed divergence is permitted by the uniform quantifiers.

### H2

The mean vector is
$$
\theta=(0,\ldots,0,-\sqrt{2L})\in\mathbb R^N.
$$
Every entry is finite at each fixed $q$, and the last mean is nonzero.

### H3

Put $a=m^{-1/2}(1,\ldots,1)^{\mathsf T}$. The covariance matrix is
$$
\Sigma=\begin{pmatrix}I_m&a\\a^{\mathsf T}&1\end{pmatrix}.
$$
Its diagonal entries are one, and for $x\in\mathbb R^m$ and $y\in\mathbb R$,
$$
(x^{\mathsf T},y)\Sigma(x^{\mathsf T},y)^{\mathsf T}
=\lVert x+ya\rVert^2\geq0,
$$
since $\lVert a\rVert=1$. All coordinates are affine functions of the same independent Gaussian vector, so their joint law is exactly Gaussian. The covariance eigenvalues are $0$, $2$, and $1$ with multiplicity $m-1$; singularity is admissible.

### H4

Use exactly
$$
p_i=2\overline\Phi(|T_i|),\qquad I_0=\{1,\ldots,m\}.
$$
The null p-values $U_i=p_i$ for $1\leq i\leq m$ are independent Uniform$(0,1)$ variables. No independence between the alternative p-value and these null p-values is assumed or used.

### H5

Let $R$ and $V$ be the rejection and false-rejection counts from ordinary BH at level $q$, using the largest qualifying rank in the entire $N$-coordinate vector. Its FDR is $\mathbb E[V/(R\vee1)]$, including samples where a larger BH crossing overrides a smaller one.

### NOT

The proposed asymptotic violation fails. In fact, one alternative cannot create the required inflation when the null p-values are independent, regardless of how that alternative depends on them.

Write $U_{(1)}\leq\cdots\leq U_{(m)}$ for the ordered null p-values. On an outcome with $V=k\geq1$, there are at most $k+1$ total rejections because there is only one alternative. The BH cutoff is $qR/N$, so
$$
U_{(k)}\leq \frac{qR}{N}\leq\frac{q(k+1)}N.
$$
Consequently, without conditioning on the alternative,
$$
\operatorname{FDR}\leq\Pr(V>0)
\leq\sum_{k=1}^m\Pr\!\left\{U_{(k)}\leq\frac{q(k+1)}N\right\}.
$$
For $x\in[0,1]$, a union bound over subsets of $k$ null coordinates gives
$$
\Pr\{U_{(k)}\leq x\}\leq\binom mk x^k.
$$
Here $x=q(k+1)/N\leq q<1$. Using $\binom mk\leq(em/k)^k$, $m/N\leq1$, and $(k+1)/k\leq2$, we obtain
$$
\Pr\!\left\{U_{(k)}\leq\frac{q(k+1)}N\right\}
\leq (2eq)^k.
$$
Thus, for $q<1/(2e)$,
$$
\operatorname{FDR}\leq\sum_{k=1}^m(2eq)^k
\leq\frac{2eq}{1-2eq},
$$
and therefore
$$
0\leq\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}
\leq\frac{2e}{(1-2eq)\sqrt{\log(1/q)}}\longrightarrow0.
$$
The bound is uniform over $m$, the alternative mean, and the alternative's dependence on the independent nulls. It therefore treats the entire specified gate family, rather than a finite-level numerical instance.

## Failure

NOT fails: independent nulls and at most one arbitrarily dependent alternative force FDR $O(q)$, even at exact covariance singularity and the prescribed superpolynomial dimension and diverging mean.
