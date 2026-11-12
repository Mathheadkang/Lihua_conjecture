---
type: candidate
title: One antagonistic alternative with many independent composite nulls
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:36:58.955Z'
extension_version: 0.0.4
---

## Object

For $q\in(0,1/(4e))$, let
$$
L=\log(1/q),\qquad M=\lceil e^{L^2}\rceil,\qquad N=M+1,\qquad \mu_q=\overline\Phi^{-1}(q/N).
$$
Let $Z_1,\ldots,Z_M$ be independent standard normals and define
$$
T_i=-qi/M+Z_i\quad(1\le i\le M),\qquad
T_N=\mu_q-\frac1{\sqrt M}\sum_{i=1}^{M}Z_i.
$$
Use one-sided Gaussian p-values and ordinary BH at level $q$. This tests a small number of alternatives, with a growing number of distinct null directions and a covariance of growing rank. The alternative is negatively correlated with every null and has a mean at its individual Bonferroni critical value. The null means are heterogeneous and strictly negative.

## Checks

### H1

The levels belong to $(0,1)$ and may tend to zero. All parameters are specified separately for every $q$, consistently with the uniform quantifiers.

### H2

$M=\lceil e^{L^2}\rceil$ and $N=M+1$ are finite positive integers at every $q>0$. No explicit array of that size is needed to specify the finite law. Both grow without bound as $q\downarrow0$.

### H3

The mean vector has $\theta_i=-qi/M<0$ for $1\le i\le M$ and $\theta_N=\mu_q>0$. Every entry is finite at each level, since $0<q/N<1/2$. Thus the composite true-null set is exactly $[M]$; no negative true null is discarded.

### H4

Write $u=M^{-1/2}\mathbf1_M$. The covariance is
$$
\Sigma=
\begin{pmatrix}
I_M&-u\\
-u^{\mathsf T}&1
\end{pmatrix}.
$$
It is the Gram matrix of the unit vectors $e_1,\ldots,e_M,-u$ in $\mathbb R^M$, so it is symmetric, positive semidefinite and unit-diagonal. Its rank is $M$, not one. Moreover, for every $b\in\mathbb R^N$,
$$
b^{\mathsf T}(T-\theta)=\sum_{i=1}^{M}(b_i-b_N/\sqrt M)Z_i
$$
is centered normal with variance $b^{\mathsf T}\Sigma b$, including the allowed zero-variance case. Hence the observation is exactly jointly Gaussian.

### H5

Use $p_i=\overline\Phi(T_i)$ and the true-null set $[M]$. Put $U_i=\overline\Phi(Z_i)$ for $i\le M$. These $U_i$ are independent uniforms, and the negative null means imply the pointwise inequalities
$$
p_i=\overline\Phi(Z_i-qi/M)\ge U_i\quad(1\le i\le M).
$$
No assumption about independence between the alternative and the nulls is made.

### H6

Apply ordinary BH with its largest qualifying rank and non-strict thresholds. Its rejection count equals that rank: if more p-values were below the threshold of the largest qualifying rank, their own larger rank would also qualify, a contradiction. Consequently each rejection satisfies $p_i\le qR/N$.

Let $V$ be the number of rejected true nulls and $A$ the number of rejected alternatives. Since there is exactly one alternative, $A\in\{0,1\}$ and $R=V+A$. On $\{V\ge1\}$, the $V$th smallest null p-value satisfies
$$
p^{0}_{(V)}\le q(V+A)/N\le2qV/N.
$$
The coordinatewise inequalities in H5 imply $U_{(V)}\le p^{0}_{(V)}$. Thus, putting $\alpha=2qM/N<2q$, every false discovery implies
$$
\bigcup_{v=1}^{M}\{U_{(v)}\le\alpha v/M\}.
$$

### H7

Use exactly $\operatorname{FDR}=\mathbb E[V/(R\vee1)]$. Since $V/(R\vee1)\le\mathbf1_{\{V\ge1\}}$, H6 gives an explicit bound without assuming a particular behavior of the alternative. For every $v\in[M]$, independence of the $U_i$ and a union bound over $v$-element subsets give
$$
\mathbb P(U_{(v)}\le\alpha v/M)
\le\binom Mv(\alpha v/M)^v
\le\frac{(\alpha v)^v}{v!}
\le(e\alpha)^v.
$$
Here $v!\ge(v/e)^v$. Since $e\alpha<2eq<1/2$, summing the geometric series yields
$$
\operatorname{FDR}
\le\frac{e\alpha}{1-e\alpha}
\le\frac{2eq}{1-2eq}.
$$
All estimates are finite-level and uniform in the displayed enormous dimension.

### NOT

The required violation fails, because
$$
0\le\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}
\le\frac{2e}{(1-2eq)\sqrt{\log(1/q)}}\longrightarrow0.
$$
The argument uses only independence of the centered null coordinates, their nonpositive means, and the existence of at most one alternative. In particular, the same obstruction is uniform in the alternative's finite mean and its allowed joint Gaussian dependence on the nulls. It makes no assertion for dependent nulls or a growing population of alternatives.

## Failure

NOT fails: one alternative can increase the rejection count from $V$ to at most $V+1$, so every false discovery transfers to an independent-uniform crossing at level below $2q$, giving FDR $O(q)$.
