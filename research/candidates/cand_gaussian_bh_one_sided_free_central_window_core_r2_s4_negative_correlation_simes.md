---
type: candidate
title: >-
  Negative correlation Simes inflation does not violate the central contribution
  bound
status: failed
target_asset: gaussian_bh_one_sided_free_central_window_core
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 4
direction: known_counterexamples
statement_digest: 779c4649ca5118819e8dfa6dbce8e2a5f940384b9968185d078f02aeffa659b9
performed_by: unknown
created_at: '2026-11-06T22:44:14.806Z'
extension_version: 0.0.4
---

## Object

Take two null tests, one factor, means zero, loadings
$a_1=1/\sqrt2$, $a_2=-1/\sqrt2$, and independent standard normal
$Z,\varepsilon_1,\varepsilon_2$. Thus
$T_1=(Z+\varepsilon_1)/\sqrt2$ and
$T_2=(-Z+\varepsilon_2)/\sqrt2$, with correlation $-1/2$.
Use one-sided p-values and $q=0.1$. This examines the familiar
negative-dependence route to Simes/BH inflation, with nonunit, nonzero
loadings rather than the endpoint families on the board.

## Checks

### H1

$N=2,d=1$ are finite positive integers. The displayed independent normal
representation gives unit variances and a positive definite covariance
matrix with off-diagonal entries $-1/2$.

### H2

Both means are zero, so both tests are true nulls in the one-sided track.
$r_1=r_2=s_1=s_2=1/\sqrt2$ and
$\gamma_1=\gamma_2=\sqrt2-1$ are admissible.

### H3

$q=0.1$ satisfies both the kernel scope $0<q<1/2$ and the central
consequence scope $0<q\le1/10$.
Set $U=\overline\Phi^{-1}(0.1)=1.2815515655446006$ and
$b=\overline\Phi^{-1}(0.05)=1.6448536269514715$.

### H4

Use ordinary BH with its largest qualifying rank. The central labels are
$Y_1=Z$ and $Y_2=-Z$ exactly as required. Write
$A(z,t)=\overline\Phi(\sqrt2t-z)$.
Given $Z=z$, the probability that test 1 alone is rejected is
$A(z,b)[1-A(-z,U)]$; the probability both are rejected is
$A(z,U)A(-z,U)$. Symmetry therefore gives

$$
\mathrm{Ce}=2\int_{-\infty}^{U}\phi(z)
\left\{A(z,b)[1-A(-z,U)]+\tfrac12 A(z,U)A(-z,U)\right\}\,dz.
$$

### NOT

Fails for the proposed central-contribution violation. The displayed
integral is approximately $0.041354263598030516$, while the proposed
upper bound is

$$
q\left(\tfrac12+\frac{(\sqrt2-1)U}{\sqrt{2\pi}}\right)
=0.07117729400491944.
$$

An explicit conservative upper calculation avoids relying on the
accuracy of the central integral. Negative correlation implies
$\mathbb P(T_1\ge U,T_2\ge U)\le q^2$: condition on $T_1$, for which
the second exceedance probability is decreasing, whereas
$\mathbf1\{T_1\ge U\}$ is increasing. Consequently

$$
\mathrm{Ce}\le 2\int_{-\infty}^{U}\phi(z)A(z,b)\,dz+q^2.
$$

Put $h=(U+12)/20000$ and $z_j=-12+jh$. Since $A(z,b)$ increases
in $z$, an explicit upper sum for the last display is

$$
2\left\{\overline\Phi(12)+
\sum_{j=0}^{19999}[\Phi(z_{j+1})-\Phi(z_j)]A(z_{j+1},b)\right\}+0.01
\approx0.05107829821429988<0.07117729400491944.
$$

For context, integrating the same conditional rejection expression over
all real $z$ gives FDR approximately $0.1003023335148693>q$.
That inflation does not violate this target's central bound. No general
kernel assertion is refuted or proved by this test.

## Failure

NOT fails: the negative-correlation BH pathology has central contribution below the claimed central bound.
