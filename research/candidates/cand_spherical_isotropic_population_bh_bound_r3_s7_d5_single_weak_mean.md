---
type: candidate
title: Five-dimensional single weak alternative mean
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

Set $d=5$, $u=104$, $q=2Q(u)$, $a=1/u$, and
$$
W=\tfrac12\delta_0+\tfrac12\delta_a.
$$
Use the product population $W(d\mu)\sigma_4(dv)$, $Z\sim N(0,I_5)$, and $T_{\mu,v}=\mu+v^\top Z$ with no residual noise. Use exactly the specified smallest finite admissible cutoff $x_r$ and zero FDP when there is none. Thus $\pi_0=1/2$.

## Checks

### H1

$d=5$ is an integer at least four.

### H2

$W$ is a Borel probability law on $[0,\infty)$, with $W(\{0\})=1/2$. Every absolute mean belongs to $[0,1/u]$.

### H3

At every absolute mean the conditional directional kernel is exactly $\sigma_4$, independent of that mean.

### H4

The sole sampling randomness is $Z\sim N(0,I_5)$, and $T_{\mu,v}=\mu+v^\top Z$ has zero residual variance.

### H5

$q=2Q(104)$ lies in $(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

The cutoff and FDP are the target's population definitions, including the smallest finite cutoff and the no-contact convention. No alternative branch of a contact is selected.

### NOT

**Fail.** An analytic radial exclusion gives $\operatorname{FDR}_{\rm pop}<3q$, below the claimed right side.

Put $k=2$, $p=1$, $c=3/4$, $K=4$, and
$$
r_*^2=u^2+2(d-1)\log u-2\log K,\qquad b=r_*+a.
$$
For $0\le t\le r$ the spherical density gives
$$
H_r(t)=c\int_{t/r}^1(1-v^2)^p\,dv
\le\frac{c2^p}{k}\left(\frac{r-t}{r}\right)^k.
$$
All means are at most $a$, so $F_r(x)\le2H_r(x-a)$. For $r\le r_*$, positive rejection mass at $x\ge u$ requires $u\le x\le b$ and $r\ge u-a$. Put $s=b-x\ge0$. Using
$$
\frac{Q(u)}{Q(x)}\le\frac{x^2+1}{ux}e^{(x^2-u^2)/2},
\quad b^2-x^2\ge2us,
\quad\sup_{s\ge0}s^ke^{-us}=\left(\frac{k}{eu}\right)^k
$$
gives
$$
\frac{F_r(x)Q(u)}{Q(x)}
\le\frac{L}{K}\left(\frac ur\right)^k
\frac{x^2+1}{ux}\exp\{r_*/u+1/(2u^2)\},
\qquad L=\frac{2c2^p}{k}\left(\frac ke\right)^k=\frac6{e^2}<1.
$$
Here $r_*^2<u^2+50$, $r_*/u<101/100$, and $b/u<102/100$. The three factors following $L/K$ are less than $11/10$, $11/10$, and $3$, respectively: use $r\ge u-a$, $k<3$, and $e^{21/20}<3$. Their product is less than $4$. Consequently $F_r(x)Q(u)/Q(x)<4L/K<1$. For $x>b$ rejection mass is zero. Thus no finite BH contact exists at any $r\le r_*$.

The FDP is at most one, hence $\operatorname{FDR}_{\rm pop}\le\mathbb P(R>r_*)$. The exact $\chi_5$ tail is
$$
\mathbb P(R>r)=2Q(r)+\sqrt{\frac2\pi}e^{-r^2/2}\left(r+\frac{r^3}{3}\right).
$$
Upper Mills at $r_*$ and lower Mills at $u$ imply
$$
\frac{\mathbb P(R>r_*)}{q}
<4\frac{u^2+1}{u^5}\left(\frac{r_*^3}{3}+r_*+\frac1{r_*}\right)
<4\frac{1001}{1000}\frac7{20}<3.
$$
Indeed $u<r_*<(101/100)u$ and $u=104$ give
$r_*^3/3+r_*+1/r_*<(7/20)u^3$; also $u^2+1<(1001/1000)u^2$.

Finally $M_5=1/(2\sqrt3)>1/4$ and $\log(3u)>4$. With $\pi_0=1/2$, the proposed right side exceeds
$$
\frac q2\{2+4(1/4)4\}=3q.
$$
Thus this object satisfies the proposed bound. All exclusion steps are analytic, without interpreting floating-point optimization as a certificate.

## Failure

NOT fails first: the no-contact radial exclusion gives $\operatorname{FDR}_{\rm pop}<3q$, while the claimed right side exceeds $3q$.
