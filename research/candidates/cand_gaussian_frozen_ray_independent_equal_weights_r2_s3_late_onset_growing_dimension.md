---
type: candidate
title: Growing dimension with quadratic-log late-onset thresholds
status: failed
target_asset: gaussian_frozen_ray_independent_equal_weights
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 50a2723662d1d1615266b7b08a764c5aeb61551586db2c3dbbdffbb9ea16dccc
performed_by: unknown
created_at: '2026-11-11T00:41:07.929Z'
extension_version: 0.0.4
---

## Object

For every integer $n\geq3$, take $K=n$, independent $Z_1,\ldots,Z_n\sim N(0,1)$, and $c=\alpha=\exp(n^2)$. Use precisely the full frozen-ray field
$$
L_w=\frac1n\sum_{i=1}^n e^{wZ_i-w^2/2},\qquad \Lambda=\sup_{w\geq0}L_w.
$$
This is a joint growing-dimension and diverging-threshold boundary family, rather than a fixed-dimensional variant of the earlier scalar or two-coordinate tests. The calculation below applies only to its stated thresholds.

## Checks

### H1

Pass: $K=n\geq3$ is a positive integer for every member of the family.

### H2

Pass: the coordinates are independent standard normal variables, so their joint law is centered Gaussian with correlation matrix $I_n$.

### H3

Pass: $w$ ranges over all of $[0,\infty)$, and the same Gaussian vector is used for every $w$. There is no truncation or resampling of the ray.

### H4

Pass: $c=e^{n^2}\geq e^9>2$.

### H5

Pass: $\alpha=e^{n^2}\geq e^9>2$.

### NOT

Fail: both asserted inequalities hold with fixed constants on this entire family. Here are explicit bounds, including a tail calculation that uses independence to avoid a dimension factor from the coordinate envelope.

Put $X_i=\exp((Z_i^+)^2/2)$ and $S=\sum_{i=1}^nX_i$. Pointwise $\Lambda\leq S/n$. For $x>1$, Mills' inequality gives
$$
\Pr(X_i>x)=\overline\Phi(\sqrt{2\log x})\leq\frac{1}{2x\sqrt{\pi\log x}}.
$$
Direct integration, with $b=\sqrt{2\log x}$, gives
$$
\mathbb E\min(x,X_i)=\frac12+\sqrt{\frac{\log x}{\pi}}+x\overline\Phi(b).
$$
Because $\min(nc,S)\leq\sum_i\min(nc,X_i)$, these formulas imply
$$
\begin{aligned}
\mathbb E\min(c,\Lambda)
&\leq \mathbb E\min(nc,X_1)\\
&\leq\frac12+\sqrt{\frac{n^2+\log n}{\pi}}+
\frac{1}{2\sqrt{\pi(n^2+\log n)}}\\
&\leq\sqrt{\frac{\log c}{\pi}}+2.
\end{aligned}
$$
For the last inequality, rationalizing the difference of square roots bounds it by $\log n/(2n\sqrt\pi)\leq1/(2\sqrt\pi)$, and the final reciprocal term is at most $1/(2n\sqrt\pi)$.

For the tail let $a=\alpha=e^{n^2}$, $B=na/2$, $\ell=\log B$, and $Y_i=X_i\mathbf1_{\{X_i\leq B\}}$. Independence is preserved by this coordinatewise truncation. Exact integration gives
$$
\mathbb E Y_i=\frac12+\sqrt{\frac\ell\pi}.
$$
Also
$$
\mathbb E Y_i^2=\frac12+\frac1{\sqrt{2\pi}}
\int_0^{\sqrt{2\ell}}e^{z^2/2}\,dz
\leq\frac12+\frac{B}{\sqrt{\pi\ell}}
\leq\frac{2B}{\sqrt\ell}.
$$
Indeed, writing $b=\sqrt{2\ell}$, the relation $b^2-z^2\geq b(b-z)$ on $[0,b]$ bounds the integral by $2e^{b^2/2}/b$. The final inequality uses $\ell\geq9$ and $B=e^\ell\geq\sqrt\ell$.

Since $n^2\leq\ell=n^2+\log(n/2)\leq2n^2$, one has $\mathbb E Y_i\leq1/2+n\leq2n\leq a/2$ for $n\geq3$; the last inequality follows from $e^{n^2}\geq4n$. Consequently the union bound for large coordinates and Chebyshev's inequality for the independent truncated coordinates give
$$
\begin{aligned}
\Pr(\Lambda\geq a)
&\leq\Pr(S\geq na)\\
&\leq n\Pr(X_1>B)+\Pr\left(\sum_iY_i\geq na\right)\\
&\leq\frac{1}{a\sqrt{\pi\ell}}
+\frac{4n\mathbb E Y_1^2}{n^2a^2}\\
&\leq\frac{1/\sqrt\pi+4}{a\sqrt\ell}
\leq\frac{5}{a\sqrt{\log a}}.
\end{aligned}
$$
Thus $C_{\mathrm{sh}}=2$ and $C_{\mathrm{tail}}=5$ suffice on the stated growing-dimension family. This does not establish either constant uniformly over other choices of $c,\alpha$ relative to $K$.

## Failure

NOT fails: at $K=n\geq3$ and $c=\alpha=e^{n^2}$, the moment excess is bounded by $2$ and the normalized tail by $5$, uniformly in $n$.
