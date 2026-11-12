---
type: candidate
title: Three correlated interior null loadings remain below the radial bound
status: failed
target_asset: multifactor_radial_fdr_bounds
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 4
direction: small_cases
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:46:27.817Z'
extension_version: 0.0.4
---

## Object

Use the two-sided track with $m=3$, $d=1$, $q=2\overline\Phi(2)$, all means zero, and scalar loadings $(a_1,a_2,a_3)=(1/2,-1/2,1/2)$. For independent standard normal $Z,\varepsilon_1,\varepsilon_2,\varepsilon_3$, set

$$
T_i=a_iZ+\frac{\sqrt3}{2}\varepsilon_i.
$$

The off-diagonal correlations are $(-1/4,1/4,-1/4)$ in the order $(12,13,23)$. All loading norms are strictly between zero and one, and the covariance is positive definite.

## Checks

### H1

Pass. The model is a Gaussian multifactor representation with positive integers $m=3$ and $d=1$, deterministic means and loadings, and independent standard normal factor and residuals. Each loading norm is $1/2$.

### H2

Pass. Apply ordinary BH at level $q$ to the two-sided p-values $P_i=2\overline\Phi(|T_i|)$. The level satisfies $0<q=2\overline\Phi(2)<2\overline\Phi(1)$, and $u_2(q)=2$.

### H3

Pass. All three hypotheses are true nulls, so $I_0=\{1,2,3\}$ and $\pi_0=1$. For every coordinate,

$$
r_i=\frac12,\qquad \gamma_i=\frac1{\sqrt3},\qquad \frac1m\sum_{i\in I_0}\gamma_i=\frac1{\sqrt3}.
$$

### H4

Pass. Since $d=1$, the radial upper-$q$ quantile is $b=\overline\Phi^{-1}(q/2)=2$. Hence $\Delta_2=\log\{q/(2\overline\Phi(b))\}=0$ and $b=u_2(q)$.

### NOT

Fail. Each $P_i$ is marginally uniform. Partition $(0,q]$ into the three intervals $((j-1)q/3,jq/3]$, $j=1,2,3$. If coordinate $i$ is rejected and $P_i$ lies in the $j$th interval, its rejection count satisfies $R\geq j$, since $P_i\leq qR/3$. Thus its contribution to FDP is at most $1/j$. Values above $q$ cannot be rejected. Taking expectations, summing over $i$, and using uniformity yields

$$
\operatorname{FDR}\leq\sum_{i=1}^3\sum_{j=1}^3\frac1j\mathbb P\left(\frac{(j-1)q}{3}<P_i\leq\frac{jq}{3}\right)=q\left(1+\frac12+\frac13\right)=\frac{11q}{6}.
$$

This argument imposes no independence assumption on the p-values. In comparison, the uncapped radial bound is

$$
B=q\left(\frac32+\sqrt{\frac2{3\pi}}\right)>\frac{11q}{6},
$$

because $\pi<6$ implies $\sqrt{2/(3\pi)}>1/3$. The cap at one is inactive: Mills' elementary upper bound gives $q=2\overline\Phi(2)<\phi(2)<1/8$, while $3/2+\sqrt{2/(3\pi)}<5/2$, so $B<5/16<1$.

## Failure

NOT fails: the dependence-free upper bound $11q/6$ is strictly smaller than this model's claimed finite-level radial bound.
