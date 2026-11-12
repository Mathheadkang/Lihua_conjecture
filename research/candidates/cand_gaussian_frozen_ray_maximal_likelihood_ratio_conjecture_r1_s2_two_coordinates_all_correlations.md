---
type: candidate
title: Small cases with at most two coordinates and arbitrary correlation
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
round: 1
slot: 2
direction: small_cases
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:02:37.013Z'
extension_version: 0.0.4
---

## Object

Consider the entire smallest-size family. For $n=1$, take $\Sigma=(1)$, $Z=X$, and $\omega=(1)$. For $n=2$, take arbitrary $\rho\in[-1,1]$ and $p\in[0,1]$, and set
$$
\Sigma=\begin{pmatrix}1&\rho\\\rho&1\end{pmatrix},\qquad
Z=(X,\rho X+\sqrt{1-\rho^2}Y),\qquad
\omega=(p,1-p),
$$
where $X,Y$ are independent standard normal random variables. Use this same $Z$ for every $w\geq0$ in the target's $L_w$ and $\Lambda$. Let $c,\alpha\geq2$ be arbitrary. The two-coordinate family includes independent, identical, and antipodal coordinates; thus it adds distinct Gaussian directions to the one-coordinate benchmark rather than changing only a scale.

## Checks

### H1

Pass: $n\in\{1,2\}$ is a positive finite integer.

### H2

Pass: the one-coordinate covariance is a correlation matrix. In the two-coordinate case the covariance is symmetric, has diagonal entries one, and has eigenvalues $1+\rho$ and $1-\rho$, both nonnegative. The endpoints $\rho=\pm1$ are allowed singular cases.

### H3

Pass: the displayed linear transformations of independent standard normal variables are centered jointly Gaussian with exactly the displayed covariance, including at the singular endpoints.

### H4

Pass: the weights are deterministic, nonnegative, and sum to one, including $p=0$ and $p=1$.

### H5

Pass: $c,\alpha\geq2$, and the supremum is over the common realization specified in the object.

### NOT

Fail: all three assertions hold uniformly over this entire small-size family. The following bounds provide explicit constants and check the sharp coefficient as well as the order and tail statements.

Write $\overline\Phi=1-\Phi$, and put
$$
M_i=\sup_{w\geq0}e^{wZ_i-w^2/2}=e^{(Z_i^+)^2/2}.
$$
Pointwise,
$$
1\leq\Lambda\leq\sum_i\omega_iM_i\leq\max_iM_i.
$$
Each $Z_i$ is standard normal regardless of its dependence with the others. For $t\geq1$ and $a=\sqrt{2\log t}$, direct Gaussian integration gives
$$
F(t):=\mathbb E\min\{t,M_i\}
=\frac12+\frac{a}{\sqrt{2\pi}}+t\overline\Phi(a)
\leq1+\sqrt{\frac{\log t}{\pi}}.
$$
For the last inequality, $e^{a^2/2}\overline\Phi(a)\leq1/2$: its derivative is negative for $a>0$ by $a\overline\Phi(a)<\phi(a)$, and its value at zero is $1/2$.

The case $n=1$ has $\Lambda=M_1$ exactly, hence $\mathbb E\min\{c,\Lambda\}=F(c)$ and $\mathbb P\{\Lambda\geq\alpha\}=\overline\Phi(\sqrt{2\log\alpha})$. Thus even the smallest exact benchmark does not violate any assertion.

For both sizes, omit any zero weights. The elementary inequality $\min\{c,\sum_i a_i\}\leq\sum_i\min\{c,a_i\}$ for nonnegative $a_i$ yields
$$
\begin{aligned}
\mathbb E\min\{c,\Lambda\}
&\leq\sum_{i:\omega_i>0}\omega_iF(c/\omega_i)\\
&\leq1+\frac1{\sqrt\pi}\sum_{i:\omega_i>0}\omega_i\sqrt{\log c+\log(1/\omega_i)}\\
&\leq1+\sqrt{\frac{\log c+H(\omega)}{\pi}}\\
&\leq\sqrt{\frac{\log c}{\pi}}+1+\sqrt{\frac{\log2}{\pi}},
\end{aligned}
$$
where Jensen's inequality gives the third line and $H(\omega)=\sum_{\omega_i>0}\omega_i\log(1/\omega_i)\leq\log n\leq\log2$. Therefore the sharp assertion holds here with $C_{\mathrm{sh}}=1+\sqrt{\log2/\pi}$. Because $c\geq2$, the same estimate gives the order assertion with
$$
C_{\mathrm{ord}}=\frac1{\sqrt{\log2}}+\frac2{\sqrt\pi}.
$$
Finally, the pointwise maximum bound and a union bound, followed by the Gaussian Mills inequality, give
$$
\begin{aligned}
\mathbb P\{\Lambda\geq\alpha\}
&\leq n\overline\Phi(\sqrt{2\log\alpha})\\
&\leq\frac{n}{2\sqrt\pi\,\alpha\sqrt{\log\alpha}}
\leq\frac{1/\sqrt\pi}{\alpha\sqrt{\log\alpha}}.
\end{aligned}
$$
Thus $C_{\mathrm{tail}}=1/\sqrt\pi$ works uniformly over all weights and correlations in the two smallest sizes. These estimates rule out this family only; their entropy and union-bound dependence does not establish the target for unbounded dimension.

## Failure

NOT fails: all three bounds hold uniformly when $n\leq2$, with explicit constants independent of the weights and correlation, including singular endpoints.
