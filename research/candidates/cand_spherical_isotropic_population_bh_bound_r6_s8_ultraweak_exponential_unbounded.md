---
type: candidate
title: Ultraweak exponential alternative with unbounded support
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
round: 6
slot: 8
direction: drop_hypothesis
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:07:00.541Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, and $\varepsilon=e^{-4u^2}$. Let $\nu$ have density $\varepsilon^{-1}e^{-\mu/\varepsilon}$ on $(0,\infty)$ and set
$$
W=\tfrac12\delta_0+\tfrac12\nu.
$$
Use the product directional population $W\otimes\sigma_3$, zero residual variance, and exactly the prescribed smallest finite admissible cutoff (with zero FDP when it does not exist). Thus $\pi_0=1/2$. This alternative law has unbounded support and positive mass in every interval $(0,b)$, while its mean tends very rapidly to zero on the displayed scale.

## Checks

### H1

$d=4$ is an integer at the allowed lower boundary.

### H2

$\nu$ is a Borel probability measure, is atomless at zero, and has support $[0,\infty)$. Hence $W$ is an allowed Borel absolute-mean law with unbounded support and $W(\{0\})=1/2$.

### H3

The population measure is explicitly $W\otimes\sigma_3$. At every mean, the prescribed directional kernel is the same uniform law and is independent of the mean.

### H4

The statistics are $T_{\mu,v}(Z)=\mu+v^\top Z$ for $Z\sim N(0,I_4)$, with no residual noise.

### H5

$q=2Q(104)$ lies in $(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

The cutoff and FDP are the ones in the supplied definition, including the no-finite-contact convention. No alternative contact branch is chosen.

### NOT

The proposed violation fails: this object's FDR is strictly below $7q\pi_0$, whereas its proposed multiplicative coefficient is greater than seven. The following argument does not replace the specified first contact.

First, the density of $rV_1$ in dimension four is
$$
f_r(z)=\frac{2}{\pi r}\sqrt{1-z^2/r^2}\,\mathbf 1_{\{|z|<r\}}.
$$
It is even and nonincreasing in $|z|$. For each $x\geq0$, the function $H_r(x-\mu)+H_r(x+\mu)$ is nondecreasing in $\mu\geq0$: its derivative is $f_r(x-\mu)-f_r(x+\mu)\geq0$, with the same conclusion by integration at density endpoints. Thus $F_r(x)\geq2H_r(x)$, and the contact identity gives the uniform bound $\operatorname{FDP}_{\rm pop}(r)\leq\pi_0$.

We next obtain a cap bound to locate radii at which this object can have a positive FDP. For $2\leq t\leq r$, put $y=r(r-t)$. Direct integration and the lower Mills inequality give
$$
H_r(t)\leq\frac{4\sqrt2}{3\pi}(1-t/r)^{3/2},\qquad
Q(t)\geq\frac{t}{1+t^2}\varphi(t).
$$
Because $r^2-t^2\geq y$ and $t+1/t\leq r(1+t^{-2})$,
$$
\frac{H_r(t)}{Q(t)}
\leq\frac{8}{3\sqrt\pi}(1+t^{-2})
\frac{e^{r^2/2}}{r^2}\,y^{3/2}e^{-y/2}
<\frac52\frac{e^{r^2/2}}{r^2}.
$$
Indeed the maximum of $y^{3/2}e^{-y/2}$ is $3\sqrt3e^{-3/2}$, so the coefficient is at most $10\sqrt{3/\pi}e^{-3/2}<5/2$, using $\pi>3$ and $e^{3/2}>4$. The latter follows, for example, from $e^3>1+3+9/2+27/6+81/24=131/8>16$.

Set
$$
a=e^{-2u^2},\qquad \delta=\nu((a,\infty))=e^{-e^{2u^2}}.
$$
For every $x\geq0$, splitting means at $a$ yields
$$
F_r(x)\leq2H_r(x-a)+\delta.
$$
Here means at most $a$ contribute at most $2H_r(x-a)$, and the remaining population mass is at most $\delta$ and contributes at most its mass.

The upper and lower Mills inequalities imply
$$
\frac{Q(2u)}q
\geq\frac{u^2}{1+4u^2}e^{-3u^2/2}
\geq\frac15e^{-3u^2/2}
>\delta.
$$
For the final inequality, $e^{2u^2}\geq2+3u^2/2$ for $u\geq1$, and $e^2>5$. Also $a\leq1/(8u^2)$ for $u\geq2$. The Gaussian hazard satisfies $\varphi(z)/Q(z)\leq z+1/z$ for positive $z$. Consequently, for $u\leq x\leq2u$ and $t=x-a\geq2$,
$$
\log\frac{Q(t)}{Q(x)}
\leq a(2u+1)
\leq\frac{2u+1}{8u^2}<\frac12,
\qquad \frac{Q(t)}{Q(x)}<2.
$$

If the specified contact has positive FDP at a radius $r\leq2u$, then $u\leq x_r<r$. Its contact identity, the mean split, and $\delta\leq Q(2u)/q\leq Q(x_r)/q$ give
$$
2H_r(x_r-a)\geq Q(x_r)/q,\qquad
\frac{H_r(x_r-a)}{Q(x_r-a)}\geq\frac1{4q}.
$$
The cap bound therefore forces
$$
g(r):=\frac{e^{r^2/2}}{r^2}>\frac1{10q}.
$$
The function $g$ is increasing for $r>\sqrt2$. Moreover $qg(u)\leq2/(\sqrt{2\pi}u^3)<1/10$, so there is a unique $s>u$ with $g(s)=1/(10q)$. Positive FDP at $r\leq2u$ requires $r>s$.

Since $R\sim\chi_4$, its exact tail gives
$$
\mathbb P(R\geq s)=(1+s^2/2)e^{-s^2/2}
=10q(1/s^2+1/2)<6q.
$$
Also $\mathbb P(R>2u)=(1+2u^2)e^{-2u^2}<q$. To verify this last loose inequality directly, lower Mills and $\pi<8$ give $q>e^{-u^2/2}/(4u)$, while for $u\geq4$,
$$
4u(1+2u^2)\leq12u^3
<\frac9{16}u^6
\leq e^{3u^2/2}.
$$
The final inequality is the third term of the exponential series. Combining the radius implication, the two tail bounds, and $\operatorname{FDP}_{\rm pop}\leq\pi_0$ proves
$$
\operatorname{FDR}_{\rm pop}<7q\pi_0.
$$

Finally $M_4=1/\pi$. Since $u=104$, $e<3$ implies $\log(3u)=\log312>5$, and $\pi<4$ implies
$$
2+4M_4(1+u^{-2})\log(3u)>7.
$$
Thus the proposed right side exceeds this object's FDR even before its positive additive allowance is used.

## Failure

NOT fails first: the ultraweak unbounded exponential alternative obeys $\operatorname{FDR}_{\rm pop}<7q\pi_0$, below the proposed coefficient.
