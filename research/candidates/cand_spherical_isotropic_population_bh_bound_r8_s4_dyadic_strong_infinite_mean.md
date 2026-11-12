---
type: candidate
title: Dyadic strong-mean infinite-mean mixture
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
round: 8
slot: 4
direction: known_counterexamples
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:59:53.230Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$ and
$$
W=\frac12\delta_0+\frac12\sum_{k=0}^{\infty}2^{-(k+1)}\delta_{4u2^k}.
$$
Use the product directional law $W\otimes\sigma_3$, zero residual variance, and the specified smallest-finite-contact population BH rule. Thus $\pi_0=1/2$. The positive means form a lacunary unbounded law with appreciable total mass $1/2$ above $u$, and its first moment is infinite: each summand contributes $u$ to the first moment. This tests strong discrete branches rather than an unbounded tail attached to a weak-mean bulk.

## Checks

### H1

Pass: $d=4$ is an integer at least four.

### H2

Pass: all support points lie in $[0,\infty)$ and the positive weights sum to $1/2$, so $W$ is a Borel probability measure with $W(\{0\})=1/2$. Its unbounded support and infinite mean are allowed.

### H3

Pass: the directional law is explicitly the same uniform measure $\sigma_3$ at each absolute mean, independent of that mean.

### H4

Pass: take $T_{\mu,v}=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and no extra noise.

### H5

Pass: $q=2Q(104)$ lies in $(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

Pass: use exactly $x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$ when this set is nonempty, and FDP zero otherwise. Continuity supplies the stipulated contact equality.

### NOT

Fail. In fact the FDR is less than $3q\pi_0$.

Put $a=u+u^{-1}<2u$. Shifting the Gaussian tail integral gives
$$
\frac{Q(a)}{Q(u)}<e^{-1-1/(2u^2)}<\frac12.
$$
For every $0<r\leq2u$, $u\leq x\leq a$, and positive support point $\mu\geq4u$, one has $\mu-x>r$. Hence every alternative is rejected and
$$
F_r(x)=\frac12+H_r(x).
$$
In particular $F_r(a)\geq1/2>2Q(a)/q$, so a finite first contact exists and satisfies $u\leq x_r\leq a$. Consequently
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{H_r(x_r)}{1/2+H_r(x_r)}
\leq2H_r(u),\qquad 0<r\leq2u.
$$
If an independent uniform direction $V$ is sampled, $RV_1\sim N(0,1)$, so $\mathbb E H_R(u)=Q(u)$. The contribution of $R\leq2u$ is therefore at most $2Q(u)=q=2q\pi_0$.

On $R>2u$ use FDP at most one. The exact $\chi_4$ tail is
$$
\mathbb P(R>2u)=e^{-2u^2}(1+2u^2).
$$
The lower Mills inequality, $\sqrt{2\pi}<3$, and $u\geq104$ imply
$$
\frac{\mathbb P(R>2u)}{Q(u)}
<\frac{3(u^2+1)(1+2u^2)}{u}e^{-3u^2/2}
\leq18u^3e^{-3u^2/2}
<\frac{32}{u^3}<1.
$$
For the penultimate inequality use $e^{3u^2/2}>(3u^2/2)^3/6=9u^6/16$. Thus this tail contributes less than $Q(u)=q\pi_0$, proving the asserted $3q\pi_0$ bound.

Finally $M_4=1/\pi$, $\pi<4$, and $\log312>5$, so the proposed coefficient is
$$
2+\frac4\pi(1+104^{-2})\log312>7>3.
$$
The proposed right side strictly exceeds this candidate's FDR.

## Failure

NOT fails first: although half the law lies on unbounded strong-mean atoms and the mean is infinite, the alternatives are saturated throughout the relevant low-radius contacts, giving FDR less than $3q\pi_0$.
