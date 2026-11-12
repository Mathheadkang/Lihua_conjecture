---
type: candidate
title: Ultrarare nulls with weak alternatives in growing dimension
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
round: 5
slot: 4
direction: known_counterexamples
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:53:23.256Z'
extension_version: 0.0.4
---

## Object

Set $u=104$, $d=u^4$, $q=2Q(u)$, and $p=e^{-3u^2}$. Let
$$
W=p\delta_0+(1-p)\delta_{1/u}.
$$
Use $Z\sim N(0,I_d)$ and the product population $W(d\mu)\sigma_{d-1}(dv)$ with statistics $T_{\mu,v}=\mu+v^\top Z$, no residual noise, and the smallest finite admissible Gaussian-statistic cutoff specified in the target. This probes rare true nulls and weak alternatives in a growing-dimension regime; the failure calculation below does not use a finite-dimensional restriction from the previous search board.

## Checks

### H1

$d=104^4$ is an integer at least four.

### H2

The statistics are exactly $T_{\mu,v}=\mu+v^\top Z$; their residual variance is zero.

### H3

Since $0<p<1$, $W$ is a Borel probability law on $[0,\infty)$ and $W(\{0\})=p$.

### H4

The directional kernel is exactly $\sigma_{d-1}$ at both absolute means, independent of the mean.

### H5

$q=2Q(104)\in(0,1)$, so $Q^{-1}(q/2)=104\geq104$.

### H6

For $r>0$, use
$$
F_r(x)=2pH_r(x)+(1-p)\{H_r(x-1/u)+H_r(x+1/u)\},
\qquad x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}.
$$
When this set is empty the FDP is zero; otherwise use the target's contact identity and FDP formula. Thus the convention agrees exactly with the target.

### NOT

The requested violation fails by an elementary bound valid for every nonnegative mean law in every allowed dimension. For $r>0$, the density of $rv_1$ is
$$
f_r(t)=\frac{\Gamma(d/2)}{r\sqrt\pi\,\Gamma((d-1)/2)}
\left(1-\frac{t^2}{r^2}\right)^{(d-3)/2}\mathbf 1_{\{|t|<r\}}.
$$
It is symmetric and nonincreasing as a function of $|t|$, with a continuous extension by zero at the support endpoints. For $x\geq0$ and $\mu\geq0$, put $G(\mu)=H_r(x-\mu)+H_r(x+\mu)$. Then
$$
G'(\mu)=f_r(x-\mu)-f_r(x+\mu)\geq0,
$$
because $|x-\mu|\leq x+\mu$. Hence $G(\mu)\geq G(0)=2H_r(x)$, and integrating against any allowed $W$ gives $F_r(x)\geq2H_r(x)$. At each finite contact,
$$
\operatorname{FDP}_{\rm pop}(r)=\frac{2pH_r(x_r)}{F_r(x_r)}\leq p.
$$
The same bound holds with no contact and at $r=0$. Therefore
$$
\operatorname{FDR}_{\rm pop}\leq p=e^{-3u^2}<e^{-2u^2}
\leq q p\{2+4M_d(1+u^{-2})\log(3u)\}+e^{-2u^2}.
$$
In particular, no law with $\pi_0\leq e^{-2u^2}$ can violate the proposed bound, regardless of dimension or alternative distribution.

## Failure

NOT fails first: symmetric unimodality gives $\operatorname{FDP}_{\rm pop}\leq\pi_0$, and this object's null mass is smaller than the additive allowance $e^{-2u^2}$.
