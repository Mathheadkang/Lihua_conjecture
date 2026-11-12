---
type: candidate
title: Arbitrarily large Gaussian mixtures with geometrically unbalanced weights
status: failed
target_asset: gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
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
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:09:30.079Z'
extension_version: 0.0.4
---

## Object

For every integer $n\geq3$, every $r\in(0,1/9]$, and every correlation matrix $\Sigma\in\mathcal C_n$, take $Z\sim\mathcal N_n(0,\Sigma)$ and
$$
\omega_i=\frac{(1-r)r^{i-1}}{1-r^n},\qquad 1\leq i\leq n.
$$
Use the target's frozen realization to define $L_w$ and $\Lambda=\sup_{w\geq0}L_w$. The dimension, rank, correlations and the value of $w$ at the supremum are unrestricted. In particular, $\Sigma=I_n$ gives arbitrarily large effective support and rank.

This family extends beyond the board's bounded-support obstructions: its support is unbounded. The additional summability of the square roots of the weights removes the support factor from the coordinate-envelope tail bound. Thus it tests strongly unbalanced, growing-dimensional objects rather than a parameter variation of a two-coordinate or rank-one object.

## Checks

### H1

Pass: $n\geq3$ is a finite positive integer, with no bound uniform across this family.

### H2

Pass: $\Sigma\in\mathcal C_n$ is symmetric positive semidefinite with unit diagonal. Negative correlations and singular matrices remain allowed.

### H3

Pass: $Z$ has precisely the centered jointly Gaussian law $\mathcal N_n(0,\Sigma)$ required by the target. Every coordinate is standard normal.

### H4

Pass: the displayed weights are deterministic and positive, and the geometric-series identity gives $\sum_i\omega_i=1$.

### H5

Pass: the same $Z$ is used for all real $w\geq0$; the quadratic term is exactly $-w^2/2$. All probabilities below use this fixed centered Gaussian law, and all logarithms are natural. The checks include every real truncation level $c\geq2$ and every real tail level $\alpha\geq2$.

### NOT

Fail: all three target conclusions hold uniformly in this entire family, including growing dimension and arbitrarily late maximizing scales.

Put $M_i=\exp((Z_i^+)^2/2)$. Pointwise completion of the square gives $\Lambda\leq\sum_i\omega_iM_i$. Define $S=\sum_i\sqrt{\omega_i}$. Direct summation gives
$$
S^2=\frac{1+\sqrt r}{1-\sqrt r}\frac{1-r^{n/2}}{1+r^{n/2}}\leq2.
$$
The weight entropy satisfies
$$
H(\omega)\leq H_*=-\log(8/9)+\frac{\log9}{8}.
$$
Indeed, this weight distribution is a geometric distribution conditioned on $i\leq n$, whose mean $i-1$ is at most $r/(1-r)$. Hence
$$
H(\omega)=\log\frac{1-r^n}{1-r}-(\log r)\sum_i(i-1)\omega_i
\leq-\log(1-r)-\frac{r\log r}{1-r}\leq H_*;
$$
the last expression is increasing in $r$, since its derivative is $-\log r/(1-r)^2>0$.

For a standard normal coordinate and $t\geq1$, Gaussian integration gives
$$
\mathbb E\min(t,M_i)=\frac12+\sqrt{\frac{\log t}{\pi}}+t\bar\Phi(\sqrt{2\log t})
\leq1+\sqrt{\frac{\log t}{\pi}}.
$$
For the last inequality, $t\bar\Phi(\sqrt{2\log t})\leq1/2$: writing $x=\sqrt{2\log t}$, the function $e^{x^2/2}\bar\Phi(x)$ decreases for $x\geq0$ by Mills' inequality and equals $1/2$ at zero. Subadditivity of truncation and concavity of the square root therefore yield, for every real $c\geq2$,
$$
\mathbb E\min(c,\Lambda)
\leq\sum_i\omega_i\mathbb E\min(c/\omega_i,M_i)
\leq1+\sqrt{\frac{\log c+H(\omega)}{\pi}}
\leq\sqrt{\frac{\log c}{\pi}}+1+\sqrt{\frac{H_*}{\pi}}.
$$
This proves the sharp assertion with $C_{\rm sh}=1+\sqrt{H_*/\pi}$, and the order assertion with
$$
C_{\rm ord}=\frac1{\sqrt\pi}+\frac{1+\sqrt{H_*/\pi}}{\sqrt{\log2}}.
$$

For every real $\alpha\geq2$, put $\beta_i=\alpha/(S\sqrt{\omega_i})$. If $M_i<\beta_i$ for every $i$, then $\sum_i\omega_iM_i<\alpha$, so a union bound applies without any independence assumption. Since $S\leq\sqrt2$ and $\omega_i\leq1$,
$$
\beta_i\geq\alpha/\sqrt2>1,\qquad
\log\beta_i\geq\tfrac12\log\alpha.
$$
Mills' inequality gives
$$
\mathbb P\{\Lambda\geq\alpha\}
\leq\sum_i\bar\Phi(\sqrt{2\log\beta_i})
\leq\sum_i\frac1{2\sqrt\pi\,\beta_i\sqrt{\log\beta_i}}
\leq\frac{S^2}{\sqrt{2\pi}\,\alpha\sqrt{\log\alpha}}
\leq\frac{\sqrt{2/\pi}}{\alpha\sqrt{\log\alpha}}.
$$
Thus $C_{\rm tail}=\sqrt{2/\pi}$ works uniformly. These constants are independent of $n,r,\Sigma$, covariance rank, $c$ and $\alpha$. This excludes only this summable-weight family; it establishes no bound for arbitrary probability weights.

## Failure

NOT fails: bounded weight entropy and a uniform bound on $\sum_i\sqrt{\omega_i}$ give all three conjectured inequalities despite unbounded dimension and support.
