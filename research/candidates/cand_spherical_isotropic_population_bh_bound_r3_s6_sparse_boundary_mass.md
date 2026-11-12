---
type: candidate
title: Exponentially vanishing alternative mass at minimum dimension
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
slot: 6
direction: boundary_degenerate
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Set $d=4$, $u=104$, $q=2Q(u)$, $\varepsilon=e^{-u^2}$, and
$$
W=(1-\varepsilon)\delta_0+\varepsilon\delta_{4u},
\qquad \pi_0=1-\varepsilon.
$$
Use the product directional population $W\otimes\sigma_3$, $Z\sim N(0,I_4)$, and $T_{\mu,v}=\mu+v^\top Z$ with zero residual variance. Use exactly the target's smallest finite admissible Gaussian-statistic cutoff, and its zero-FDP convention when there is no contact. This tests exponentially vanishing alternative mass, where the elementary cutoff bound obtained by dividing by alternative mass becomes very large. The null proportion is outside the three fixed parameter pairs excluded on the supplied search board.

## Checks

### H1

The population has the required spherical Gaussian-factor representation with zero residual variance: conditional on $Z$, each statistic equals the deterministic value $\mu+v^\top Z$.

### H2

The dimension is the allowed minimum integer $d=4$.

### H3

$W$ is a Borel probability law on $[0,\infty)$ because $0<\varepsilon<1$, both support points are nonnegative, and the two masses sum to one. Its atom at zero is exactly $\pi_0=1-\varepsilon>1/2$.

### H4

At each absolute mean, including means outside the support, specify the conditional directional kernel to be $\sigma_3$. Thus directions are uniform and independent of the mean.

### H5

Strict positivity of $Q(104)$ and $Q(104)<1/2$ give $q\in(0,1)$, and $Q^{-1}(q/2)=104$ meets the lower endpoint exactly.

### H6

For each $r>0$ use
$$
x_r=\min\{x\geq u:F_r(x)\geq2Q(x)/q\}
$$
when the set is nonempty. The spherical tails are continuous, so the finite contact identity holds. Its FDP is $q\pi_0H_r(x_r)/Q(x_r)$; use FDP zero when the set is empty or $r=0$. This is the prescribed largest population BH p-value threshold.

### NOT

This check fails by an explicit upper bound. The argument does not infer failure from numerical root finding or from the absence of contacts.

Put
$$
S(r)=\sup_{x\geq u}\frac{H_r(x)}{Q(x)},\qquad
b=\sqrt{u^2+10\log u},\qquad
K=\frac{8}{3\sqrt\pi}\left(\frac{3}{2e}\right)^{3/2}.
$$
At a finite contact, the contact identity and the false-rejection mass being at most the total rejection mass give
$$
\operatorname{FDP}_{\mathrm{pop}}(r)\leq
\min\{1,q\pi_0S(r)\}.
$$
The same bound holds without a contact. For $r\leq u$ the FDP is zero because $H_r(x)=0$ for every $x\geq u$.

For $u\leq x<r$ the dimension-four coordinate density gives
$$
H_r(x)=\frac{2}{\pi r}\int_x^r\sqrt{1-t^2/r^2}\,dt
\leq\frac{4\sqrt2}{3\pi}\frac{(r-x)^{3/2}}{r^{3/2}}.
$$
The Gaussian Mills lower bound $Q(x)\geq\phi(x)x/(1+x^2)$ implies
$$
\frac{H_r(x)}{Q(x)}
\leq\frac{8}{3\sqrt\pi}(1+u^{-2})r^{-1/2}
(r-x)^{3/2}e^{x^2/2}.
$$
Since $(r^2-x^2)/2\geq u(r-x)$ and
$\sup_{y\geq0}y^{3/2}e^{-uy}=(3/(2eu))^{3/2}$, this yields
$$
S(r)\leq K(1+u^{-2})r^{-1/2}u^{-3/2}e^{r^2/2}.
$$
The radius has the $\chi_4$ density $r^3e^{-r^2/2}/2$. Splitting at $b$ therefore gives
$$
\begin{aligned}
\operatorname{FDR}_{\mathrm{pop}}
&\leq q\pi_0\frac K2(1+u^{-2})u^{-3/2}
\int_u^b r^{5/2}\,dr+\mathbb P(R>b)\\
&\leq q\pi_0\frac K2(1+u^{-2})(b/u)^{3/2}5\log u
+e^{-b^2/2}(1+b^2/2).
\end{aligned}
$$
Here $r^{5/2}\leq b^{3/2}r$ on $[u,b]$ was used in the second line.

The following deliberately loose elementary bounds suffice, with strict inequalities:
$$
K<\frac{31}{50},\quad 1+u^{-2}<\frac{1001}{1000},\quad
\log104<\frac{93}{20},\quad
\frac bu<\frac{1003}{1000},\quad
(b/u)^{3/2}<\frac{201}{200}.
$$
For example $K^2=24/(\pi e^3)$, and $\pi>157/50$, $e>271/100$ give the first bound. The displayed bound on $\log104$ gives the bound on $b/u$ by squaring; cubing and squaring gives the following bound on $(b/u)^{3/2}$. Consequently the coefficient of $q\pi_0$ in the integral term is less than
$$
\frac{31}{100}\frac{1001}{1000}\frac{201}{200}\frac{93}{4}
<\frac{363}{50}=7.26.
$$
For the remainder, $e^{-b^2/2}=e^{-u^2/2}u^{-5}$ and the same Mills lower bound give
$$
\frac{\mathbb P(R>b)}{q}
\leq\sqrt{2\pi}\frac{u^2+1}{2u}(1+b^2/2)u^{-5}
<\frac3{u^2}.
$$
The last inequality follows from $\sqrt{2\pi}<3$, $(u^2+1)/(2u)<u$, and $1+b^2/2<u^2$. Since $\pi_0>1/2$, this remainder divided by $q\pi_0$ is less than $6/u^2<1/1000$. Hence
$$
\operatorname{FDR}_{\mathrm{pop}}<7.3q\pi_0.
$$
On the other hand $M_4=1/\pi$. Using $\pi<22/7$ and $\log312>11/2$ shows
$$
2+4M_4(1+u^{-2})\log(3u)>9.
$$
The proposed right side is thus greater than $9q\pi_0$, even before its positive $e^{-2u^2}$ term is included. This object cannot violate it. Approximate values $K=0.6167213$, integral coefficient $7.1844502$, and target coefficient $9.3128948$ are reproducibility diagnostics only; the strict comparisons above establish the failure.

## Failure

NOT fails first: an exponentially sparse alternative with $\pi_0=1-e^{-10816}$ still has $\operatorname{FDR}_{\mathrm{pop}}<7.3q\pi_0$, while the proposed right side is greater than $9q\pi_0$.
