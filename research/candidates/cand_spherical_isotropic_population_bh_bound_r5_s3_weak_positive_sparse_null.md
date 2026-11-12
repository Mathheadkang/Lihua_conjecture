---
type: candidate
title: Sparse null mass with a unit positive mean at the extreme Gaussian level
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
slot: 3
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:53:23.256Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(104)$, $p=1/1024$, and
$$
W=p\delta_0+(1-p)\delta_1.
$$
At each mean use the same independent uniform direction on $\mathbb S^3$, with $Z\sim N(0,I_4)$ and $T_{\mu,v}=\mu+v^\top Z$. Use the prescribed smallest finite admissible cutoff, with FDP zero when none exists. The positive mean is much smaller than $u/2$ but exceeds the board's weak-support boundary $1/u$; the sparse null mass also lies below the board's unrestricted-law envelope range.

## Checks

### H1

There is zero residual variance: $T_{\mu,v}=\mu+v^\top Z$ contains no additional observation noise.

### H2

The dimension $d=4$ is an integer satisfying $d\geq4$.

### H3

$W$ is a Borel probability measure on $[0,\infty)$, and its null mass is $\pi_0=W(\{0\})=p$.

### H4

The population law is exactly $W\otimes\sigma_3$. The directional kernel equals $\sigma_3$ at both absolute means, independently of the mean.

### H5

Use $\mathcal C_r=\{x\geq u:F_r(x)\geq2Q(x)/q\}$, $x_r=\min\mathcal C_r$ when nonempty, and the specified contact FDP. The calculation below bounds this actual smallest contact without selecting a different branch.

### H6

Since $q=2Q(104)$, one has $q\in(0,1)$ and $Q^{-1}(q/2)=104\geq104$.

### NOT

This check fails by a strict analytic upper bound. Let $b>u$ be determined by
$$
Q(b)=Q(u)/2048.
$$
The lower Mills inequality $\varphi(t)/Q(t)>t$ gives
$$
0<b-u<\frac{\log2048}{u}<\frac8{104}=\frac1{13},
$$
where $\log2<7/10$ suffices for the second inequality. Put $a=(1-(b-u))/104$. Then
$$
\frac1{113}<\frac3{338}<a<\frac1{104}.
$$
For $d=4$ the coordinate density on $[-1,1]$ is $(2/\pi)\sqrt{1-v^2}$. Consequently
$$
H_u(b-1)=\frac2\pi\int_0^a\sqrt{2s-s^2}\,ds
\geq\frac4{3\pi}\sqrt{2-a}\,a^{3/2}
>\frac{49}{99440}.
$$
The final rational estimate follows from $\pi<22/7$, $\sqrt{2-a}>7/5$, $a>1/113$, and $\sqrt{113}<32/3$. Since $b-1>0$, the spherical cap is nondecreasing in its radius, so for every $r\geq u$,
$$
F_r(b)\geq\frac{1023}{1024}H_r(b-1)
>\frac{1023}{1024}\frac{49}{99440}
>\frac1{2048}=\frac{2Q(b)}q.
$$
The last inequality is $100254>99440$ after multiplication by $2048$. Thus $b$ is admissible for every $r\geq u$, and the actual cutoff satisfies $u\leq x_r\leq b$ there. For $r<u$ its null FDP is zero.

For any fixed $r$ and $x\in[u,b]$, monotonicity of $H_r$ yields the deterministic inequality
$$
\frac{H_r(x)}{Q(x)}
=\frac{H_r(x)}{Q(u)}+H_r(x)\int_u^x\frac{\varphi(t)}{Q(t)^2}\,dt
\leq\frac{H_r(u)}{Q(u)}+\int_u^b\frac{H_r(t)\varphi(t)}{Q(t)^2}\,dt.
$$
Average this common upper bound, using Tonelli and the Gaussian marginal identity $\mathbb E H_R(t)=Q(t)$. The contact formula therefore gives
$$
\operatorname{FDR}_{\mathrm{pop}}
\leq qp\left[1+\int_u^b\frac{\varphi(t)}{Q(t)}\,dt\right]
=qp(1+\log2048)
<\frac{87}{10}qp<9qp.
$$
At $d=4$, $M_4=1/\pi$. The proposed multiplicative coefficient is strictly larger than nine, since
$$
2+\frac4\pi(1+104^{-2})\log312
>2+\frac{22}{\pi}>9;
$$
here $\log312>11/2$ and $\pi<22/7$. Hence this object's FDR lies strictly below the proposed right-hand side, even before its positive additive term $e^{-2u^2}$ is included.

## Failure

NOT fails first: a uniform admissible cutoff and its logarithmic interval envelope give $\operatorname{FDR}_{\mathrm{pop}}<(87/10)q\pi_0$, below the proposed coefficient, despite sparse null mass and a unit positive mean.
