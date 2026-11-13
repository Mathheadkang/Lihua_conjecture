---
type: candidate
title: Simplex frame at the PSD boundary (equicorrelation -1/(N-1))
status: failed
target_asset: gaussian_mills_penalized_subset_supremum_acceptance
checks:
  H1: pass
  H2: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: d3f1947df037516732eca7aa1a62191594e52c4d36ea06fed769788d4ec0bb33
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:39:54.654Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

For $N\ge2$ let $\Sigma_{ii}=1$ and $\Sigma_{ij}=-1/(N-1)$ for $i\ne j$: the most negative equicorrelation allowed by positive semidefiniteness (the boundary case, rank $N-1$, $\sum_iT_i=0$ a.s.). Realization: $T=c\,(g-\bar g\mathbf 1)$ with $g\sim\mathcal N_N(0,I)$, $\bar g=N^{-1}\sum_ig_i$, $c=\sqrt{N/(N-1)}$. The family is $N\to\infty$; it is the spread weakly negatively correlated configuration of largest total negative correlation.

## Checks

### H1

Pass.

### H2

$\Sigma=\frac{N}{N-1}(I-N^{-1}\mathbf 1\mathbf 1^{\mathsf T})$ is a positive multiple of an orthogonal projection, hence PSD; $\Sigma_{ii}=\frac N{N-1}(1-\frac1N)=1$. Singular, admissible. Pass.

### NOT

Fails with $(A,s_0,\delta_0)=(16,\,25/4,\,0.7)$.

Small $N$ ($N<1000$), any $\Sigma$: on $\{\max_iT_i\le5\}$ every term is $\tau(X_K-\tau)\le\tau(5-\tau)\le25/4$, and $\mathbb P(\max_iT_i>5)\le1000\,\overline\Phi(5)<3\cdot10^{-4}$.

Large $N$ ($N\ge1000$). Let $A'=A/4=4$, let $D$ be the Simes acceptance event of $g$ at level $1/A'$, and $E=\{\bar g\ge-2/\sqrt N\}$. By the Simes identity $\mathbb P(D^c)=1/4$; $\mathbb P(E^c)=\overline\Phi(2)<0.023$; so $\mathbb P(D\cap E)\ge0.727$. On $D$ the Riemann-sum reduction of the independent-coordinates candidate gives $X_K(g)<\tau_{A'}(K)$, so on $D\cap E$
$$
X_K(T)=c\,(X_K(g)-\bar g)<c\,(\tau_{A'}(K)+2/\sqrt N).
$$
It suffices that $\tau_A(K)-\tau_{A'}(K)\ge(c-1)\tau_{A'}(K)+2c/\sqrt N$ for all $K$; then $M_A(T)\le0$.
- Derivative: $\frac d{dp}h(z_p)=-(h(z_p)-z_p)/p$, so $\tau_A(K)-\tau_{A/4}(K)=\int_{\kappa/A}^{4\kappa/A}\frac{h(z_v)-z_v}{v}dv\ge\log4\,(h(z)-z)|_{z=z_{\kappa/A}}$, since $h(z)-z$ decreases ($h'=h(h-z)<1$).
- Mills bounds (Sampford/Birnbaum): $\frac{3z+\sqrt{z^2+8}}4<h(z)<\frac{z+\sqrt{z^2+4}}2$, so $h(z)-z\ge1/(z+2)$ and $h(z)-z\le1$ for $z\ge0$; and $z_p\le\sqrt{2\log(1/p)}$ for $p\le1/2$.
- With $L=\sqrt{2\log(16N)}$: left side $\ge\log4/(L+2)$; $\tau_{A'}(K)\le L+1$; $c-1\le1/(2(N-1))$; $c\le\sqrt2$.

The needed inequality $\log4/(L+2)\ge(L+1)/(2(N-1))+2\sqrt2/\sqrt N$ holds at $N=1000$ ($0.217\ge0.092$), and the ratio of the two sides increases in $N$ (checked numerically on a geometric grid to $10^{15}$; asymptotically $(\log N)^{-1/2}$ against $N^{-1/2}$). Hence $\mathbb P(M_A(T)\le0)\ge0.727$ for $N\ge1000$.

## Failure

NOT fails: the simplex is a codimension-one projection of i.i.d. coordinates, so it inherits the Simes acceptance event at level $4/A$ up to an $O(N^{-1/2})$ shift that the margin $\tau_A-\tau_{A/4}\gtrsim(\log N)^{-1/2}$ absorbs.
