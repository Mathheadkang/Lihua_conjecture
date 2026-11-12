---
type: candidate
title: >-
  Dense spherical null grid in three dimensions with rare fourth-direction
  alternatives
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
round: 2
slot: 2
direction: extremal
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T20:05:08.223Z'
extension_version: 0.0.4
---

## Object

For $0<q\le\overline\Phi(4)$ put $U=\overline\Phi^{-1}(q)\ge4$,
$$
L=2\lceil50q^{-20}\rceil,\qquad M=L^2,\qquad A=L,\qquad N=M+A.
$$
For $1\le j,k\le L$, let
$$
z_j=-1+(2j-1)/L,\qquad \varphi_k=(2k-1)\pi/L,
$$
$$
v_{jk}=(\sqrt{1-z_j^2}\cos\varphi_k,\sqrt{1-z_j^2}\sin\varphi_k,z_j,0).
$$
Let $G\sim N_4(0,I_4)$. The $M$ null coordinates are $T_{jk}=v_{jk}\cdot G$, and the $A$ alternative coordinates are identical copies of $U^{-1}+G_4$. Use the original full ordinary one-sided BH procedure at level $q$. The full covariance has rank four; the null loading span has dimension three. Distinct null direction count tends to infinity, and the grid contains antipodal directions. The alternative fraction $A/N=1/(L+1)$ tends to zero.

## Checks

### H1

$N$ is a finite positive integer for every $q$, although it grows rapidly as $q$ decreases. The theorem permits this dependence.

### H2

The $M$ null means are zero and the $A$ alternative means are $U^{-1}>0$. Thus the original one-sided null set is exactly the grid coordinates.

### H3

Let $B$ have rows $v_{jk}$ for the nulls and $e_4$ for the alternatives. Then $\Sigma=BB^{\mathsf T}$ is positive semidefinite, symmetric, and has unit diagonal. The sphere grid spans the first three coordinates and the alternatives add $e_4$, giving rank four. Antipodal grid pairs have covariance $-1$.

### H4

$T=\theta+BG$ is exactly jointly Gaussian, with allowed singularities from the clones.

### H5

All p-values are $\overline\Phi(T_i)$ and BH uses the largest crossing, all multiplicities, original labels, and denominator $N$. Every rejected coordinate satisfies $T_i\ge U$, since its p-value is at most $qR/N\le q$. Therefore any rejected alternative requires
$$
G_4\ge U-U^{-1}.
$$
If no alternative is rejected and $R>0$, put $t=\overline\Phi^{-1}(qR/N)\ge U$. Let $f_M(r,t)$ be the fraction of null grid coordinates with statistic at least $t$, for $r=\sqrt{G_1^2+G_2^2+G_3^2}$. Then, for the actual full BH rank,
$$
f_M(r,t)=R/M=(N/M)\overline\Phi(t)/q\ge\overline\Phi(t)/q.
$$
This necessary condition retains the original largest crossing; it is not a rank-selection surrogate.

### NOT

Fails by the following exact finite-grid bound. Partition $S^2$ using $L$ equal intervals in height $z$ and $L$ equal intervals in azimuth. The $M=L^2$ cells have equal surface area and representatives $v_{jk}$. Every point of a cell lies within Euclidean distance $10/\sqrt L\le\delta:=q^{10}$ of its representative. If a representative has dot product at least $t$ with the first three coordinates of $G$, its entire cell has dot product at least $t-r\delta$. Hence, whenever the right side is relevant and positive,
$$
f_M(r,t)\le\max\{0,(1-t/r+\delta)/2\}.
$$
Here the cap formula uses the exact fact that a uniform point of $S^2$ has a coordinate uniform on $[-1,1]$; there is no random approximation to the covariance.

Set $r_0=\sqrt{U^2+2\log U}$. Suppose $r\le r_0$ and an actual null-only BH crossing exists. Positivity of $f_M$ implies
$$
U\le t\le r(1+\delta)\le t_{\max}:=r_0(1+\delta).
$$
For $U\ge4$, $\delta\le U^{-4}$, $t_{\max}\le5U/4$, and
$$
(t_{\max}^2-U^2)/2=\log U+(\delta+\delta^2/2)(U^2+2\log U)\le\log U+1/4.
$$
The elementary Gaussian hazard bound $h(x)=\phi(x)/\overline\Phi(x)\le x+x^{-1}$ for $x>0$ gives
$$
\frac{\overline\Phi(t)}q\ge\frac{U}{t_{\max}}e^{-(t_{\max}^2-U^2)/2}\ge\frac{4e^{-1/4}}{5U}>\frac1{2U}.
$$
On the other hand,
$$
f_M(r,t)\le\frac{r_0-U}{2r_0}+\frac\delta2\le\frac{\log U}{2U^2}+\frac1{2U^4}<\frac1{2U}.
$$
This contradicts the actual-rank condition from H5. Thus a false rejection with no alternative rejected forces $r>r_0$.

Consequently the full original FDR satisfies
$$
\operatorname{FDR}\le P\{\chi_3>r_0\}+\overline\Phi(U-U^{-1}).
$$
The exact radial tail and the upper Mills bound give
$$
P\{\chi_3>r_0\}=2\overline\Phi(r_0)+\sqrt{2/\pi}\,r_0e^{-r_0^2/2}
\le\sqrt{2/\pi}(r_0+r_0^{-1})e^{-r_0^2/2}
\le4q(U+U^{-1}),
$$
where $e^{-r_0^2/2}=e^{-U^2/2}/U$, $r_0+r_0^{-1}\le2U$, and the lower Mills bound $e^{-U^2/2}\le\sqrt{2\pi}q(U+U^{-1})$ were used. Also the increasing hazard and $h(U)\le U+U^{-1}$ imply
$$
\frac{\overline\Phi(U-U^{-1})}{q}\le e^{1+U^{-2}}<3.
$$
Combining these inequalities and using $U\ge4$ yields
$$
\operatorname{FDR}\le4q(U+U^{-1})+3q\le5qU.
$$
Therefore the normalized FDR remains bounded, and NOT fails. This computation handles a concrete null-span-three extremal family with a growing signed grid, but not arbitrary three-dimensional null populations, null-span growth, or many angularly coupled alternative gates. In particular the union bound over the single rare alternative gate does not supply a model-adaptive payment in those settings.

## Failure

NOT fails: exact spherical-cap counting forces an actual null-only BH crossing beyond radius $\sqrt{U^2+2\log U}$; the remaining rare alternative gate has probability less than $3q$, giving original FDR at most $5qU$.
