---
type: candidate
title: Near-null bulk with a rare remote alternative atom
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
round: 10
slot: 4
direction: known_counterexamples
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T07:46:48.544Z'
extension_version: 0.0.4
---

## Object

This bounded test combines a nearly null bulk and a rare remote signal, motivated by competing first-contact branches in least-favorable multiple-testing configurations. Set
$$
d=4,\qquad u=104,\qquad q=2Q(u),\qquad
\eta=u^{-1},\qquad \varepsilon=e^{-16},
$$
and
$$
W=\tfrac12\delta_0+(\tfrac12-\varepsilon)\delta_\eta
  +\varepsilon\delta_{2u}.
$$
At every mean use uniform independent directions and zero residual variance. Use the specified smallest finite population BH contact, including the no-contact convention. The null mass is $\pi_0=1/2$.

The high-mean mass is only $e^{-16}$, so this object has neither the board's half-mass premise above $u$ nor its tiny-total-contamination premise: $W([u,\infty))=e^{-16}$, while $1-\pi_0=1/2$.

## Checks

### H1

Pass: $d=4$ is an integer at least four.

### H2

Pass: all three support points belong to $[0,\infty)$; the displayed weights are nonnegative and sum to one. Thus $W$ is a Borel probability measure and $W(\{0\})=1/2$.

### H3

Pass: the population is exactly $W\otimes\sigma_3$, so the directions are uniform and independent of the absolute mean, including at all three atoms.

### H4

Pass: $Z\sim N(0,I_4)$ is the only randomness and $T_{\mu,v}=\mu+v^\top Z$, with no residual noise.

### H5

Pass: $q=2Q(104)\in(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

Pass: take $x_r=\min\{x\ge u:F_r(x)\ge2Q(x)/q\}$ when this set is nonempty, and use FDP zero otherwise, precisely as in the target definition.

### NOT

Fail. An explicit cap bound gives $\operatorname{FDR}_{\rm pop}<3q$, whereas the proposed right-hand side exceeds $7q/2$.

Here is the calculation; it bounds both possible contributions to the contact without assuming that its branch varies continuously. Put $a=1.01u=105.04$. The dimension-four cap, with $h=r-t\ge0$, satisfies
$$
H_r(t)=\frac2\pi\int_{t/r}^1\sqrt{1-s^2}\,ds
\le\frac{4\sqrt2}{3\pi}(h/r)^{3/2}
\quad(0\le t\le r).
$$
If $u\le x\le r\le a$ and $t=x-\eta$, then $t\ge u-\eta$, $t/r>.98$, and $(r+t)/2\ge .99r$. Mills' lower bound and maximization of $h^{3/2}e^{-.99rh}$ therefore give
$$
\frac{H_r(t)}{Q(t)}
\le C_0\{1+(u-\eta)^{-2}\}\frac{e^{r^2/2}}{r^2},
\qquad
C_0=\frac{4\sqrt2}{3\pi}\sqrt{2\pi}
\left(\frac{3}{1.98}\right)^{3/2}e^{-3/2}<.627.
$$
The two Mills bounds also give
$$
\frac{Q(x-\eta)}{Q(x)}
\le\frac{a+u^{-1}}{u-\eta}e^{a\eta}<2.774.
$$
Consequently, with a deliberately rounded constant,
$$
H_r(x-\eta)<2Q(x)\frac{e^{r^2/2}}{r^2}.
$$
Write $F_r=F_{\rm low}+F_{\rm high}$ for the two lower-mean atoms and the $2u$ atom. Monotonicity of $H_r$ and the fact that each mean's two-sided rejection probability is at most one imply
$$
F_{\rm low}(x)\le2H_r(x-\eta)
<4Q(x)\frac{e^{r^2/2}}{r^2},
\qquad F_{\rm high}(x)\le\varepsilon.
$$
A positive FDP requires a finite contact $u\le x_r<r$. If also $r\le a$, its identity $F_r(x_r)=2Q(x_r)/q$ implies at least one of
$$
F_{\rm low}(x_r)\ge Q(x_r)/q,
\qquad
F_{\rm high}(x_r)\ge Q(x_r)/q.
$$
The first condition requires $g(r):=r^2e^{-r^2/2}\le4q$. Since $g$ decreases for $r\ge u$ and $g(u)>4q$, let $b>u$ solve $g(b)=4q$. The exact $\chi_4$ radial tail yields
$$
\mathbb P(R\ge b)
=(1+b^2/2)e^{-b^2/2}
=2q(1+2/b^2)<2.001q.
$$
The second condition requires $Q(r)\le\varepsilon q$. Let $c>u$ satisfy $Q(c)=\varepsilon q$. The Mills ratio bound
$$
\frac{Q(a)}{Q(u)}
\le\frac{u+u^{-1}}a e^{-(a^2-u^2)/2}
<10^{-47}<2\varepsilon
$$
shows $c<a$. Thus another use of Mills' lower bound gives
$$
\frac{\mathbb P(R\ge c)}q
\le\sqrt{2\pi}(1+a^2/2)(a+a^{-1})e^{-16}
<\tfrac14.
$$
Finally,
$$
\frac{\mathbb P(R>a)}q
\le\frac{\sqrt{2\pi}}2(u+u^{-1})(1+a^2/2)
 e^{-(a^2-u^2)/2}<.001.
$$
Using FDP at most one and the preceding event inclusion therefore gives
$$
\operatorname{FDR}_{\rm pop}
<(2.001+\tfrac14+.001)q<3q.
$$
For $d=4$ the target constant is $M_4=1/\pi$. Since $\log(312)>5$ and $4/\pi>1$, its coefficient $2+4M_4(1+u^{-2})\log(3u)$ exceeds $7$. With $\pi_0=1/2$, the proposed right-hand side exceeds $7q/2>3q$. This proves failure of NOT for this object. It supplies no conclusion about arbitrary mean mixtures or their first-contact branches.

## Failure

NOT fails first: splitting the contact equation into near-null-bulk and rare-remote-atom contributions bounds this mixture's FDR below $3q$, below the proposed bound at $\pi_0=1/2$.
