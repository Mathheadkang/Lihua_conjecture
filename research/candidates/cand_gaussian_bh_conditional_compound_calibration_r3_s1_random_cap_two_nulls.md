---
type: candidate
title: >-
  Continuous conditioning across the cap with two active nulls and a random
  nonnull
status: failed
target_asset: gaussian_bh_conditional_compound_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T16:05:02.429Z'
extension_version: 0.0.4
---

## Object

Set N=3, q=1/10, and keep the original null set I_0={1,2}. Let Z,U_1,U_2,W be independent uniforms on [0,1]. Put

$$
a(z)=\frac15+\frac35z,\qquad b(z)=\frac{a(z)}2.
$$

For i=1,2 let P_i=1/30 if U_i<=b(Z), and P_i=1 otherwise. Set P_3=0 if W<=1/2, and P_3=1 otherwise. The third coordinate is an original nonnull throughout; its zero atom is not a null atom. This differs from the prior one-active-null family: two nulls interact and the nonnull itself is random. It tests the transition 2qK_q=1 under a continuous conditioning law.

## Checks

### H1

N=3 is an integer at least one.

### H2

I_0={1,2} is a fixed subset of {1,2,3}; no labels change with Z or with a BH outcome.

### H3

q=1/10 belongs to (0,1).

### H4

Every coordinate takes values in {0,1/30,1}, a subset of [0,1]. The probabilities b(z) range from 1/10 to 2/5.

### H5

Z is real-valued. For every z, the conditional coordinate laws are the product of the two Bernoulli-atom null laws and the independent Bernoulli-atom nonnull law, since U_1,U_2,W are independent of Z and of each other. The displayed measurable kernels give regular conditional laws. Individual conditional superuniformity is not required.

### NOT

For every z the summed null CDF is zero below 1/30 and a(z) on [1/30,q]. Thus

$$
M_q(z)=\frac{a(z)}{3(1/30)}=10a(z),\qquad K_q(z)=10a(z),
\qquad \min\{1,2qK_q(z)\}=\min\{1,2a(z)\}.
$$

The envelope is finite everywhere. Its cap changes at z=1/2, where a(z)=1/2. This tests both the nonsaturated and saturated sides without a null atom at zero.

Let S be the number of null coordinates equal to 1/30 and B the indicator that P_3=0. Conditional on Z=z, S is Binomial(2,b(z)) and B is an independent Bernoulli(1/2). Exactly those S+B coordinates are rejected: when S+B>0, rank S+B qualifies because every one of its p-values is at most q/3, while every remaining p-value equals 1>q. If S+B=0 there is no rejection. Hence the actual largest non-strict BH rank gives R=S+B, V=S and FDP=S/((S+B) vee 1), with the original null labels.

Writing a=a(z), b=a/2, direct finite enumeration yields

$$
\begin{aligned}
\mathbb E[\operatorname{FDP}\mid Z=z]
&=\frac12\Pr(S>0)+\frac12\mathbb E\!\left[\frac{S}{S+1}\right]\\
&=\frac12(2b-b^2)+\frac12\left[b(1-b)+\frac23b^2\right]\\
&=\frac{3a}{4}-\frac{a^2}{6}.
\end{aligned}
$$

For a in [1/5,1/2] this is strictly below 2a. For a in [1/2,4/5] it increases to 37/75<1, and is therefore strictly below the capped bound. At the transition it equals 1/3 while the bound equals 1. The unconditional values, integrating the uniform a on [1/5,4/5], are FDR=197/600 and expected bound=17/20. Thus neither conclusion is violated.

## Failure

NOT fails: conditional FDR 3a(z)/4-a(z)^2/6 stays strictly below min{1,2a(z)} throughout the cap transition.
