---
type: candidate
title: Single negative-null model at the upper testing-level edge
status: failed
target_asset: gaussian_bh_growing_clone_compensated_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T22:49:51.760Z'
extension_version: 0.0.4
---

## Object

Take the fixed data N=d=1, theta_1=-0.01, Sigma=[1], v_1=1, i=1 and q=0.49. Use the exact compensated private-clone construction in the target. This probes the smallest admissible dimension, a chosen negative mean close to the excluded zero mean, and a level close to 1/2. All limits keep these data fixed.

## Checks

### H1

Pass. N=1 is finite, the mean is fixed and real, and [1] is positive definite with unit diagonal.

### H2

Pass. The fixed q=0.49 belongs to (0,1/2).

### H3

Pass. i=1 is an original coordinate and theta_1=-0.01 is nonzero.

### H4

Pass. G is a scalar standard Gaussian and T_1=-0.01+G uses the finite unit-row representation v_1=1.

### H5

Pass. Use one-sided survival-function p-values and ordinary largest-rank, non-strict BH. The original null set is {1}; the original FDR is F=S(u-theta_1), with u=S^{-1}(q).

### H6

Pass. Each finite array has precisely K copies of the sole group, with independent standard Gaussian private marks independent of G, score theta_1+d_epsilon+sqrt(1-s^2)G+s xi_b, and the stated d_epsilon=s(t_s+1/t_s). No other group exists. Original-coordinate signed jumps and the order K first, epsilon second are retained.

### H7

Pass. Since d_epsilon tends to zero, theta_1+d_epsilon remains negative for every sufficiently small epsilon. Every expanded coordinate is a true null.

### NOT

Fail. Both conclusions hold for this object, including the signed coefficient. Here is a direct calculation, independent of the target proof.

Write Phi=1-S and, conditionally on G, m=theta_1+d_epsilon+sqrt(1-s^2)G. At population mass x in (0,1), a crossing exists precisely when

$$
m\ge S^{-1}(qx)-sS^{-1}(x).
$$

Consequently define

$$
M_s=\min_{t\in\mathbb R}\{S^{-1}(q\Phi(t))+st\}.
$$

The function being minimized tends to positive infinity at both ends for 0<s<1, so its minimum is attained. Apart from the conditional event m=M_s, a crossing exists if and only if m>M_s, and it then has a non-tangent largest endpoint with b(x)=x. The event m=M_s has Gaussian probability zero. Because all copies are null, the population FDP is exactly the indicator that a crossing exists.

For completeness, finite-copy BH has the same limiting rejection indicator. If m>M_s, some interior x has b(x)>x, and empirical convergence gives a qualifying finite rank. If m<M_s, the continuous ratio b(x)/x has supremum strictly below 1: its limit at zero is 0 for s<1 and its value at 1 is below 1. Uniform empirical convergence excludes masses bounded away from zero. For small masses, b(x)/x tends to 0; if b(x)<=eta*x for x<=delta, a binomial Chernoff bound and a union over ranks r<=delta*K bound the probability by sum_{r>=1}(e*eta)^r. Sending delta to zero sends eta to zero. Thus finite rejection probability tends to zero below M_s. Bounded convergence over G gives

$$
F_{\infty,\varepsilon}=\mathbb E D_\varepsilon
=S\left(\frac{M_s-\theta_1-d_\varepsilon}{\sqrt{1-s^2}}\right).
$$

To expand M_s, its minimizers t tend to positive infinity as s tends to zero. At a minimizer put x=Phi(t) and u_x=S^{-1}(qx). Differentiation gives exactly

$$
\phi(t)=s x h(u_x).
$$

Since x tends to 1 and u_x tends to u, comparison with phi(t_s)=s gives

$$
t=t_s-\frac{\log h(u)}{t_s}+o(t_s^{-1}).
$$

The Gaussian tail expansion S(t)=phi(t)/t*(1+o(1)) and the derivative of S^{-1}(qx) give u_x-u=s/t*(1+o(1)). Hence

$$
M_s=u+s(t_s+t_s^{-1})-\frac{s}{t_s}\log h(u)+o(s/t_s).
$$

The variance normalization contributes O(s^2)=o(s/t_s). Therefore

$$
\frac{F_{\infty,\varepsilon}-F}{s/t_s}
\longrightarrow \phi(u-\theta_1)\log h(u).
$$

For the original singleton model the only face jump is +1, so mu_{1,1}(R^0)=phi(u-theta_1). The target right side is exactly the expression above, including its negative sign here.

A short standard-library numerical contact calculation gives u=0.0250689083, h(u)=0.8139121274 and predicted coefficient -0.0820928651. At s=10^-4, 10^-6 and 10^-8 the scaled differences are approximately -0.0567775, -0.0649929 and -0.0691714; these are finite-scale diagnostics only. They illustrate the slow approach in t_s and do not establish the limit.

## Failure

NOT fails: the smallest admissible negative-null model satisfies both the population representation and the proposed compensated variation.
