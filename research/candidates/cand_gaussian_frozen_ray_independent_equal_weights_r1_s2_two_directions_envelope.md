---
type: candidate
title: Two independent directions admit a sufficient coordinate envelope
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
slot: 2
direction: small_cases
statement_digest: 50a2723662d1d1615266b7b08a764c5aeb61551586db2c3dbbdffbb9ea16dccc
performed_by: unknown
created_at: '2026-11-11T00:38:18.299Z'
extension_version: 0.0.4
---

## Object

Take $K=2$, two independent standard normal coordinates, and arbitrary real $c,\alpha\geq2$. Use the full frozen-ray supremum from the target. Test whether allowing a second coordinate creates an unbounded excess over the sharp moment term or an unbounded normalized maximal tail within this family.

## Checks

### H1

Pass: $K=2$ is a positive integer.

### H2

Pass: $Z_1,Z_2$ are independent $N(0,1)$, so their centered covariance is $I_2$.

### H3

Pass: $L_w=(e^{wZ_1-w^2/2}+e^{wZ_2-w^2/2})/2$ for every $w\geq0$, using the same vector for all $w$. Define $M_i=\exp((Z_i^+)^2/2)$. Coordinatewise optimization provides the upper bound
$$
\Lambda\leq\frac{M_1+M_2}{2}\leq\max(M_1,M_2).
$$
Only an upper bound is used: the two coordinate optimizers need not be the same.

### H4

Pass: $c$ ranges over all real numbers at least $2$.

### H5

Pass: $\alpha$ ranges over all real numbers at least $2$.

### NOT

Fail: put $t_x=\sqrt{2\log x}$. The elementary inequality $\min(C,a+b)\leq\min(C,a)+\min(C,b)$ for nonnegative $a,b$ yields
$$
E\min(c,\Lambda)\leq E\min(2c,M_1)
=\frac12+\sqrt{\frac{\log(2c)}{\pi}}+2c\overline\Phi(t_{2c}).
$$
Gaussian tail integration gives $x\overline\Phi(t_x)\leq1/(2\sqrt{\pi\log x})$. Since $\sqrt{a+b}-\sqrt a\leq\sqrt b$ for nonnegative $a,b$,
$$
E\min(c,\Lambda)-\sqrt{\frac{\log c}{\pi}}
\leq\frac12+\sqrt{\frac{\log2}{\pi}}+\frac{1}{2\sqrt{\pi\log4}}<2.
$$
The coordinate envelope and a union bound also give
$$
P(\Lambda\geq\alpha)\leq2\overline\Phi(t_\alpha)
\leq\frac{1}{\sqrt\pi\,\alpha\sqrt{\log\alpha}}.
$$
Thus $C_{\mathrm{sh}}=2$ and $C_{\mathrm{tail}}=1/\sqrt\pi$ suffice throughout this family. The same envelope bounds each fixed dimension with dimension-dependent constants, but that does not decide whether constants can be uniform in $K$. No finite observation about a large normalized value would disprove existence of the target's unspecified constants.

## Failure

NOT fails: both the sharp-coefficient moment bound and the required tail order hold uniformly in $c,\alpha$ for $K=2$.
