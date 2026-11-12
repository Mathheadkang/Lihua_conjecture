---
type: candidate
title: Growing signed null circle with rare independent alternative clones
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T19:59:50.622Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(1)$, put $U=\overline\Phi^{-1}(q)$, $M=\lceil q^{-1}\rceil$, $A=\lceil\sqrt M\rceil$, and $N=M+A$. Let $G=(G_1,G_2,G_3)$ have independent standard Gaussian coordinates. For $j=0,\ldots,M-1$, set
$$
v_j=(\cos(2\pi j/M),\sin(2\pi j/M),0),\qquad T_j=v_j\cdot G.
$$
The remaining $A$ coordinates are identical alternatives $T_{M+\ell}=U^{-1}+G_3$, $1\le\ell\le A$. Index labels can be shifted to $[N]$ without changing the procedure. Apply ordinary one-sided BH at level $q$ to all $N$ coordinates, including multiplicities. This is a full covariance-rank-three family whose true-null loading span has dimension two, with $M\to\infty$ distinct signed null directions. Alternative fraction $A/N\to0$; their positive means tend to zero.

## Checks

### H1

$N=M+A$ is a finite positive integer for each $q$, with no dimension restriction. The family varies with $q$ as permitted.

### H2

The first $M$ means are zero and the remaining means are $U^{-1}>0$. Thus the one-sided true-null set is exactly the first $M$ coordinates. Negative null means are not needed for this attempted family.

### H3

Let $L$ have first $M$ rows $v_j$ and last $A$ rows $e_3$. Then $\Sigma=LL^{\mathsf T}$ is symmetric positive semidefinite and every diagonal entry is one. Since $M\ge3$, the circle rows span $\mathbb R^2\times\{0\}$; adding $e_3$ gives covariance rank three. Some null-null covariances $\cos(2\pi(j-k)/M)$ are negative, so this is a signed higher-rank model.

### H4

$T=\theta+LG$ is exactly jointly Gaussian with the stated mean and covariance. Clone singularities are allowed.

### H5

The p-values are $p_i=\overline\Phi(T_i)$, and the full largest-crossing BH rule is used without relabeling, deletion, or a changed denominator. If any null is rejected, its p-value satisfies
$$
p_i\le qR/N\le q,\qquad T_i\ge U.
$$
If an alternative is rejected it also satisfies $G_3\ge U-U^{-1}$; the probability of this necessary event is $\overline\Phi(U-U^{-1})\sim e q$, so these alternatives are rare at the actual rejection threshold. This rarity assertion is not used in the FDR bound below.

### NOT

Fails. Let $R,V$ denote the original full BH counts. Since every null loading lies in the first two coordinates and has unit length,
$$
\{V>0\}\subseteq\{\sqrt{G_1^2+G_2^2}\ge U\}.
$$
Consequently, without altering the actual BH rank or discarding any signed covariance term,
$$
\operatorname{FDR}=E[V/(R\vee1)]\le P(V>0)\le e^{-U^2/2}.
$$
The elementary lower Mills bound $\overline\Phi(U)\ge\phi(U)U/(U^2+1)$ gives
$$
\operatorname{FDR}\le\sqrt{2\pi}\,q(U+U^{-1}).
$$
As $q\downarrow0$, $U/\sqrt{\log(1/q)}\to\sqrt2$, so
$$
\limsup_{q\downarrow0}\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}\le2\sqrt\pi<\infty.
$$
Thus this entire family cannot violate the universal-order conclusion. In fact, the same bound holds for arbitrary many null loadings within any fixed two-dimensional subspace, arbitrary nonpositive null means, and arbitrary additional Gaussian alternatives, even if those alternatives increase the full covariance rank. This extension does not cover true-null loading span of dimension three or higher: the corresponding radial tail is larger and no BH-specific payment is established here.

## Failure

NOT fails: the exact two-dimensional null-span radial event bounds the full actual FDR by $e^{-U^2/2}=O(q\sqrt{\log(1/q)})$, uniformly over growing null direction count and rare alternative multiplicities.
