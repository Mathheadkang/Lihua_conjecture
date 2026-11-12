---
type: candidate
title: Four-dimensional one-percent alternative just above the threshold
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
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T02:11:30.353Z'
extension_version: 0.0.4
---

## Object

Take $d=4$, $u=104$, $q=2Q(u)$, and
$$
W=\frac{99}{100}\delta_0+\frac1{100}\delta_{u+u^{-1}}.
$$
Use the product population $W(d\mu)\sigma_3(dv)$, zero residual variance, and exactly the first finite contact convention in the target. Thus $\pi_0=99/100$ and the sole alternative mean is slightly greater than $u$. Its mass is only one percent, so this is distinct from the earlier half-mass strong-mean atom and from the support-restricted family $W([0,u])=1$.

## Checks

### H1

Pass. The integer dimension is $d=4\geq4$.

### H2

Pass. The displayed $W$ is a Borel probability measure supported on $[0,\infty)$, with null mass $\pi_0=99/100$.

### H3

Pass. The population is precisely $W\otimes\sigma_3$, so directions are uniform and independent of the absolute mean at each of its two atoms.

### H4

Pass. Set $Z\sim N(0,I_4)$ and $T_{\mu,v}=\mu+v^\top Z$, with no residual observation noise.

### H5

Pass. $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

Pass. At every $r>0$, use $x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}$ when that set is nonempty, and FDP zero otherwise, as required.

### NOT

Fail. A localized cap bound gives a strict upper bound below the proposed right side.

For $d=4$ the first coordinate of a uniform direction has density
$$
f(s)=\frac2\pi\sqrt{1-s^2},\qquad -1<s<1.
$$
Write $\mu=u+u^{-1}$ and take $a=u+6u^{-1}$. For every $r\geq u$,
$$
H_r(a-\mu)\geq\frac12-\frac2\pi\frac{5}{u^2}>\frac{49}{100}.
$$
Hence $F_r(a)>49/10000$. The elementary normal-tail translation inequality
$$
\frac{Q(u+h)}{Q(u)}\leq e^{-uh-h^2/2}\qquad(h\geq0)
$$
gives $2Q(a)/q\leq e^{-6}<1/400<49/10000$. Thus a finite first contact exists and $u\leq x_r\leq a$ for every $r\geq u$. Its rejection mass obeys
$$
F_r(x_r)\geq\frac1{100}H_r(x_r-\mu)\geq\frac1{100}H_r(a-\mu)>\frac{49}{10000}.
$$

On the radial interval $u<r\leq101u/100$, set $z=u/r\geq100/101$. Since $\sqrt{1-s^2}$ decreases on $[z,1]$,
$$
2H_r(u)\leq\frac4\pi(1-z)\sqrt{1-z^2}
\leq\frac{4\sqrt{201}}{\pi\,10201}
<\frac1{500}.
$$
The last comparison follows from $\sqrt{201}<15$, $\pi>3$, and $30000<30603$. Therefore
$$
F_r(x_r)\leq\frac1{100}+\frac{99}{100}\,2H_r(u)<\frac3{250}.
$$
Let $b$ satisfy $2Q(b)/q=3/250$. The contact identity and monotonicity of $Q$ imply $x_r\geq b$. Consequently, using $\mathbb E H_R(b)=Q(b)$,
$$
\mathbb E\left[\operatorname{FDP}_{\rm pop}(R)\mathbf1_{\{u<R\leq101u/100\}}\right]
\leq\frac{2\pi_0}{49/10000}\mathbb E H_R(b)
=\frac{120}{49}q\pi_0.
$$
For $R\leq u$, the null rejection mass vanishes because $x_R\geq u\geq R$; the event $R=u$ has probability zero.

It remains to bound the radial tail. The exact $\chi_4$ tail and the lower Mills inequality $Q(u)\geq\phi(u)u/(u^2+1)$ yield, with $c=101/100$,
$$
\frac{\mathbb P(R>cu)}q
\leq\frac{\sqrt{2\pi}(u^2+1)}{2u}
\left(1+\frac{c^2u^2}{2}\right)
\exp\left\{-\frac{201u^2}{20000}\right\}
<3u^3 e^{-201u^2/20000}.
$$
At $u=104$, this is less than $4\cdot10^6e^{-100}<0.00288<\pi_0$: the middle bound follows from $e^{100}>100^6/6!$. Since FDP is at most one, the tail contribution is less than $q\pi_0$. Therefore
$$
\operatorname{FDR}_{\rm pop}<\left(\frac{120}{49}+1\right)q\pi_0
=\frac{169}{49}q\pi_0<7q\pi_0.
$$
For $d=4$, $M_4=1/\pi$. Since $\pi<4$ and $\log312>5$, the target coefficient satisfies
$$
2+4M_4(1+u^{-2})\log(3u)>7.
$$
Thus this candidate strictly satisfies the proposed FDR upper bound, even before its positive additive term $e^{-2u^2}$.

## Failure

NOT fails first: the one-percent mean atom just above $u$ admits a localized cap envelope and radial-tail estimate giving FDR less than $(169/49)q\pi_0$, whereas the target coefficient exceeds $7$.
