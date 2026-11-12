---
type: candidate
title: Singular Cantor alternatives near the testing cutoff
status: failed
target_asset: spherical_isotropic_population_bh_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 3
slot: 4
direction: known_counterexamples
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, and $q=2Q(u)$. Let $(B_j)_{j\geq1}$ be independent Bernoulli variables with parameter $1/2$, and put
$$
C=\sum_{j=1}^{\infty}\frac{2B_j}{3^j},\qquad
W=\frac12\delta_0+\frac12\operatorname{Law}(u+C/u).
$$
Thus the alternative mean law is the singular continuous Cantor law translated and scaled into $[u,u+u^{-1}]$. Use population measure $W\otimes\sigma_3$, $Z\sim N(0,I_4)$, and statistics $T_{\mu,v}=\mu+v^\top Z$ with no residual noise. Use exactly the smallest finite admissible Gaussian-statistic cutoff in the target; absent a finite contact, the FDP is zero.

This tests a pathological Borel mean law rather than the previously considered alternative-support restriction $[4u,\infty)$. All its alternative means lie below $4u$.

## Checks

### H1

The integer dimension is $d=4\geq4$.

### H2

The statistics are exactly $T_{\mu,v}=\mu+v^\top Z$, so their residual variance conditional on $Z$ is zero.

### H3

The series for $C$ converges absolutely into $[0,1]$ and is a measurable function of the Bernoulli sequence. Hence its law and $W$ are Borel probability measures on $[0,\infty)$. The alternative means are positive, so $\pi_0=W(\{0\})=1/2$. The Cantor component has no atoms: specifying its first $n$ digits has probability $2^{-n}$, and any point has at most two digit representations.

### H4

The population measure is the product $W\otimes\sigma_3$. Its conditional directional kernel is exactly the uniform measure $\sigma_3$ at every absolute mean, independent of that mean.

### H5

The strict Gaussian-tail monotonicity gives $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

For each $r>0$ use
$$
x_r=\min\{x\geq u:F_r(x)\geq Q(x)/Q(u)\}
$$
when this set is nonempty, and otherwise use $x_r=\infty$ with FDP zero. At a finite contact use $q\pi_0H_r(x_r)/Q(x_r)$. These are exactly the target's threshold and FDP definitions.

### NOT

The conclusion does not fail. An exact cutoff comparison gives
$$
\operatorname{FDR}_{\mathrm{pop}}\leq8q\pi_0,
$$
strictly below the proposed bound for this object.

To prove the comparison, define the finite number $b>u$ by $Q(b)=Q(u)/8$. For $h>0$, translating the Gaussian integral gives
$$
\frac{Q(u+h)}{Q(u)}
<\exp(-uh-h^2/2).
$$
With $h=3/u$, the right side is below $e^{-3}<1/8$, so $b<u+3/u$.

For $d=4$, the first spherical coordinate has density $(2/\pi)\sqrt{1-s^2}$ on $[-1,1]$. Consequently, for $0\leq t/r\leq1$,
$$
H_r(t)\geq\frac12-\frac{2t}{\pi r},
$$
and $H_r(t)\geq1/2$ when $t\leq0$. If $r\geq b$ and $\mu\geq u$, then $(b-\mu)_+/r<3/u^2<1$ and therefore
$$
H_r(b-\mu)\geq\frac12-\frac{6}{\pi u^2}>\frac14.
$$
Discarding the other nonnegative tails yields
$$
F_r(b)\geq\frac12\int H_r(b-\mu)\,\operatorname{Law}(u+C/u)(d\mu)
>\frac18=\frac{Q(b)}{Q(u)}.
$$
Thus $b$ is admissible and $x_r\leq b$ for every $r\geq b$. For $r<b$, positive FDP requires $H_r(x_r)>0$, hence $x_r<r<b$. At every radius with positive FDP, we therefore have $u\leq x_r\leq b$, and
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
\leq\frac{q\pi_0H_r(u)}{Q(b)}.
$$
For all remaining radii the same nonnegative upper bound holds. For an independent uniform direction $V$, $V^\top Z\sim N(0,1)$, so $\mathbb EH_R(u)=Q(u)$. Taking expectations proves the displayed $8q\pi_0$ bound.

Finally, the target's constant is $M_4=1/\pi$. Since $e<3$ implies $e^5<243<312$ and $\pi<10/3$,
$$
2+\frac4\pi(1+104^{-2})\log(312)
>2+\frac65\cdot5=8.
$$
The additional $e^{-2u^2}$ is positive. The strict comparison uses exact inequalities, without numerical contact optimization or floating-point certification.

## Failure

NOT is the first failed check: the singular continuous weak-alternative law has FDR at most $8q\pi_0$, strictly below the claimed bound.
