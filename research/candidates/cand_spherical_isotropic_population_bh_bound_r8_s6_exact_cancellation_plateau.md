---
type: candidate
title: Exact null-alternative cancellation at a radial contact plateau
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
slot: 6
direction: boundary_degenerate
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:59:53.230Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, and
$$
a=Q^{-1}(q/3)>u,\qquad W=\tfrac13\delta_0+\tfrac23\delta_{2a}.
$$
Use the product directional law $W\otimes\sigma_3$, zero residual variance, and exactly the smallest finite contact rule and FDP in the target. Thus $\pi_0=1/3$. The mixing weight is the cancellation endpoint at which the null cap and the alternative cap deficit cancel at cutoff $a$.

## Checks

### H1

The dimension is the integer $d=4\geq4$.

### H2

The law $W$ is a Borel probability law on $[0,\infty)$: its masses are $1/3$ and $2/3$, and $a$ is finite and positive because $0<q/3<1/2$. Its mass at zero is exactly $\pi_0=1/3$.

### H3

At each absolute mean the directions have law $\sigma_3$ independently of that mean, by the specified product law.

### H4

The statistics are $T_{\mu,v}=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and no residual noise.

### H5

Since $q=2Q(104)$, one has $q\in(0,1)$ and $Q^{-1}(q/2)=104$, the allowed lower endpoint. Also $Q(a)=q/3<(q/2)=Q(u)$, so $a>u$.

### H6

Use the target's smallest finite cutoff, with no substitution of a different contact. Symmetry and continuity of the spherical coordinate law give $H_r(-a)=1-H_r(a)$ for every $r>0$. Therefore
$$
\begin{aligned}
F_r(a)
&=\tfrac23H_r(a)+\tfrac23\{H_r(-a)+H_r(3a)\}\\
&=\tfrac23+\tfrac23H_r(3a)
\geq\tfrac23=\frac{2Q(a)}q.
\end{aligned}
$$
Consequently a finite contact exists for every $r>0$, and its smallest cutoff obeys $u\leq x_r\leq a$. For $0<r\leq3a$, $H_r(3a)=0$ and hence $F_r(a)=2/3$ exactly: $a$ is a common equality contact across that interval. It need not be the smallest contact; the bound above uses only the actual smallest cutoff.

### NOT

Because $x_r\leq a$, one has $x_r-2a\leq-a<0$ and therefore $H_r(x_r-2a)\geq1/2$. Thus
$$
F_r(x_r)\geq\tfrac23H_r(x_r-2a)\geq\tfrac13.
$$
Using the contact identity for the actual cutoff and monotonicity of the cap in its argument,
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
\leq6\pi_0H_r(u).
$$
For an independent uniform direction $V$, $V^\top Z\sim N(0,1)$, and conditioning on $R$ gives $\mathbb E H_R(u)=Q(u)$. Hence
$$
\operatorname{FDR}_{\rm pop}\leq6\pi_0Q(u)=3q\pi_0.
$$
For $d=4$, direct substitution yields $M_4=1/\pi$. Since $\log312>1$ and $4/\pi>1$, the proposed coefficient satisfies
$$
2+4M_4(1+104^{-2})\log312>3.
$$
The derived upper bound is therefore strictly smaller than the target right side, even before its positive $e^{-2u^2}$ term. NOT fails.

## Failure

NOT fails: the exact cancellation endpoint has $x_r\leq a$ and rejection mass at least $1/3$, forcing $\operatorname{FDR}_{\rm pop}\leq3q\pi_0$ below the proposed bound.
