---
type: candidate
title: Conditionally deterministic common zero atom
status: failed
target_asset: gaussian_bh_conditional_compound_calibration
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
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:48:26.048Z'
extension_version: 0.0.4
---

## Object

Set $N=2$, $I_0=\{1,2\}$, and $q=1/10$. Let $Z$ be Bernoulli with success probability $1/2$ and set $P_1=P_2=Z$. At $z\in\{0,1\}$ use the product kernel $\delta_z\otimes\delta_z$. Extend the kernel constantly by $\delta_1\otimes\delta_1$ outside these two points.

## Checks

### H1

The dimension is a positive integer, the null set is fixed, and $q\in(0,1)$.

### H2

All coordinates are in $[0,1]$, and $Z$ is real. The displayed Borel kernels give the correct conditional joint distribution. Given each value of $Z$ both coordinates are deterministic; their joint conditional law is exactly the product of their coordinate laws. Their marginal dependence does not violate conditional independence.

### H3

At $z=0$, each coordinate CDF is $1$ for every $t\geq0$, so
$$
M_q(0)=\sup_{0<t\leq q}\frac{2}{2t}=\infty.
$$
At $z=1$, each CDF is zero for $0\leq t\leq q$, hence $M_q(1)=0$ and $K_q(1)=1$. These are measurable extended-real quantities. Rational levels tending to zero already witness the infinite supremum.

### H4

If $Z=0$, the largest qualifying rank is $2$, both nulls are rejected, and FDP equals $1$. If $Z=1$, no rank qualifies and FDP equals $0$. Counts and null labels are the prescribed ones.

### NOT

At $Z=0$ the asserted right side is $1$ by the target's explicit infinite-envelope convention, matching the conditional FDP. At $Z=1$ it is $1/5$, exceeding conditional FDP zero. The unconditional FDR is $1/2$, and the expected upper bound is $(1+1/5)/2=3/5$. Both conclusions hold, so NOT fails.

## Failure

NOT fails: the zero-atom state has infinite envelope and bound $1$, while the other state has no rejections.
