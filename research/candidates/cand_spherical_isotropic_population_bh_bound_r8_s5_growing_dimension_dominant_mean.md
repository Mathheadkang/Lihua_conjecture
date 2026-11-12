---
type: candidate
title: Growing dimension with a dominant strong alternative mean
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
slot: 5
direction: extremal
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:59:53.230Z'
extension_version: 0.0.4
---

## Object

For any integer $n\geq104$, put $u=n$, $q=2Q(n)$, $d=n^4$ and
$$
W=\tfrac12\delta_0+\tfrac12\delta_d.
$$
At both means take independent uniform directions on $\mathbb S^{d-1}$ and zero residual variance. Use exactly the prescribed first-contact population BH rule. Thus $\pi_0=1/2$. Both the dimension and alternative mean diverge as the level tends to zero; the alternative mean dominates the typical radius $\sqrt d$.

## Checks

### H1

The dimension $d=n^4$ is an integer at least four.

### H2

$W$ is a Borel probability law on $[0,\infty)$, with null mass $\pi_0=1/2$.

### H3

The population law is the product $W\otimes\sigma_{d-1}$, so the directions are uniform and independent of the absolute mean at every mean in the support.

### H4

The statistic is exactly $T_{\mu,v}(Z)=\mu+v^\top Z$ with $Z\sim N(0,I_d)$, with no residual noise.

### H5

Since $q=2Q(n)\in(0,1)$, the prescribed normal cutoff is $Q^{-1}(q/2)=n\geq104$.

### H6

For each radius use $\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$ when this set is nonempty and zero FDP otherwise, exactly as stipulated.

### NOT

NOT fails. Set $L=d-2u$. If $r\leq L$, every alternative statistic is at least $d-r\geq2u$, so every alternative is rejected at every cutoff $x\in[u,2u]$. Moreover
$$
\frac{2Q(2u)}q=\frac{Q(2u)}{Q(u)}
\leq e^{-3u^2/2}<\frac12.
$$
Here the tail inequality follows by writing $Q(2u)=\int_u^\infty\phi(t+u)\,dt$ and using $\phi(t+u)\leq e^{-3u^2/2}\phi(t)$ for $t\geq u$. Therefore $F_r(2u)\geq1/2>2Q(2u)/q$ and the first contact obeys $u\leq x_r\leq2u$. All alternatives are rejected there, whence
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2\pi_0H_r(x_r)}{1/2+2\pi_0H_r(x_r)}
\leq4\pi_0H_r(u).
$$
Rotational invariance gives $\mathbb E H_R(u)=Q(u)$: conditionally on $R$, a uniform directional projection has tail $H_R(u)$, while its unconditional distribution is $N(0,1)$. Since the FDP is at most one everywhere,
$$
\operatorname{FDR}_{\rm pop}
\leq4\pi_0Q(u)+\mathbb P(R>L)
=2q\pi_0+\mathbb P(R>L).
$$
For the remainder, $L=d-2u\geq d/2$ and $\mathbb E e^{R^2/4}=2^{d/2}$. Markov's inequality and $d\geq16$ give
$$
\mathbb P(R>L)
\leq\exp\{(d/2)\log2-L^2/4\}
\leq\exp\{d/2-d^2/16\}
\leq e^{-d^2/32}
=e^{-u^8/32}
\leq e^{-2u^2},
$$
where the last inequality uses $u^6\geq64$. Consequently
$$
\operatorname{FDR}_{\rm pop}
\leq2q\pi_0+e^{-2u^2}
<q\pi_0\{2+4M_d(1+u^{-2})\log(3u)\}+e^{-2u^2},
$$
because $M_d>0$. This rules out this simultaneous growing-dimension, strong-mean family without an assumption that means lie below $u$ and without differentiating the first contact.

## Failure

NOT fails: all alternatives are fully rejected up to a deterministic radial cutoff, giving the strict target bound $\operatorname{FDR}_{\rm pop}\leq2q\pi_0+e^{-2u^2}$.
