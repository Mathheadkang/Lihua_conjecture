---
type: candidate
title: >-
  Single-coordinate boundary saturates the leading coefficient but does not
  refute uniformity
status: failed
target_asset: gaussian_frozen_ray_independent_equal_weights
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 50a2723662d1d1615266b7b08a764c5aeb61551586db2c3dbbdffbb9ea16dccc
performed_by: unknown
created_at: '2026-11-11T00:38:18.299Z'
extension_version: 0.0.4
---

## Object

Take the boundary dimension $K=1$ and $Z_1=Z\sim N(0,1)$. Let $c$ and $\alpha$ range independently over $[2,\infty)$, including sequences tending to infinity. Use exactly the stated equal-weight likelihood field and its frozen-realization supremum. This tests the smallest admissible dimension and the divergent truncation and threshold boundaries.

## Checks

### H1

Pass. $K=1$ is a positive integer.

### H2

Pass. The singleton vector is standard normal, and independence of its coordinates is vacuous. Its correlation matrix is $I_1$.

### H3

Pass. The equal weight is $1/K=1$, and the same scalar $Z$ is used for every $w\geq0$:
$$
L_w(Z)=\exp(wZ-w^2/2).
$$
Maximizing the quadratic exponent over the full prescribed half-line gives $w=\max(Z,0)$, hence
$$
\Lambda(Z)=\exp\bigl((\max(Z,0))^2/2\bigr).
$$

### H4

Pass. Both parameters range over their complete allowed domains, $c\geq2$ and $\alpha\geq2$, with natural logarithms and no relationship between the parameters.

### NOT

Fail. Write $\overline\Phi(t)=\mathbb P\{Z\geq t\}$. For $t=\sqrt{2\log c}$, exact integration yields
$$
\mathbb E\min\{c,\Lambda\}
=\frac12+\frac{t}{\sqrt{2\pi}}+c\overline\Phi(t)
=\sqrt{\frac{\log c}{\pi}}+\frac12+c\overline\Phi(\sqrt{2\log c}).
$$
The middle integral is exactly $\int_0^t(2\pi)^{-1/2}\,dz$; the negative half-line contributes $1/2$. For every $t>0$,
$$
\overline\Phi(t)
\leq\frac{1}{t}\int_t^\infty x\frac{e^{-x^2/2}}{\sqrt{2\pi}}\,dx
=\frac{e^{-t^2/2}}{t\sqrt{2\pi}}.
$$
Consequently, uniformly over $c\geq2$,
$$
\mathbb E\min\{c,\Lambda\}
\leq\sqrt{\frac{\log c}{\pi}}+\frac12+\frac{1}{2\sqrt{\pi\log2}}.
$$
Likewise, for every $\alpha\geq2$,
$$
\mathbb P\{\Lambda\geq\alpha\}
=\overline\Phi(\sqrt{2\log\alpha})
\leq\frac{1}{2\sqrt\pi\,\alpha\sqrt{\log\alpha}}.
$$
Thus this entire boundary family satisfies both requested forms with finite absolute constants. As $c\to\infty$, the truncated-moment residual converges to $1/2$, because the displayed tail remainder tends to zero. It saturates the proposed leading coefficient but supplies neither an unbounded additive residual nor an unbounded normalized tail. This only rules out this candidate family; it proves nothing uniform in general $K$.

## Failure

NOT fails: the complete $K=1$ family obeys both inequalities with fixed finite constants, even as the truncation and tail thresholds diverge.
