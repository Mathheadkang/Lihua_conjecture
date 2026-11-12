---
type: candidate
title: One independent direction gives the stated sharp coefficient
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

Take the family indexed by arbitrary real parameters $c,\alpha\geq2$, with $K=1$ and $Z\sim N(0,1)$. Use the full frozen-ray supremum from the target. Test whether this smallest dimension violates either asserted bound for every choice of finite universal constants.

## Checks

### H1

Pass: $K=1$ is a positive integer.

### H2

Pass: the single coordinate is standard normal; independence is vacuous. The centered covariance is $I_1$.

### H3

Pass: $L_w=\exp(wZ-w^2/2)$ for all $w\geq0$, with the same realization of $Z$ throughout. Completing the square gives
$$
\Lambda=\exp\bigl((Z_+)^2/2\bigr).
$$

### H4

Pass: $c$ ranges over all real numbers at least $2$.

### H5

Pass: $\alpha$ ranges over all real numbers at least $2$.

### NOT

Fail: this entire family satisfies both bounds, including the proposed sharp coefficient. Write $t_x=\sqrt{2\log x}$ and $\overline\Phi(t)=P(Z\geq t)$. Direct Gaussian integration gives
$$
E\min(c,\Lambda)=\frac12+\sqrt{\frac{\log c}{\pi}}+c\overline\Phi(t_c),\qquad
P(\Lambda\geq\alpha)=\overline\Phi(t_\alpha).
$$
For $t>0$, $\overline\Phi(t)\leq\phi(t)/t$ follows by replacing $1$ in the Gaussian tail integrand by $z/t$. Consequently
$$
c\overline\Phi(t_c)\leq\frac{1}{2\sqrt{\pi\log c}},\qquad
\alpha\sqrt{\log\alpha}\,P(\Lambda\geq\alpha)\leq\frac{1}{2\sqrt\pi}.
$$
Thus $C_{\mathrm{sh}}=1$ and $C_{\mathrm{tail}}=1/(2\sqrt\pi)$ suffice uniformly for this object. In particular the truncated moment has exactly the coefficient $1/\sqrt\pi$, rather than a larger one. This conclusion for $K=1$ does not establish the constants uniformly over arbitrary $K$.

## Failure

NOT fails: exact integration verifies both proposed inequalities for the whole $K=1$ family.
