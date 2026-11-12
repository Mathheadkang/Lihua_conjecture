---
type: candidate
title: Strong Pareto alternatives with infinite first moment
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
slot: 3
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:59:53.230Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$ and
$$
W=\frac12\delta_0+\frac12\nu,
\qquad
\nu(d\mu)=\frac{\sqrt{3u}}{2\mu^{3/2}}
\mathbf 1_{[3u,\infty)}(\mu)\,d\mu.
$$
Use the exact isotropic zero-residual population and prescribed first-contact BH rule. Thus $\pi_0=1/2$. The nonnull mass is entirely at means at least $3u$, and its first moment is infinite. This tests unbounded means with an appreciable strong-signal component rather than a small heavy tail above a weak bulk.

## Checks

### H1

The dimension $d=4$ is an integer at the allowed lower endpoint.

### H2

The law $\nu$ is Borel on $[0,\infty)$ and
$$
\int_{3u}^\infty\frac{\sqrt{3u}}{2\mu^{3/2}}\,d\mu=1.
$$
Consequently $W$ is a Borel probability law, $W(\{0\})=1/2$, and its support is unbounded. Its first moment diverges since the corresponding integrand is proportional to $\mu^{-1/2}$.

### H3

Choose the population measure $W(d\mu)\sigma_3(dv)$. Directions are uniform conditional on every absolute mean and independent of that mean.

### H4

Let $Z\sim N(0,I_4)$ and $T_{\mu,v}=\mu+v^\top Z$, with no additional residual variance. This is exactly the required sampling model.

### H5

The choice $q=2Q(104)$ lies in $(0,1)$ and gives $Q^{-1}(q/2)=104$.

### H6

Use $x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$ when this set is nonempty, and zero FDP otherwise, as required. No alternate contact selection is used.

### NOT

The conclusion does not fail. The following bound excludes the proposed object.

Put $x_0=Q^{-1}(q/4)$ and $b=2u-u^{-1}$. For $a>0$, changing variables in the Gaussian tail gives
$$
Q(u+a)\leq e^{-ua-a^2/2}Q(u).
$$
Taking $a=1/u$ yields $Q(u+u^{-1})<Q(u)/2=q/4$, so
$$
u<x_0<u+u^{-1}.
$$
For every $0<r\leq b$, every nonnull mean obeys
$$
\mu-r\geq3u-b=u+u^{-1}>x_0.
$$
Hence every nonnull direction rejects at $x_0$, so $F_r(x_0)\geq1/2=2Q(x_0)/q$. A first contact therefore exists and satisfies $x_r\leq x_0$. Every nonnull direction still rejects at $x_r$, giving $F_r(x_r)\geq1/2$. Thus
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
\leq2H_r(x_r)\leq2H_r(u)
\qquad(0<r\leq b).
$$
For $r>b$ the FDP is at most one. Rotational invariance and an independent uniform direction give $\mathbb E[H_R(u)]=Q(u)$, while the exact $\chi_4$ tail is
$$
\mathbb P(R>b)=(1+b^2/2)e^{-b^2/2}.
$$
Since $b^2/2=2u^2-2+(2u^2)^{-1}$,
$$
\mathbb P(R>b)<2e^2u^2e^{-2u^2}.
$$
The lower Mills inequality gives
$$
q>\sqrt{2/\pi}\,\frac{u}{u^2+1}e^{-u^2/2}
>\frac{1}{2u}e^{-u^2/2}
\qquad(u=104).
$$
For the last inequality, use $\pi<4$ and $u^2/(u^2+1)>3/4$. Consequently
$$
\frac{\mathbb P(R>b)}q<4e^2u^3e^{-3u^2/2}<1.
$$
The final strict inequality is elementary at $u=104$: $4<e^2$, $104<e^5$, and $3u^2/2=16224$, so its logarithm is less than $19-16224$. It follows that
$$
\operatorname{FDR}_{\rm pop}
\leq2\mathbb E[H_R(u)]+\mathbb P(R>b)
<2q=4q\pi_0.
$$
In dimension four $M_4=1/\pi$. Since $\pi<4$ and $\log312>5$, the proposed coefficient satisfies
$$
2+4M_4(1+u^{-2})\log(3u)>7.
$$
The target right side is therefore strictly greater than $7q\pi_0$, whereas this object's FDR is below $4q\pi_0$.

## Failure

NOT fails first: the appreciable strong Pareto component forces a bounded first contact below radius $2u-u^{-1}$, and its exact radial-tail bound gives $\operatorname{FDR}_{\rm pop}<4q\pi_0$.
