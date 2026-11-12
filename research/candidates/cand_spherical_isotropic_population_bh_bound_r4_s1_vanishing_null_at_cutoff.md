---
type: candidate
title: Vanishing null mass with alternative mean at the Gaussian cutoff
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
round: 4
slot: 1
direction: boundary_degenerate
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:27:47.684Z'
extension_version: 0.0.4
---

## Object

For any real $u\geq104$, put $q=2Q(u)$, $d=7$, $\varepsilon=e^{-u^2}$, and
$$
W=\varepsilon\delta_0+(1-\varepsilon)\delta_u.
$$
Take $Z\sim N(0,I_7)$ and population measure $W\otimes\sigma_6$, with statistic $T_{\mu,v}=\mu+v^\top Z$ and zero residual variance. Use exactly the prescribed smallest finite admissible cutoff, with FDP zero if no finite cutoff exists. This tests a null proportion tending to zero while the alternative atom lies precisely at the initial Gaussian cutoff.

## Checks

### H1

The displayed statistic has the required isotropic spherical population form, with $Z\sim N(0,I_7)$ and no residual noise.

### H2

The dimension $d=7$ is an integer at least four.

### H3

The measure $W$ is a Borel probability law on $[0,\infty)$, since $0<\varepsilon<1$ and $u>0$. Its null mass is exactly $\pi_0=\varepsilon$.

### H4

The product population measure makes directions uniform on $\mathbb S^6$ and independent of the absolute mean, at both supported means.

### H5

The prescribed population BH rule is used. To bound its actual first contact, let $x_4=Q^{-1}(Q(u)/4)$. Then $u<x_4<u+1$: indeed, shifting the Gaussian tail integral gives $Q(u+1)\leq e^{-u-1/2}Q(u)<Q(u)/4$.

In dimension seven the first spherical coordinate has density
$$
f_7(t)=\frac{15}{16}(1-t^2)^2\mathbf 1_{[-1,1]}(t),
$$
so for $r\geq u$,
$$
H_r(x_4-u)\geq\frac12-\frac{15(x_4-u)}{16r}
>\frac12-\frac{15}{16u}>\frac38.
$$
Also $\varepsilon<1/3$. Consequently
$$
F_r(x_4)\geq(1-\varepsilon)H_r(x_4-u)>
\frac23\frac38=\frac14=\frac{2Q(x_4)}q.
$$
Thus a finite contact exists and the actual smallest contact satisfies $x_r\leq x_4$ whenever $r\geq u$. For $r<u$, either there is no contact or its null rejection mass is zero, since every admissible cutoff is at least $u>r$.

### H6

Since $u\geq104$, the level $q=2Q(u)$ lies in $(0,1)$ and $Q^{-1}(q/2)=u\geq104$.

### NOT

For $r\geq u$, monotonicity of $H_r$ and $Q$, and the first-contact bound in H5, give
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
=q\varepsilon\frac{H_r(x_r)}{Q(x_r)}
\leq4q\varepsilon\frac{H_r(u)}{Q(u)}.
$$
For $r<u$ the FDP is zero, so the same inequality remains valid. Rotational invariance and the standard normal marginal imply $\mathbb E H_R(u)=Q(u)$. Therefore
$$
\operatorname{FDR}_{\mathrm{pop}}\leq4q\pi_0.
$$
Here
$$
M_7=\frac{3}{5\sqrt5}>\frac15.
$$
Using $3u\geq312>e^5$, the proposed coefficient satisfies
$$
2+4M_7(1+u^{-2})\log(3u)>2+\frac45\,5=6>4.
$$
The proposed right side is thus strictly larger than this FDR upper bound for every $u\geq104$. The vanishing null-mass boundary in this family does not violate the conclusion.

## Failure

NOT fails first: the alternative atom at the initial cutoff supplies a uniform admissible cutoff and yields $\operatorname{FDR}_{\mathrm{pop}}\leq4q\pi_0$, below the proposed bound for all $u\geq104$.
