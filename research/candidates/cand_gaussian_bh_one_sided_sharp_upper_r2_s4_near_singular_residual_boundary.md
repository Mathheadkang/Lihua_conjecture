---
type: candidate
title: >-
  Vanishing residual variance with growing covariance rank and negative null
  means
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
round: 2
slot: 4
direction: boundary_degenerate
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:13:28.581Z'
extension_version: 0.0.4
---

## Object

For every $0<q<e^{-16}$ put
$$
L=\log(1/q),\qquad \sigma=L^{-1/4},\qquad r=\sqrt{1-\sigma^2},\qquad u=\overline\Phi^{-1}(q),
$$
$$
M=2\left\lceil e^{L^2}\right\rceil,\qquad N=2M.
$$
Let $Z,\varepsilon_1,\ldots,\varepsilon_M$ be mutually independent standard normal variables. Define the first $M$ coordinates by
$$
\theta_j=\begin{cases}-q,&j\text{ odd},\\0,&j\text{ even},\end{cases}
\qquad T_j=\theta_j+rZ+\sigma\varepsilon_j,\qquad 1\leq j\leq M.
$$
Define the other $M$ coordinates by
$$
\mu_j=q+\frac{2uj}{M+1},\qquad \theta_{M+j}=\mu_j,\qquad T_{M+j}=\mu_j-Z,\qquad 1\leq j\leq M.
$$
Use $p_i=\overline\Phi(T_i)$, the composite one-sided null set, ordinary BH at level $q$, and its unconditional FDR. This approaches the zero-residual boundary while keeping covariance rank $M+1$, rather than rank one. Both the dimension and all displayed parameters may vary with $q$.

## Checks

### H1

The testing level lies in $(0,1)$ and tends to zero along the whole interval $(0,e^{-16})$; the family is not a test at a single fixed level.

### H2

For each such $q$, $L$ is finite, so $M$ and $N=2M$ are finite positive integers. Every mean is finite and deterministic. The dimension is allowed to grow without restriction as $q\downarrow0$.

### H3

Writing $a=(r,\ldots,r,-1,\ldots,-1)^{\mathsf T}\in\mathbb R^{2M}$, the covariance is
$$
\Sigma=aa^{\mathsf T}+\operatorname{diag}(\underbrace{\sigma^2,\ldots,\sigma^2}_{M},\underbrace{0,\ldots,0}_{M}).
$$
It is symmetric and positive semidefinite. Its first $M$ diagonal entries are $r^2+\sigma^2=1$, and its remaining diagonal entries are $1$. Thus $\Sigma\in\mathcal C_N$. Since $\sigma>0$ and the alternative rows have nonzero loading on $Z$, its rank is $M+1$; its singularity is admissible.

### H4

The entire observation vector is an affine deterministic map of the mutually independent normal vector $(Z,\varepsilon_1,\ldots,\varepsilon_M)$. Hence it has the required joint Gaussian law, including all degenerate linear combinations. This uses actual joint Gaussianity, rather than merely Gaussian marginals.

### H5

The p-values are exactly the prescribed one-sided Gaussian p-values. Since $u>0$, every $\mu_j$ is strictly positive. Consequently
$$
I_0^{(1)}(\theta)=\{1,\ldots,M\},\qquad \pi_0=\frac12.
$$
All $M/2$ coordinates with mean $-q$ are counted as true nulls, together with the $M/2$ zero-mean coordinates.

### H6

The rejection rule is precisely the largest-rank, non-strict-inequality BH rule from the target, with denominator $N$ and level $q$. No dependence correction or replacement of the rejection rule is made.

### H7

The quantity tested is the full-law expectation $\mathbb E[V/(R\vee1)]$, with the true-null set in H5. It is well defined and lies in $[0,1]$ for every finite member of the family.

### NOT

This check fails by direct specialization of the approved [Finite-level radial bounds for Gaussian multifactor BH](../assets/multifactor_radial_fdr_bounds.md). No new general upper-bound theorem is being asserted here.

The displayed model is a [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) with factor dimension $d=1$, null loading $r$, and alternative loading $-1$. The independently indexed residual normals for the alternatives may be included with coefficient zero. Factor dimension one is compatible with covariance rank $M+1$.

The [null loading coefficient](../definitions/gaussian_null_loading_coefficients.md) is
$$
\gamma=\sqrt{\frac{1-r}{1+r}}=\frac{\sigma}{1+r},\qquad \frac1N\sum_{i\in I_0}\gamma_i=\frac{\sigma}{2(1+r)}.
$$
For $d=1$, the radial upper-$q$ quantile $b$ satisfies $2\overline\Phi(b)=q$, so the one-sided correction in that bound is exactly $\Delta_1(1,q)=\log2$. The prescribed small-level range holds. Therefore, uniformly over the very large finite dimension,
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q)
\leq q\left[1+\frac12\left(\frac12+\log2\right)\right]
+\frac{qu}{\sqrt{2\pi}}\frac{\sigma}{2(1+r)}.
$$
Using $u/\sqrt{2L}\to1$, $\sigma=L^{-1/4}\to0$, and $r\to1$, division by the actual target scale gives
$$
0\leq\frac{\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q)}{q\sqrt L}
\leq\frac{1+\frac12(\frac12+\log2)}{\sqrt L}
+\frac{u}{\sqrt{2L}}\frac{\sigma}{2(1+r)\sqrt\pi}
\longrightarrow0.
$$
Thus the growing-rank, vanishing-residual boundary does not violate the proposed asymptotic constant, despite its unrestricted dimension and negative true-null means. This conclusion is scoped to the displayed family, not to general higher-rank Gaussian dependence.

## Failure

NOT fails: the approved one-factor radial bound gives FDR $O(q[1+L^{1/4}])=o(q\sqrt L)$ for this exact growing-rank family.
