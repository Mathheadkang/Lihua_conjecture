---
type: candidate
title: Rank-one antithetic boundary with a zero weight
status: failed
target_asset: gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:02:37.013Z'
extension_version: 0.0.4
---

## Object

Let $X\sim N(0,1)$, take $n=3$, $v=(1,-1,1)^{\mathsf T}$, $\Sigma=vv^{\mathsf T}$, $Z=vX$, and $\omega=(1/2,1/2,0)$. For every $w\geq0$, use this same realization to define
$$
L_w(Z)=e^{-w^2/2}\cosh(wX),\qquad \Lambda(Z)=\sup_{w\geq0}L_w(Z).
$$
This tests the simultaneous edges of singular covariance, perfect negative correlation, and zero mixture weight. The truncation and tail levels range over all $c\geq2$ and $\alpha\geq2$.

## Checks

### H1

Pass. The dimension $n=3$ is a positive integer.

### H2

Pass. The real matrix $\Sigma=vv^{\mathsf T}$ is symmetric, $a^{\mathsf T}\Sigma a=(a^{\mathsf T}v)^2\geq0$ for every real $a$, and its three diagonal entries are one. Its rank is one and $\Sigma_{12}=\Sigma_{23}=-1$, both allowed.

### H3

Pass. For every $a\in\mathbb R^3$, $a^{\mathsf T}Z=(a^{\mathsf T}v)X$ is centered normal with variance $(a^{\mathsf T}v)^2=a^{\mathsf T}\Sigma a$. Thus $Z\sim\mathcal N_3(0,\Sigma)$, including the permitted degenerate linear combinations.

### H4

Pass. The vector $\omega$ is deterministic, all its entries are nonnegative, and they sum to one.

### H5

Pass. Substitution into the stipulated finite mixture gives the displayed $L_w$. The supremum uses a single $X$ for every real $w\geq0$. Each path is continuous and tends to zero as $w\to\infty$, so its supremum is finite and measurable (equivalently take the supremum over nonnegative rationals).

### H6

Pass. All estimates below hold for every stipulated $c\geq2$ and $\alpha\geq2$.

### NOT

Fail. This object satisfies all three conclusions, with constants $C_{\mathrm{ord}}=4$, $C_{\mathrm{sh}}=2$, and $C_{\mathrm{tail}}=1$.

To check this, put $A=e^{X^2/2}$. For every $w\geq0$,
$$
e^{-w^2/2}\cosh(wX)
=\frac12 e^{w|X|-w^2/2}+\frac12 e^{-w|X|-w^2/2}
\leq\frac12 A+\frac12,
$$
so $\Lambda\leq(A+1)/2$. Write $\overline\Phi$ and $\phi$ for the standard normal upper tail and density. For $t>1$, set $r_t=\sqrt{2\log t}$. Direct integration gives
$$
\mathbb E\min\{t,A\}=\frac{2r_t}{\sqrt{2\pi}}+2t\overline\Phi(r_t).
$$
Consequently, using $\overline\Phi(r)\leq\phi(r)/r$ for $r>0$,
$$
\begin{aligned}
\mathbb E\min\{c,\Lambda\}
&\leq\frac12+\frac12\mathbb E\min\{2c,A\}\\
&\leq\frac12+\sqrt{\frac{\log(2c)}{\pi}}
 +\frac{1}{2\sqrt{\pi\log(2c)}}\\
&\leq\sqrt{\frac{\log c}{\pi}}+2
\leq4\sqrt{\log c}.
\end{aligned}
$$
In the penultimate inequality use $\sqrt{u+v}\leq\sqrt u+\sqrt v$, $\log(2c)\geq\log4$, and
$1/2+\sqrt{\log2/\pi}+1/(2\sqrt{\pi\log4})<2$.
For the last inequality, $1/\sqrt\pi+2/\sqrt{\log2}<4$.

For every $\alpha\geq2$, the same pathwise bound and Mills' inequality give
$$
\begin{aligned}
\mathbb P\{\Lambda\geq\alpha\}
&\leq2\overline\Phi\!\left(\sqrt{2\log(2\alpha-1)}\right)\\
&\leq\frac{1}{(2\alpha-1)\sqrt{\pi\log(2\alpha-1)}}\\
&\leq\frac{1}{\alpha\sqrt{\log\alpha}}.
\end{aligned}
$$
These computations exclude this boundary object as a counterexample; they do not establish the conjecture for general covariance or weights.

## Failure

NOT fails: the antithetic rank-one, zero-weight boundary model obeys the order, sharp truncated-moment, and maximal-tail assertions with explicit constants.
