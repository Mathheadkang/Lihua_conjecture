---
type: candidate
title: Dimension 5 strong two-mean population with null mass 1/4
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
round: 2
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-04T23:55:12.818Z'
extension_version: 0.0.4
---

## Object

Take $u=104$, $q=2Q(104)$, $d=5$, and
$$
W=1/4\delta_0+3/8\delta_{416}+3/8\delta_{832}.
$$
Use zero residual variance, $Z\sim N(0,I_5)$, and the product directional law $W\otimes\sigma_{5-1}$. Thus $\pi_0=1/4$. Use exactly the specified smallest finite admissible Gaussian-statistic cutoff, with zero FDP if there is no finite contact.

This tests a new odd dimension and two distinct strong means with an interior null mass; it is not a repeat of the smallest-dimension, vanishing-mean, boundary-null-mass or unbounded-support diagnostics mentioned on the board.

## Checks

### H1

The dimension $d=5$ is an integer at least four.

### H2

The statistics are exactly $T_{\mu,v}(Z)=\mu+v^\top Z$, with no residual observation noise.

### H3

The displayed $W$ is a Borel probability measure on $[0,\infty)$: all weights are positive and $1/4+2(3/8)=1$. Its atom at zero has mass $\pi_0=1/4$.

### H4

At every absolute mean the directional kernel is the same uniform probability measure $\sigma_{5-1}$ and is independent of the mean, by the specified product law.

### H5

The chosen level satisfies $0<q<1$, and $Q^{-1}(q/2)=104\geq104$ exactly. No floating-point representation of this extremely small level is needed.

### H6

Use the specified largest population BH threshold and population FDP, including the zero convention when the contact set is empty. The following argument bounds its first contact directly; it does not substitute a different admissible contact.

### NOT

The proposed upper bound is not violated. Here is a direct analytic bound, without numerical integration.

For $0<r\leq2u$ and $u\leq x\leq2u$, both positive means obey $\mu-r\geq2u\geq x$. Therefore every alternative rejects at these cutoffs (endpoint equality affects a directional null set), so $F_r(x)\geq1-\pi_0$. The normal Mills bounds give
$$
\frac{Q(2u)}{Q(u)}
\leq\frac{u^2+1}{2u^2}e^{-3u^2/2}<\frac14\leq1-\pi_0.
$$
Thus $2u$ is admissible and the smallest contact $x_r$ lies in $[u,2u]$. At this first contact,
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
\leq\frac{2\pi_0H_r(u)}{1-\pi_0}.
$$
For $r>2u$ use the elementary bound $\operatorname{FDP}_{\rm pop}(r)\leq1$. Since a fixed uniform direction projected against the standard Gaussian vector is $N(0,1)$, $\mathbb E H_R(u)=Q(u)$. Consequently
$$
\operatorname{FDR}_{\rm pop}
\leq\frac{q\pi_0}{1-\pi_0}+\mathbb P(R>2u).
$$
Using the moment generating function of $R^2\sim\chi^2_5$ at $1/4$,
$$
\mathbb P(R>2u)\leq2^{5/2}e^{-u^2}.
$$
Together with $q\geq2\phi(u)u/(u^2+1)$, this gives
$$
\log\frac{\mathbb P(R>2u)}{q\pi_0}
\leq\frac 52\log2-u^2-
\log\!\left(\frac{2\phi(u)u}{u^2+1}\right)-\log\pi_0
<-5390<0.
$$
(The explicit right side before rounding is approximately -5400.01056.) It follows that
$$
\operatorname{FDR}_{\rm pop}<q\pi_0\left(\frac1{1-\pi_0}+1\right)=7/3\,q\pi_0.
$$
For this dimension $M_5=1/(2\sqrt3)>1/4$. Since $\log(312)>5$, the proposed coefficient $2+4M_5(1+104^{-2})\log(312)$ exceeds $7$ (numerically about 8.6320619876), while $7/3\leq5$. Hence the proposed bound holds strictly, even before adding its positive $e^{-2u^2}$ term.

## Failure

NOT fails first: a direct first-contact bound gives $\operatorname{FDR}_{\rm pop}<7/3\,q\pi_0$, strictly below the claimed right side.
