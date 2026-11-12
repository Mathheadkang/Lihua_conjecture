---
type: candidate
title: Six-dimensional two weak alternative means
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
round: 3
slot: 7
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Set $d=6$, $u=104$, $q=2Q(u)$, $a=1/u$, and
$$
W=\tfrac12\delta_0+\tfrac14\delta_{a/2}+\tfrac14\delta_a.
$$
Use the product population $W(d\mu)\sigma_5(dv)$, $Z\sim N(0,I_6)$, and $T_{\mu,v}=\mu+v^\top Z$ with no residual noise. Use exactly the specified smallest finite admissible cutoff $x_r$ and zero FDP when there is none. Thus $\pi_0=1/2$.

## Checks

### H1

$d=6$ is an integer at least four.

### H2

$W$ is a Borel probability law on $[0,\infty)$, with $W(\{0\})=1/2$. Every absolute mean belongs to $[0,1/u]$.

### H3

At every absolute mean the conditional directional kernel is exactly $\sigma_5$, independent of that mean.

### H4

The sole sampling randomness is $Z\sim N(0,I_6)$, and $T_{\mu,v}=\mu+v^\top Z$ has zero residual variance.

### H5

$q=2Q(104)$ lies in $(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

The cutoff and FDP are the target's population definitions, including the smallest finite cutoff and the no-contact convention. No alternative branch of a contact is selected.

### NOT

**Fail.** An analytic radial exclusion gives $\operatorname{FDR}_{\rm pop}<3q$, below the proposed right side.

Put $k=5/2$, $p=3/2$, $c=8/(3\pi)$, $K=8$, and
$$
r_*^2=u^2+2(d-1)\log u-2\log K,\qquad b=r_*+a.
$$
For $0\le t\le r$ the spherical density gives
$$
H_r(t)=c\int_{t/r}^1(1-v^2)^p\,dv
\le\frac{c2^p}{k}\left(\frac{r-t}{r}\right)^k.
$$
Since every mean is at most $a$, $F_r(x)\le2H_r(x-a)$. For $r\le r_*$, positive rejection mass at $x\ge u$ requires $u\le x\le b$ and $r\ge u-a$. Set $s=b-x\ge0$. The inequalities
$$
\frac{Q(u)}{Q(x)}\le\frac{x^2+1}{ux}e^{(x^2-u^2)/2},
\quad b^2-x^2\ge2us,
\quad\sup_{s\ge0}s^ke^{-us}=\left(\frac{k}{eu}\right)^k
$$
give
$$
\frac{F_r(x)Q(u)}{Q(x)}
\le\frac{L}{K}\left(\frac ur\right)^k
\frac{x^2+1}{ux}\exp\{r_*/u+1/(2u^2)\},
\qquad L=\frac{2c2^p}{k}\left(\frac ke\right)^k.
$$
Here $r_*^2<u^2+50$, $r_*/u<101/100$, and $b/u<102/100$. The three factors following $L/K$ are less than $11/10$, $11/10$, and $3$, respectively; use $r\ge u-a$, $k<3$, and $e^{21/20}<3$. Their product is less than $4$. Also $\pi>3$, $2^{3/2}<3$, and $e>8/3$ give
$$
L<\frac{32}{15}\left(\frac{15}{16}\right)^2=\frac{15}{8}<2.
$$
Consequently $F_r(x)Q(u)/Q(x)<4L/K<1$. For $x>b$ rejection mass is zero. The BH admissibility condition requires this ratio to be at least one, so no finite contact exists on $r\le r_*$.

The FDP is at most one, so $\operatorname{FDR}_{\rm pop}\le\mathbb P(R>r_*)$. With $z=r_*^2/2$, the exact $\chi_6$ tail and lower Mills bound give
$$
\frac{\mathbb P(R>r_*)}{q}
\le8\sqrt{\frac\pi2}\frac{u^2+1}{u^6}\left(1+z+\frac{z^2}{2}\right)
<8\frac{63}{50}\frac{1001}{1000}\frac{13}{100}<3.
$$
Indeed $r_*^2<(101/100)u^2$ and $u=104$ imply
$1+z+z^2/2<(13/100)u^4$; also $u^2+1<(1001/1000)u^2$.

Finally $M_6=\sqrt3/(2\pi)>1/4$ (use $\pi<22/7<2\sqrt3$), and $\log(3u)>4$. Since $\pi_0=1/2$, the proposed right side exceeds
$$
\frac q2\{2+4(1/4)4\}=3q.
$$
The object therefore satisfies the claimed bound. The failure rests on exact inequalities and chi-tail formulas rather than floating-point evidence.

## Failure

NOT fails first: the no-contact radial exclusion gives $\operatorname{FDR}_{\rm pop}<3q$, while the claimed right side exceeds $3q$.
