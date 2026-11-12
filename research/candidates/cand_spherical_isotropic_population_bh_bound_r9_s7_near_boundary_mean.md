---
type: candidate
title: Dimension-four half-null law with mean just above the bounded-mean boundary
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
round: 9
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T02:11:30.353Z'
extension_version: 0.0.4
---

## Object

Let $u=104$, $q=2Q(u)$, $d=4$, and
$$
W=\tfrac12\delta_0+\tfrac12\delta_{u+u^{-1}},\qquad \pi_0=\tfrac12.
$$
Use the exact isotropic product directional population, zero residual variance, and smallest finite BH contact specified in the context pack. This tests a two-atom law just outside the previously excluded support restriction $W([0,u])=1$, without an atom at $2u$ or a larger strong mean.

## Checks

### H1

Pass: $d=4$ is an integer at least four.

### H2

Pass: $W$ is a Borel probability law on $[0,\infty)$ and $W(\{0\})=1/2$.

### H3

Pass: take population measure $W\otimes\sigma_3$. Every conditional direction is uniform and independent of the mean.

### H4

Pass: use $T_{\mu,v}(Z)=\mu+v^\top Z$ with $Z\sim N(0,I_4)$ and no residual noise.

### H5

Pass: $0<q=2Q(104)<1$, and $Q^{-1}(q/2)=104\geq104$.

### H6

Pass: use precisely the smallest finite $x_r\geq u$ with $F_r(x_r)\geq2Q(x_r)/q$; assign FDP zero if no contact exists. For $r>u$, the explicit admissible cutoff constructed below guarantees a finite contact. No contact selection is replaced by an arbitrary branch.

### NOT

Fail: the proposed upper bound holds strictly for this object. In dimension four, the density of $rv_1$ is
$$
f_r(t)=\frac{2}{\pi r}\sqrt{1-(t/r)^2}\,\mathbf 1_{\{|t|<r\}}.
$$
Consequently, for $r>u$,
$$
H_r(u^{-1})\geq\frac12-\frac{2}{\pi r u}
>\frac12-u^{-2}.
$$
Set $a=u+2u^{-1}$ and $\mu=u+u^{-1}$. Then
$$
F_r(a)\geq\frac12 H_r(a-\mu)
=\frac12 H_r(u^{-1})
>\frac14-\frac{1}{2u^2}>\frac15.
$$
For every $h\geq0$, shifting the Gaussian tail integration gives
$$
Q(u+h)\leq e^{-uh-h^2/2}Q(u).
$$
Thus
$$
\frac{2Q(a)}q=\frac{Q(a)}{Q(u)}
\leq e^{-2-2u^{-2}}<\frac15,
$$
so $a$ is admissible and the first contact satisfies $x_r\leq a$. Therefore
$$
F_r(x_r)\geq\frac12H_r(x_r-\mu)
\geq\frac12H_r(u^{-1})>\frac15.
$$
It follows that
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
\leq10\pi_0H_r(u),\qquad r>u.
$$
For $r\leq u$, every permitted cutoff has zero null rejection mass, so the FDP is zero. Finally $\mathbb E H_R(u)=Q(u)$ because $RV_1$ is a standard normal coordinate. Hence
$$
\operatorname{FDR}_{\rm pop}\leq10\pi_0Q(u)=5q\pi_0.
$$
But $M_4=1/\pi$, $\pi<4$, and $\log(312)>5$, so
$$
2+4M_4(1+u^{-2})\log(3u)>7>5.
$$
The candidate FDR is therefore strictly below the target right-hand side, even before its additive $e^{-2u^2}$ term.

## Failure

NOT fails: an admissible cutoff valid on every radius capable of a null rejection gives $\operatorname{FDR}_{\rm pop}\leq5q\pi_0$, below the target coefficient.
