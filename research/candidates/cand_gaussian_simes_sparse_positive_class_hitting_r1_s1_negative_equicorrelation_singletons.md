---
type: candidate
title: Extreme negative equicorrelation -1/(N-1) (only singleton positive classes)
status: failed
target_asset: gaussian_simes_sparse_positive_class_hitting
checks:
  H1: pass
  H2: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 890cfc3a9c9940c136cc16ee0457d5a898e3cb8394ae61c9b578e3710d695ad7
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:27:45.478Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Any candidate constants, $\alpha\in(0,\alpha_1]$, $N\ge2$, and the boundary equicorrelation matrix
$$
\Sigma=\tfrac{N}{N-1}\bigl(I-\tfrac1NJ\bigr),\qquad \Sigma_{ii}=1,\ \Sigma_{ij}=-\tfrac1{N-1}\ (i\ne j),
$$
the most negative admissible common correlation (rank $N-1$). Every off-diagonal entry is negative, so the positive classes are exactly the singletons: the "many weakly negatively correlated coordinates, no positive class of size $\ge2$" case.

## Checks

### H1

$\Sigma$ is $\tfrac N{N-1}$ times an orthogonal projection, so PSD, symmetric, unit diagonal: $\Sigma\in\mathcal C_N$.

### H2

pass.

### NOT

Prior side (this is where $\Sigma$ is hard for the lemma). With singleton classes, $c\,|S|\,r_\alpha/N=c\,r_\alpha/N\le1$, so $\{i\}$ is hit iff $i\in\mathcal A_\alpha$, and $h=\pi(\mathcal A_\alpha)$ for $\pi=\sum_iw_i\delta_{\{i\}}$. On $E_\alpha\setminus D_{\alpha,\delta_0}$ one has $1\le r_\alpha<k_0:=N\overline\Phi(u_\alpha+\delta_0)/\alpha$ (since $r_\alpha=\widehat k_\alpha$ is itself a crossing), so $\mathcal A_\alpha\subseteq\{p_i\le\overline\Phi(u_\alpha+\delta_0)\}$ and
$$
\mathbb P(E_\alpha\setminus D_{\alpha,\delta_0},\ h\ge c_*)\le\frac{\mathbb E[\pi(\mathcal A_\alpha);E_\alpha\setminus D]}{c_*}\le\frac{\overline\Phi(u_\alpha+\delta_0)}{c_*}\le\frac{\alpha}{c_*}.
$$
So no prior helps: the conclusion holds for this $\Sigma$ iff $\mathbb P(E_\alpha\setminus D_{\alpha,\delta_0})\le1/4+O(\alpha/c_*)$.

Event side (this is where NOT fails). Let $G\sim\mathcal N(0,1)$ be independent of $T$ and $W=T+(N-1)^{-1/2}G\mathbf 1$. Then $\mathrm{Cov}(W)=\Sigma+J/(N-1)=c^2I$ with $c^2=N/(N-1)$, i.e. $W_i=cY_i$, $Y_i$ iid standard. On $\{G\ge0\}$, $W\ge T$ coordinatewise and the Simes/BH crossing event is monotone, so $\tfrac12\mathbb P(E_\alpha)\le\mathbb P(\text{Simes rejects for }p^W)$, $p^W_i=\overline\Phi(W_i)$. The CDF $F(x)=\overline\Phi(\overline\Phi^{-1}(x)/c)$ of $p^W_i$ satisfies, for $x\in[\alpha/N^2,\alpha]$ and $t=\overline\Phi^{-1}(x)\in(0,\sqrt{2\log(N^2/\alpha)}]$ (using $1-c^{-1}\le1/N$, $t^2(1-c^{-2})=t^2/N$ and the Mills bound $\overline\Phi(t)\ge t\varphi(t)/(1+t^2)$),
$$
\frac{F(x)}{x}\le1+\frac{(1+t^2)e^{t^2/(2N)}}{N}=:1+\varepsilon_{N,\alpha}\to1\quad(N\to\infty,\ \alpha\text{ fixed}).
$$
Coupling each $\max(p^W_i,\alpha/N^2)$ with a uniform $U_i\le(1+\varepsilon)\max(p^W_i,\alpha/N^2)$ on $\{p^W_i\le\alpha\}$ (quantile transform) and using Simes' equality for iid uniforms gives $\mathbb P(\text{Simes}(p^W))\le(1+\varepsilon_{N,\alpha})\alpha+N F(\alpha/N^2)\le(1+\varepsilon_{N,\alpha})\alpha(1+1/N)$. Hence $\mathbb P(E_\alpha)\le2(1+\varepsilon_{N,\alpha})(1+1/N)\alpha$, which is $\le5\alpha$ once $\varepsilon_{N,\alpha}\le1/4$. For the remaining small $N$ use the arbitrary-dependence bound $\mathbb P(E_\alpha)\le\alpha H_N$, $H_N=\sum_{j\le N}1/j$ (proof: on $E_\alpha$, $1=\sum_i\mathbf 1\{p_i\le\alpha r_\alpha/N\}/r_\alpha\le\sum_i\sum_{j\le N}\mathbf 1\{\alpha(j-1)/N<p_i\le\alpha j/N\}/j$, whose expectation is $\alpha H_N$ since $p_i$ is uniform). The threshold $N$ with $\varepsilon_{N,\alpha}\le1/4$ is polynomial in $\log(1/\alpha)$, far below $e^{1/(4\alpha)-1}$, so for all sufficiently small $\alpha$ one gets $\mathbb P(E_\alpha)\le1/4$ for every $N$. NOT fails.

## Failure

NOT fails: although only singleton positive classes exist (so $h\le\pi(\mathcal A_\alpha)$ and no prior can satisfy the hitting requirement on $E\setminus D$), the weak negative equicorrelation is a Gaussian perturbation of independence and $\mathbb P(E_\alpha)\le 5\alpha<1/4$.
