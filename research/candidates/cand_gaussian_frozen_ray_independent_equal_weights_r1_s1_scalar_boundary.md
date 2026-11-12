---
type: candidate
title: Scalar boundary family attains both target rates without refuting them
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
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 50a2723662d1d1615266b7b08a764c5aeb61551586db2c3dbbdffbb9ea16dccc
performed_by: unknown
created_at: '2026-11-11T00:38:18.299Z'
extension_version: 0.0.4
---

## Object

For each positive integer n, take K=1, Z_1 distributed as N(0,1), and c_n=alpha_n=exp(n). Use the same Z_1 for every w in [0,infinity), with the target's equal-weight field. This is the smallest permitted dimension and an unbounded truncation and threshold family. The calculations below also cover every real c>=2 and alpha>=2 in this dimension.

## Checks

### H1

pass. K=1 is a positive integer for every n.

### H2

pass. The sole coordinate is standard normal; independence of a one-element family holds, and its correlation matrix is I_1.

### H3

pass. With K=1 the exact prescribed frozen field is L_w=exp(w Z_1-w^2/2). Maximizing this concave quadratic exponent on the full interval w>=0 gives w=max(Z_1,0), hence
$$
\Lambda=\exp\{(Z_1^+)^2/2\}.
$$

### H4

pass. c_n=exp(n)>=e>2.

### H5

pass. alpha_n=exp(n)>=e>2.

### NOT

fail. Neither asserted uniform bound is violated by this family, even asymptotically. Let phi and Phi denote the standard normal density and distribution function, and write barPhi=1-Phi. For t>1,
$$
\mathbb P\{\Lambda\ge t\}=\overline\Phi(\sqrt{2\log t}).
$$
For a=sqrt(2 log c), integration of this tail gives the exact identity
$$
\mathbb E\min\{c,\Lambda\}
=\frac12+c\overline\Phi(a)+\frac{a}{\sqrt{2\pi}}
=\sqrt{\frac{\log c}{\pi}}+\frac12+c\overline\Phi(a).
$$
To check the bounded remainder directly, the change of variable z=a+u gives
$$
c\overline\Phi(a)
=\int_0^\infty\phi(u)e^{-au}\,du
\le\frac12.
$$
Thus the moment inequality holds with C_sh=1 throughout this family. As c tends to infinity the remainder tends to 1/2, so the leading coefficient is attained rather than exceeded.

For b=sqrt(2 log alpha)>0, the Gaussian Mills bound follows from
$$
\overline\Phi(b)
\le\frac1b\int_b^\infty z\phi(z)\,dz
=\frac{\phi(b)}b.
$$
Consequently
$$
\alpha\sqrt{\log\alpha}\,\mathbb P\{\Lambda\ge\alpha\}
\le\frac{1}{2\sqrt\pi}.
$$
The ratio tends to 1/(2 sqrt(pi)) as alpha tends to infinity, by the Gaussian Mills asymptotic. The tail therefore has exactly the target order and admits a fixed constant. A lower bound on the necessary constants is not a refutation of their existence; in particular no diverging moment excess or diverging normalized tail arises here.

## Failure

NOT fails: the entire scalar boundary family satisfies both conclusions with dimension-independent constants, while attaining their leading moment coefficient and tail order.
