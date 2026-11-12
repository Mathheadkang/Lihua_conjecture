---
type: candidate
title: Dimension-four half-null population with a strong atom at twice the cutoff
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
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:59:53.230Z'
extension_version: 0.0.4
---

## Object

Take $d=4$, $u=104$, $q=2Q(u)$ and
$$
W=\tfrac12\delta_0+\tfrac12\delta_{2u}.
$$
Thus $\pi_0=1/2$. Directions are uniform on $\mathbb S^3$ independently of the absolute mean, and $T_{\mu,v}(Z)=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and no residual noise. Use the specified smallest finite spherical BH contact.

## Checks

### H1

Pass: $d=4$ is an integer at least four.

### H2

Pass: $W$ is a Borel probability law on $[0,\infty)$ and $W(\{0\})=1/2$.

### H3

Pass: the population measure is exactly $W\otimes\sigma_3$, with the same uniform directional kernel at both absolute means.

### H4

Pass: the sole sampling randomness is $Z\sim N(0,I_4)$; residual variance is zero.

### H5

Pass: $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

Pass: the threshold is the smallest finite $x\geq u$ satisfying $F_r(x)\geq2Q(x)/q$, with the FDP convention in the target definition. The calculation below supplies a finite contact for every $r>0$.

### NOT

Fail. Define $x_0$ by $Q(x_0)=Q(u)/4=q/8$. Then $u<x_0<2u$: indeed,
$$
Q(2u)=\int_u^\infty\phi(t+u)\,dt
\leq e^{-3u^2/2}Q(u)<Q(u)/4.
$$
For every $r>0$, symmetry gives $H_r(x_0-2u)\geq1/2$ because $x_0-2u<0$. Consequently
$$
F_r(x_0)\geq\tfrac12H_r(x_0-2u)\geq\tfrac14
=2Q(x_0)/q.
$$
Continuity therefore provides the specified first contact with $u\leq x_r\leq x_0$. Monotonicity of $H_r$ and $Q$ yields
$$
\operatorname{FDP}_{\rm pop}(r)
=q\pi_0\frac{H_r(x_r)}{Q(x_r)}
\leq q\pi_0\frac{H_r(u)}{Q(x_0)}.
$$
For an independent uniform direction $V$, $V^\top Z\sim N(0,1)$, so $\mathbb E[H_R(u)]=Q(u)$. Averaging gives the exact exclusion bound
$$
\operatorname{FDR}_{\rm pop}\leq
q\pi_0\frac{Q(u)}{Q(x_0)}=4q\pi_0.
$$
Here $M_4=1/\pi$. Since $\pi<4$ and $\log312>5$, the proposed multiplier satisfies
$$
2+4M_4(1+u^{-2})\log(3u)>7>4.
$$
The proposed right side is therefore strictly larger than this population's FDR. This test has a positive mass at a mean above $u$; its exclusion uses a uniform finite-contact upper cutoff, rather than requiring monotonicity of $F_r(x)$ in radius.

## Failure

NOT fails first: the strong atom forces every first contact into $[u,x_0]$, and Gaussian marginal averaging bounds the FDR by $4q\pi_0$, below the proposed bound.
