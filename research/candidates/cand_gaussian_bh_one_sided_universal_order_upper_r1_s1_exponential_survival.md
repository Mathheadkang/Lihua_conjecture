---
type: candidate
title: Exponentially varying rare-alternative survival with vanishing null loading
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T19:59:50.622Z'
extension_version: 0.0.4
---

## Object

For every integer j>=2 let r=1/j, q_j=exp(-j^2), m_j=ceil(exp(j^2)), N_j=ceil(exp(3j^2)), and n_j=N_j-m_j. Take independent standard normals Z, epsilon_1,...,epsilon_n_j. For the n_j true nulls put T_i=rZ+sqrt(1-r^2)epsilon_i. For l=1,...,m_j set
$$
a_{j,l}=\sqrt{1+4r^2\log\frac{m_j}{l-1/2}},\qquad
\mu_{j,l}=\frac{1+r}{r}a_{j,l},\qquad
T_{n_j+l}=\mu_{j,l}-Z.
$$
Run the original one-sided BH procedure at q_j, including all alternative multiplicities and the largest qualifying rank. This is an exact finite Gaussian sequence, without a population approximation or an interchange of limits.

The secondary profile is its actual discrete survival, not a single-atom tail replacement. For a>=1 it is exactly
$$
W_j(a)=\frac1{N_j}\min\left\{m_j,\left\lfloor m_j\exp\left(-\frac{a^2-1}{4r^2}\right)+\frac12\right\rfloor\right\}.
$$
For a<1 it equals m_j/N_j. Conditional on Z=z, its rejection count at score cutoff c is exactly N_j W_j(r(c+z)/(1+r)). The alternative fraction is asymptotic to exp(-2/r^2). Relative to a Gaussian survival S(a/r), this has an exponentially r-dependent profile, so it is outside the bounded fixed-g_q profile regime of idea_97f590b891a2.

## Checks

### H1

The levels q_j are in (0,1) and tend to zero. A refutation along this sequence would require FDR_j/[q_j sqrt(log(1/q_j))] to be unbounded; exceeding a proposed fixed constant at one j would not suffice.

### H2

N_j is a finite positive integer, and 0<m_j<N_j for every j>=2.

### H3

Every null mean is zero. Every alternative mean mu_j,l is finite and strictly positive. Thus the original one-sided true-null set is exactly {1,...,n_j}; no coordinate is relabeled.

### H4

The displayed independent-normal representation is jointly Gaussian, with unit variances. Its covariance is a Gram matrix: null loading vectors are r e_0+sqrt(1-r^2)e_i, and all alternative loading vectors are -e_0. Hence it is positive semidefinite with unit diagonal; alternative ties and singularity are allowed by the target.

### H5

p_i=S(T_i), and the rejection rank is the maximum of all k with p_(k)<=q_j k/N_j. No rank proxy, first-crossing approximation, null deletion, or covariance modification is made.

### NOT

Fail. Write s=sqrt(1-r^2) and b=1/s. Given Z=z, the null coordinates are independent N(rz,s^2), and the alternatives are constants. Thus all coordinates are conditionally independent, including the degenerate alternatives, as required by the approved conditional compound-calibration lemma. The null conditional density f_z satisfies, for every real x,
$$
\frac{f_z(x)}{\phi(x)}
=b\exp\left(\frac{z^2}{2}-\frac{r^2}{2s^2}(x-z/r)^2\right)
\le b e^{z^2/2}.
$$
Integration over every upper tail gives M_q(z)<= (n_j/N_j)b e^{z^2/2}, hence K_q(z)<=b e^{z^2/2}. Apply the approved calibration lemma to the same actual BH rank to obtain
$$
\operatorname{FDR}_j\le E\min\{1,A_j e^{Z^2/2}\},\qquad A_j=2q_jb.
$$
Since r<=1/2, b<=2/sqrt(3). Put x_j=sqrt(2 log(1/A_j)); then j<=x_j<=sqrt(2)j for j>=2. Exact integration and the upper Mills bound yield
$$
E\min\{1,A_j e^{Z^2/2}\}
=\sqrt{2/\pi}\,A_jx_j+2S(x_j)
\le\sqrt{2/\pi}\,A_j(x_j+1/x_j)
\le 4q_jj.
$$
Therefore FDR_j/[q_j sqrt(log(1/q_j))]<=4 for all j>=2. The bound makes no approximation to W_j and permits every alternative mean and multiplicity in this explicit sequence. More generally it applies to arbitrary deterministic alternative functions of this single Z, with the stated conditionally independent null residuals and r<=1/2; it does not address unrestricted Gaussian covariance.

## Failure

NOT fails: the exact conditional-null density envelope bounds the actual FDR by 4q_j sqrt(log(1/q_j)), even for this exponentially varying finite rare-alternative survival profile.
