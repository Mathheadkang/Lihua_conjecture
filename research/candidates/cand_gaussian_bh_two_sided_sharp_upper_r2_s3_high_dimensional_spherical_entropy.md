---
type: candidate
title: Growing-rank spherical null arrays with superexponential direction count
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: extremal
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:53:53.945Z'
extension_version: 0.0.4
---

## Object

For integers \(j\ge3\), put
$$
q_j=e^{-j},\qquad d_j=j,\qquad \eta_j=e^{-j^3},\qquad \delta_j=\eta_j/j.
$$
Let \(\sigma_d\) be uniform probability measure on \(S^{d-1}\). Choose a deterministic finite multiset of rational unit vectors \(U_j=(u_{j1},\ldots,u_{jN_j})\) satisfying the uniform absolute-cap discrepancy bound
$$
\sup_{v\in S^{j-1},\ s\in[0,1]}
\left|\frac1{N_j}\sum_{i=1}^{N_j}\mathbf1\{|u_{ji}^{\mathsf T}v|\ge s\}
-\sigma_j\{u:|u_1|\ge s\}\right|\le\delta_j.
$$
To fix the choice, use the first such multiset in any fixed enumeration of all finite multisets of rational unit vectors. The existence argument below shows that this instruction defines a finite multiset. No random direction is mixed into the sampling law.

Let \(Z_j\sim\mathcal N_j(0,I_j)\), and define the observed array by
$$
T_{ji}=u_{ji}^{\mathsf T}Z_j,\quad 1\le i\le N_j,\qquad
\theta_j=0,\qquad
(\Sigma_j)_{ik}=u_{ji}^{\mathsf T}u_{jk}.
$$
Use two-sided p-values \(p_{ji}=2\overline\Phi(|T_{ji}|)\) and ordinary BH at level \(q_j\). All coordinates are true nulls. The construction increases both rank and null-direction entropy; it is not a fixed-rank circle or a bounded collection of repeated null types.

## Checks

### H1

The dimensions \(N_j\) are positive finite integers. Here is an elementary existence argument for the discrepancy requirement. Fix \(j\) and \(\delta>0\). The law of \(|u_1|\) under \(\sigma_j\) has no atoms, so its distribution function is uniformly continuous. Consequently, uniformly in \(s\in[0,1]\), the measure of a band \(\{u:||u^{\mathsf T}v|-s|\le h\}\) tends to zero as \(h\downarrow0\); rotational invariance makes this uniform in \(v\).

Partition the compact sphere into finitely many Borel cells of sufficiently small diameter, and choose a rational unit representative within a sufficiently small distance of every point in its cell. Replacing the spherical measure in each cell by an atom of the same weight at this representative changes any absolute-cap probability only by the measure of one such boundary band. This can be made at most \(\delta/2\). Approximate the finitely many cell weights by nonnegative rational weights summing to one, with total absolute error at most \(\delta/2\). A common denominator turns the rational weighted measure into a finite uniform multiset, with discrepancy at most \(\delta\). Rational unit vectors are dense on the sphere, for example by rational stereographic parametrization.

At \(s=1\) and \(v\) equal to any listed direction, the continuous cap mass is zero, so the total empirical mass on the absolute direction \(\{v,-v\}\) is at most \(\delta_j\). If \(K_j\) is the number of distinct absolute directions, their masses sum to one, hence \(N_j\ge K_j\ge1/\delta_j\), and
$$
\log N_j\ge\log K_j\ge j^3+\log j.
$$
Thus this family is outside the earlier obstruction that assumed a sub-square-root-log number of null types. The means and covariance may depend on \(q_j\), as the target permits.

### H2

The mean vector is the real vector \(\theta_j=0\). Every coordinate is a two-sided true null, so the FDR is exactly the probability that the global BH procedure makes at least one rejection.

### H3

The observation is an exact linear image of the jointly Gaussian vector \(Z_j\), so it is jointly Gaussian. Its covariance is the Gram matrix \(\Sigma_j=U_jU_j^{\mathsf T}\), which is symmetric PSD with diagonal entries one. Every linear combination has the required centered normal law, including zero variance combinations. The discrepancy bound also forces the listed directions to span \(\mathbb R^j\): a unit vector orthogonal to their span would give empirical cap mass zero for every \(s>0\), while the continuous mass tends to one as \(s\downarrow0\). Hence \(\operatorname{rank}(\Sigma_j)=j\), which tends to infinity. The large observation covariance is singular, as allowed.

### H4

The p-values are exactly those specified in the target, and BH uses its largest qualifying rank with no modification. The analysis below concerns its single global crossing over all \(N_j\) coordinates. It neither applies BH separately to local blocks nor sums separate local FDRs.

### NOT

This check fails. In fact,
$$
\operatorname{FDR}_{\rm BH}^{(2)}(q_j;N_j,0,\Sigma_j)\le (1+o(1))q_j,
$$
so its ratio to \(q_j\sqrt{\log(1/q_j)}\) tends to zero. The following argument keeps the finite arrays throughout and controls their difference from the continuous spherical field.

Write \(\mathcal R=\|Z_j\|\) and \(z_t=\overline\Phi^{-1}(t/2)\). Define the continuous cap fraction
$$
G_j(t,r)=\sigma_j\{u:|u_1|\ge z_t/r\},
$$
with value zero when \(r=0\) or \(z_t/r>1\). For fixed \(t\), this is nondecreasing in \(r\), and
$$
\mathbb E\,G_j(t,\mathcal R)=t.
$$
The identity follows by taking an independent uniform direction \(U\): conditional on \(\mathcal R\), the tail probability of \(|U^{\mathsf T}Z_j|\) is \(G_j(t,\mathcal R)\), while unconditionally \(U^{\mathsf T}Z_j\) is standard normal.

We first prove a radius-only crossing inequality. For any \(\alpha\in(0,1)\),
$$
\mathbb P\left\{\text{there exists }t\in(0,\alpha]:G_j(t,\mathcal R)\ge t/\alpha\right\}\le\alpha.
$$
For each fixed \(t<\alpha\), let \(r_t\) be the first radius where \(G_j(t,r)\ge t/\alpha\). Such a radius is finite, and continuity gives equality there. Monotonicity and the expectation identity imply
$$
t=\mathbb E G_j(t,\mathcal R)
\ge \frac t\alpha\,\mathbb P(\mathcal R\ge r_t),
$$
so \(\mathbb P(\mathcal R\ge r_t)\le\alpha\). The union over \(t\) is a union of nested upper-radius events. Its probability is the supremum of their probabilities, because the radius has a continuous distribution. The endpoint \(t=\alpha\) cannot produce a finite-radius crossing, since \(z_\alpha>0\) and \(G_j(\alpha,r)<1\) for every finite \(r\). This proves the inequality without requiring a maximizing threshold.

Return to the finite array. If BH rejects, there is a rank \(k\ge1\) such that, at \(t=q_jk/N_j\), the empirical p-value fraction is at least \(t/q_j\). Split possible witnessing thresholds at \(q_j\eta_j\).

If \(t<q_j\eta_j\), some coordinate has \(p_{ji}\le q_j\eta_j\), so the unit norm of every direction gives
$$
\mathcal R\ge z_{q_j\eta_j}.
$$
For large \(j\), \(z_{q_j\eta_j}>j^{3/2}\). For example, a standard lower Mills bound gives
$$
2\overline\Phi(j^{3/2})\ge c\,j^{-3/2}e^{-j^3/2}
> e^{-j-j^3}=q_j\eta_j
$$
for some fixed \(c>0\) and all sufficiently large \(j\). Since \(\mathcal R^2\) is chi-square with \(j\) degrees of freedom, exponential Markov at parameter \(1/4\) yields
$$
\mathbb P(\mathcal R\ge z_{q_j\eta_j})
\le 2^{j/2}e^{-j^3/4}=o(q_j).
$$
This treats arbitrarily tiny BH ranks without a union bound over the enormous number of directions.

If \(t\ge q_j\eta_j\), the cap discrepancy gives
$$
G_j(t,\mathcal R)\ge\frac t{q_j}-\delta_j
\ge \left(1-\frac1j\right)\frac t{q_j}
=\frac t{\alpha_j},\qquad
\alpha_j=\frac{q_j}{1-1/j}.
$$
Because \(t\le q_j<\alpha_j<1\), the radius-only crossing inequality applies. Combining the two threshold ranges gives
$$
\operatorname{FDR}_{\rm BH}^{(2)}(q_j;N_j,0,\Sigma_j)
\le \frac{q_j}{1-1/j}+o(q_j).
$$
Finally \(\log(1/q_j)=j\), so division by \(q_j\sqrt j\) proves the claimed vanishing normalized FDR. This is an upper bound and does not assert an asymptotic equality with \(q_j\).

## Failure

NOT fails: the exact, growing-rank, high-entropy spherical Gaussian arrays have global all-null BH FDR at most \((1+o(1))q_j\), hence zero on the conjectured square-root-log normalization.
