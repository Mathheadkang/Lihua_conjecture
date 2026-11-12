---
type: candidate
title: Dense unit-loading directions at a near-boundary dimension budget
status: failed
target_asset: slow_factor_dimension_one_sided_sharpness
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
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
performed_by: unknown
created_at: '2026-11-04T07:10:23.174Z'
extension_version: 0.0.4
---

## Object

For $0<q<e^{-e}$ let $\ell=\log(1/q)$ and
$$
D(q)=\max\left\{1,\frac{\sqrt\ell}{(\log\ell)^2}\right\},\qquad
d(q)=\lfloor D(q)\rfloor,\qquad M(q)=\lceil e^{\ell^2}\rceil.
$$
Index the tests by every nonzero integer vector $k\in\{-M,\ldots,M\}^{d}$. Put $a_k=k/\|k\|$, $\theta_k=0$, and $T_k=a_k^{\mathsf T}Z$ for $Z\sim N_d(0,I_d)$. This gives $m(q)=(2M+1)^d-1$ finite tests, all loading directions from a very fine rational grid, and zero residual variances. Apply ordinary one-sided BH.

## Checks

### H1

The displayed deterministic budget is finite and at least one. The integer $d=\lfloor D(q)\rfloor$ is always permitted, including levels where the maximum defining $D$ equals one.

### H2

Eventually $D=\sqrt\ell/(\log\ell)^2$, so $D\log\ell/\sqrt\ell=1/\log\ell\to0$. The dimension approaches the growth boundary, with an explicit slowly vanishing ratio.

### H3

Every loading has norm exactly one, the test count is finite at each level, and the joint distribution has the required factor representation. The coordinate loading vectors include all basis vectors, so the covariance rank is $d$, independently of the much larger number of tests. The factors, grid resolution, covariance, and test count may all depend on $q$.

### H4

All means are zero, so all coordinates are true one-sided nulls. The specified p-values and ordinary BH procedure are used.

### NOT

This family does not violate the uniform upper assertion. In the approved finite-level radial bound, $\pi_0=1$ and every $\gamma_k=0$, giving
$$
\operatorname{FDR}\leq q\left(\frac32+\Delta_1(d,q)\right).
$$
The following explicit quantile estimate is uniform in this $q$-dependent $d$. Write $b=b_d(q)$, and $X=\|Z\|^2$. Its moment generating function at $t=(1-1/\ell)/2$ is $\mathbb E e^{tX}=\ell^{d/2}$. Markov's inequality gives
$$
b^2\leq x=\frac{2\ell+d\log\ell}{1-1/\ell},
$$
because $\mathbb P(X>x)\leq e^{-\ell}=q$. Also $b\geq\overline\Phi^{-1}(q)\to\infty$. The normal Mills lower bound $\overline\Phi(b)\geq\phi(b)b/(b^2+1)$ therefore gives
$$
\Delta_1(d,q)
\leq \frac{x}{2}-\ell+\log(b+1/b)+\frac12\log(2\pi)
=O(d\log\ell+\log\ell).
$$
Here $x=O(\ell)$ and $d\log\ell=O(\sqrt\ell/\log\ell)$, with constants independent of the number or orientation of loadings. Hence $\Delta_1=o(\sqrt\ell)$ and this object's FDR divided by $q\sqrt\ell$ tends to zero. Having arbitrarily many saturated loading directions cannot generate an upper-bound violation within this budget.

## Failure

NOT fails: the finite-level radial bound and an explicit uniform chi-square quantile estimate rule out overshoot even for this rapidly growing dense family.
