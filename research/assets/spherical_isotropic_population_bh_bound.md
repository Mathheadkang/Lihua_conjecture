---
type: theorem
title: Uniform dimension bound for isotropic spherical population BH
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - spherical_isotropic_directional_population
  - spherical_population_bh_false_discovery_rate
tags:
  - gaussian_bh
  - spherical_population
  - uniform_dimension_bound
---

## Statement

Consider the [isotropic spherical directional population](../definitions/spherical_isotropic_directional_population.md) with zero residual variance, any integer $d\geq4$, and any Borel absolute-mean probability law $W$ on $[0,\infty)$, including unbounded support. At every absolute mean the directions are uniform and independent of that mean. Let $\pi_0=W(\{0\})$. Use the [largest spherical population BH threshold and false discovery rate](../definitions/spherical_population_bh_false_discovery_rate.md): its Gaussian-statistic cutoff is the smallest finite $x\geq u$ with $F_r(x)\geq2Q(x)/q$, and its FDP is zero when no finite contact exists.

For every $q\in(0,1)$ with $u=Q^{-1}(q/2)\geq104$, the proposed bound is
$$
\operatorname{FDR}_{\mathrm{pop}}(q;W,d)
\leq q\pi_0\left\{2+4M_d(1+u^{-2})\log(3u)\right\}+e^{-2u^2},
$$
where $\log$ is the natural logarithm, $\Gamma$ is Euler's gamma function, and
$$
M_d=\frac{\Gamma(d/2)}{\sqrt\pi\,\Gamma((d-1)/2)\sqrt{d-2}}
\left(\frac{d-3}{d-2}\right)^{(d-3)/2}\leq1.
$$
In particular, as $q\downarrow0$, this gives $\operatorname{FDR}_{\mathrm{pop}}=O(q\log u)=o(qu)$ uniformly over $d\geq4$ and all such $W$, allowing $d$ and $W$ to depend on $q$.

## Scope

This is a separate continuous-population target with uniform directions conditional on every absolute mean and zero residual variance. It asserts no finite Gaussian-vector approximation, no conclusion for nonuniform or mean-dependent directions, and no resolution of either unrestricted one-sided or two-sided Gaussian BH target.

## Research status

This node extracts the approved project's additional supporting target. It is a proposed theorem without a proof or verification verdict. Any proof must control the first contact globally, including births and switches of contacts and positive variation as a measure, and then justify the conditional radial transport and cutoff bounds. An almost-everywhere derivative estimate alone does not supply that control. The candidate source identified by the project is `research-local/spherical_radial_bh_global_population_bound_20261104.md`; no proof from that note is certified here.

## Proof

**1. Fixed parameters and null mass.** Fix an integer $d\ge4$, a Borel probability law $W$ on $[0,\infty)$, and $q$ with $u=Q^{-1}(q/2)\ge104$. All the quantities $H_r$, $F_r$, $x_r$ and $\pi_0=W(\{0\})$ have exactly the meanings in the two approved definitions. In particular, $x_r=\infty$ means that there is no finite contact. Write
$$
\phi(x)=(2\pi)^{-1/2}e^{-x^2/2},\qquad
c_d=\frac{\Gamma(d/2)}{\sqrt\pi\,\Gamma((d-1)/2)},\qquad
a=\max\{u,52\sqrt d/u\},\qquad b=\sqrt d+2u,
\qquad \ell(r)=\frac r{2\sqrt d}.
$$
We reserve $B$ for $-\partial_xF_r(x)$, $D$ for $r\partial_rF_r(x)$, and $\Lambda(r)$ for a coefficient defined below. If $\pi_0=0$, the defined FDP and FDR are zero, and the conclusion follows. Suppose henceforth that $\pi_0>0$.

At a finite contact the contact identity gives
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
=q\pi_0\frac{H_r(x_r)}{Q(x_r)}\in[0,1],
$$
because the numerator is a submass of the total rejection mass. At no contact the FDP is zero. For every finite $r>0$, the uniform sphere has a positive-measure band $|rv_1|<u$, so $2H_r(u)<1$. Each component rejection mass is at most one; hence
$$
F_r(u)\le2\pi_0H_r(u)+(1-\pi_0)<1=2Q(u)/q.
$$
Thus the endpoint $u$ cannot be a finite contact with positive null mass. We also rederive attainment and the contact identity in part 3.

**2. Sphere density and constants.** Parameterize a unit-sphere latitude by $(s,\sqrt{1-s^2}\,w)$, where $-1<s<1$ and $w\in\mathbb S^{d-2}$. The derivative in the $s$ direction has length $(1-s^2)^{-1/2}$ and is perpendicular to the latitude directions, whose area scales by $(1-s^2)^{(d-2)/2}$. Thus the latitude area is proportional to $(1-s^2)^{(d-3)/2}\,ds$.

Here are the required normalizations. For positive $\alpha,\beta$, changing variables $v=t+s$, $z=t/(t+s)$ in the product of the defining gamma integrals gives
$$
\Gamma(\alpha)\Gamma(\beta)
=\Gamma(\alpha+\beta)\int_0^1 z^{\alpha-1}(1-z)^{\beta-1}\,dz.
$$
The Gaussian integral, obtained by squaring $\int_{\mathbb R}e^{-t^2}\,dt$ and using plane polar coordinates, gives $\Gamma(1/2)=\sqrt\pi$. Consequently, substitution $z=s^2$ gives
$$
\int_{-1}^1(1-s^2)^{(d-3)/2}\,ds
=\frac{\sqrt\pi\,\Gamma((d-1)/2)}{\Gamma(d/2)}.
$$
Scaling a latitude by $r$ therefore yields the density and tail
$$
g_r(t)=\frac{c_d}{r}\left(1-\frac{t^2}{r^2}\right)^{(d-3)/2}
\mathbf1_{\{|t|<r\}},\qquad H_r(t)=\int_t^\infty g_r(z)\,dz.
$$
We set the density equal to zero at both endpoints. Since $(d-3)/2>0$, this extension is continuous jointly for $r>0$ and $t\in\mathbb R$. It also verifies the strict central-band assertion in part 1.

For $s=|t|/r\in[0,1]$, maximizing $c_ds(1-s^2)^{(d-3)/2}$ gives the unique interior maximum at $s=(d-2)^{-1/2}$: the derivative has the sign of $1-(d-2)s^2$. Thus
$$
\sup_t |t|g_r(t)
=\frac{c_d}{\sqrt{d-2}}
\left(\frac{d-3}{d-2}\right)^{(d-3)/2}=M_d>0.
$$
Applying Cauchy--Schwarz to the gamma integral, with integrand the product of the square roots of $t^{(d-1)/2-1}e^{-t}$ and $t^{(d+1)/2-1}e^{-t}$, gives
$$
\Gamma(d/2)^2\le\Gamma((d-1)/2)\Gamma((d+1)/2).
$$
Integration by parts in the defining integral gives $\Gamma(z+1)=z\Gamma(z)$ for $z>0$. It follows that
$$
c_d\le\sqrt{\frac{d-1}{2\pi}}\le\sqrt d,\qquad
M_d\le\sqrt{\frac{d-1}{2\pi(d-2)}}<1\quad(d\ge4).
$$

Let $U$ be uniform on the unit sphere. Coordinate symmetry and $\sum_iU_i^2=1$ give $\mathbb EU_1^2=1/d$. Put $A=\mathbb EU_1^4$ and $C=\mathbb EU_1^2U_2^2$. Sign symmetry kills the odd mixed moments. Rotational invariance of $(U_1+U_2)/\sqrt2$ gives $A=(2A+6C)/4$, so $A=3C$. Taking expectations in $(\sum_iU_i^2)^2=1$ then gives
$$
C=\frac1{d(d+2)},\qquad A=\frac3{d(d+2)}.
$$
For $Y=dU_1^2$, we therefore have $\mathbb EY=1$ and $\mathbb EY^2=3d/(d+2)\le3$. Moreover
$$
\frac34\le\mathbb E[Y\mathbf1_{\{Y\ge1/4\}}]
\le(\mathbb EY^2)^{1/2}\mathbb P(Y\ge1/4)^{1/2}.
$$
Thus $\mathbb P(Y\ge1/4)\ge3/16$. By symmetry of $U_1$,
$$
H_r(\ell(r))=\mathbb P\left(U_1\ge\frac1{2\sqrt d}\right)\ge\frac3{32}.
$$

**3. Regularity and selection for arbitrary $W$.** The scaling identity $H_r(t)=H_1(t/r)$ and the continuous zero extension of $g_r$ give, including at $t=\pm r$,
$$
\partial_tH_r(t)=-g_r(t),\qquad
\partial_rH_r(t)=\frac tr g_r(t).
$$
For $\mu\ge0$ put
$$
f_\mu(r,x)=H_r(x-\mu)+H_r(x+\mu),\qquad
b_\mu(r,x)=g_r(x-\mu)+g_r(x+\mu),
$$
$$
d_\mu(r,x)=(x-\mu)g_r(x-\mu)+(x+\mu)g_r(x+\mu).
$$
The actual two folded boundaries therefore give $-\partial_x f_\mu=b_\mu$ and $r\partial_r f_\mu=d_\mu$. Uniformly in $\mu$,
$$
0\le b_\mu\le2c_d/r,\qquad |d_\mu|\le2M_d.
$$
On every compact rectangle with $r$ bounded away from zero these are uniform bounds for the component derivatives. Dominated convergence, or integration of the bounded derivatives along coordinate line segments followed by dominated convergence, therefore justifies differentiation under $W$ and continuity of the resulting derivatives. Explicitly,
$$
B(r,x)=\int b_\mu(r,x)\,W(d\mu)=-\partial_xF_r(x),\qquad
D(r,x)=\int d_\mu(r,x)\,W(d\mu)=r\partial_rF_r(x).
$$
Thus $F$ is continuously differentiable for $r>0$, without any bound on the support or moments of $W$.

If a finite feasible cutoff $v$ exists, the feasible set intersected with $[u,v]$ is nonempty and compact by continuity, and its minimum is the minimum of the whole feasible set. At a minimum larger than $u$, strict feasibility would, by continuity, give a smaller feasible cutoff; at $u$, $F_r(u)\le1=2Q(u)/q$. This proves attainment and the contact identity. For every finite $t\ge u$,
$$
\{r:x_r\le t\}
=\left\{r:\max_{u\le x\le t}\{F_r(x)-2Q(x)/q\}\ge0\right\}.
$$
On compact neighborhoods of any positive radius, joint continuity is uniform on the displayed compact $x$ interval. The maximum is therefore continuous in $r$. This proves that the extended-valued $x_r$ is Borel measurable. The FDP, set equal to zero at no contact, is consequently Borel measurable as well. If a finite contact satisfies $x_r\ge r$, then $H_r(x_r)=0$ and its FDP is zero.

**4. A gradient budget with both signs of $D$.** At $r>0$, $x\ge0$, define
$$
I_- =\int(d_\mu(r,x))_-\,W(d\mu),\qquad
I_+ =\int(d_\mu(r,x))_+\,W(d\mu),\qquad D=I_+-I_-.
$$
If $d_\mu<0$, then necessarily $\mu>x$: otherwise both coefficients in $d_\mu$ are nonnegative. In that case $H_r(x-\mu)\ge1/2$, so $f_\mu\ge1/2$. Only the $(x-\mu)$ term can be negative, and its absolute value is at most $M_d$. Hence $(d_\mu)_-\le2M_df_\mu$ pointwise, and
$$
I_-\le2M_dF_r(x),\qquad D\ge-2M_dF_r(x).
$$
For any $x\ge\ell>0$, split the component integral into $\mu\le x-\ell$ and its complement. On the first set both $x-\mu$ and $x+\mu$ are at least $\ell$, so $d_\mu\ge\ell b_\mu\ge0$ and its contribution to $B$ is at most $I_+/\ell$. On the complement $x-\mu<\ell$, so $f_\mu\ge H_r(\ell)$, whereas $b_\mu\le2g_r(0)$. Whenever $H_r(\ell)>0$, these facts give
$$
B\le\frac{I_+}{\ell}+\frac{2g_r(0)}{H_r(\ell)}F
\le\frac D\ell+\left\{\frac{2M_d}{\ell}+\frac{2g_r(0)}{H_r(\ell)}\right\}F.
$$
Here and below $F$ without arguments in a differential calculation denotes $F_r(x)$ at the displayed point. Set $\ell=\ell(r)$ and
$$
\Lambda(r)=\frac{2M_d}{\ell(r)}+\frac{2g_r(0)}{H_r(\ell(r))}.
$$
The bounds in part 2 give
$$
\Lambda(r)\le\left(4+\frac{64}{3}\right)\frac{\sqrt d}{r}
<\frac{26\sqrt d}{r}.
$$
The budget $B\le D/\ell(r)+\Lambda(r)F$ holds for every sign of $D$ when $x\ge\ell(r)$.

Since $52/u\le1/2$, both $u$ and $52\sqrt d/u$ are strictly less than $b=\sqrt d+2u$, so $a<b$. For $r\in[a,b]$,
$$
\ell(r)\le\frac b{2\sqrt d}=\frac12+\frac u{\sqrt d}
\le\frac12+\frac u2\le u.
$$
Also $r\ge a\ge52\sqrt d/u$, whether either argument attains the maximum defining $a$, and therefore $\Lambda(r)\le u/2$. Thus this all-signed budget applies to every $x\ge u$ throughout the core interval.

**5. Global feasible paths.** For $x>0$, integration by parts with $\phi'(t)=-t\phi(t)$ gives
$$
Q(x)=\frac{\phi(x)}x-\int_x^\infty\frac{\phi(t)}{t^2}\,dt.
$$
The integral is positive and at most $Q(x)/x^2$. Rearranging proves
$$
x<h(x):=\frac{\phi(x)}{Q(x)}\le x+\frac1x.
$$
Fix $a\le r_1<r_2\le b$ and any finite feasible $x_1\ge u$ at $r_1$. For $r\in[r_1,r_2]$ define the finite differentiable path
$$
X(r)=\{x_1^2+8M_d\log(r/r_1)\}^{1/2},\qquad
X'(r)=\frac{4M_d}{rX(r)},\qquad
\beta(r)=\frac r{\ell(r)}X'(r)=\frac{8M_d\sqrt d}{rX(r)}.
$$
Because $r\ge52\sqrt d/u$ and $X(r)\ge u$, we have $0<\beta(r)\le2M_d/13<1$. Where $F_r(X(r))>0$, define
$$
J(r)=\log\frac{qF_r(X(r))}{2Q(X(r))}.
$$
All derivatives here are justified by part 3, and part 4 gives
$$
\begin{aligned}
J'(r)&=\frac{D}{rF}-\frac BF X'+h(X)X'\\
&\ge\frac{D}{rF}(1-\beta)+(h(X)-\Lambda)X'\\
&\ge-\frac{2M_d}{r}(1-\beta)+\frac X2\frac{4M_d}{rX}
=\frac{2M_d\beta}{r}>0.
\end{aligned}
$$
The second inequality uses $1-\beta>0$, $D\ge-2M_dF$, and $\Lambda\le u/2\le X/2<h(X)-X/2$.

Initially $F_{r_1}(x_1)\ge2Q(x_1)/q>0$ and $J(r_1)\ge0$. If $F_r(X(r))$ had a zero on this compact path, continuity would give a first zero $r_0>r_1$. On $[r_1,r_0)$ the derivative inequality implies $J(r)\ge J(r_1)$, whence
$$
F_r(X(r))\ge\frac2q Q(X(r))e^{J(r_1)}
\ge\frac2q Q(X(r_2))e^{J(r_1)}>0.
$$
Continuity at $r_0$ is a contradiction. Thus no zero occurs, $J\ge0$ throughout, and $X(r)$ is feasible throughout. Taking $x_1=x_{r_1}$ shows both persistence of finite contacts and, by minimality at $r_2$,
$$
x_{r_2}^2-x_{r_1}^2\le8M_d\log(r_2/r_1)
\qquad(a\le r_1\le r_2\le b,\ x_{r_1}<\infty).
$$
The case $r_1=r_2$ is immediate. This is a comparison of feasible sets at every pair of radii; it requires no differentiable branch of selected contacts and applies at tangencies, births, and switches.

**6. Jumps and positive variation.** Choose a finite $T>b$ and set $y(r)=\min\{x_r,T\}$, with $y(r)=T$ at no contact. If $x_{r_1}=\infty$, then $y(r_1)=T\ge y(r_2)$. If $T\le x_{r_1}<\infty$, the same inequality holds. If $x_{r_1}<T$, part 5 makes $x_{r_2}$ finite and gives $y(r_2)^2-y(r_1)^2\le x_{r_2}^2-x_{r_1}^2$. All three cases therefore give
$$
y(r_2)^2-y(r_1)^2\le8M_d\log(r_2/r_1).
$$
It follows exactly, for the actual Borel representative, that
$$
m(r):=y(r)^2-8M_d\log r
\quad\hbox{is nonincreasing on }[a,b].
$$
This bounded monotone function has finite one-sided limits, bounded variation, and at most countably many discontinuities: for each positive integer $n$ there are only finitely many drops exceeding $1/n$, since their sum is bounded by $m(a)-m(b)$. Adding the smooth function $8M_d\log r$ proves the same bounded-variation and regulatedness properties for $y^2$. In particular, every upward increment has the displayed logarithmic bound, and taking limits from both sides excludes positive jumps.

For completeness the measure bound follows from interval increments. Take the right-continuous representative on the interior. Passing the all-pairs inequality to right limits gives, on each half-open interior interval $(s,t]$,
$$
y(t)^2-y(s)^2\le8M_d\int_s^t\frac{dr}{r}.
$$
The increment measure of $m$ is a nonpositive measure, because its negative is the Lebesgue--Stieltjes measure of the nondecreasing function $-m$. Adding the measure $8M_d\,dr/r$ therefore gives
$$
d(y^2)\le8M_d\,\frac{dr}{r}.
$$
This is a measure inequality, rather than just an almost-everywhere derivative assertion. Endpoint choices and the countably many possible changes from the actual representative do not affect radial integrals. Part 8 will, in fact, use the actual all-pairs inequality directly.

**7. Conditional squared excess.** Gaussian polar coordinates factor the density into a radial function times uniform spherical area. Therefore $Z=RU$ has $U$ uniform and independent of $R$; normalization using the gamma integral yields
$$
f_{\chi_d}(r)=\frac{2^{1-d/2}}{\Gamma(d/2)}r^{d-1}e^{-r^2/2}\mathbf1_{\{r>0\}}.
$$
In particular,
$$
\mathbb P(R\in dr,Z_1\ge x)=f_{\chi_d}(r)H_r(x)\,dr,
\qquad
k(r,x):=f_{\chi_d}(r)\frac{H_r(x)}{Q(x)}
$$
is the normalized conditional density of $R$ given $Z_1\ge x$. It vanishes for $r\le x$ when $x>0$.

Let $V=\sum_{j=2}^dZ_j^2$ and $\nu=d-1$. Independence of Gaussian coordinates makes $V$ independent of $Z_1$ and gives, again by polar coordinates and normalization,
$$
f_{\chi^2_\nu}(v)=\frac{v^{\nu/2-1}e^{-v/2}}{2^{\nu/2}\Gamma(\nu/2)}\mathbf1_{\{v>0\}}.
$$
For $x\ge u>0$, the substitution $z=\sqrt{x^2+t}$ in the conditional Gaussian density on $z\ge x$ gives the density of $E_x=Z_1^2-x^2$:
$$
p_x(t)=\frac{\phi(\sqrt{x^2+t})}{2Q(x)\sqrt{x^2+t}}\mathbf1_{\{t\ge0\}}
=\frac{h(x)e^{-t/2}}{2\sqrt{x^2+t}}\mathbf1_{\{t\ge0\}}
\le(1+u^{-2})\frac{e^{-t/2}}2\mathbf1_{\{t\ge0\}}.
$$
It integrates to one by the same substitution; the inequality follows from $h(x)\le x+1/x$ and $\sqrt{x^2+t}\ge x$.

To check the convolution constant, put $G_\alpha(v)=v^{\alpha-1}e^{-v/2}/(2^\alpha\Gamma(\alpha))$ for $v>0$, extended by zero for $v\le0$. For $w>0$, the beta identity in part 2 gives
$$
\begin{aligned}
(G_\alpha*G_\beta)(w)
&=\frac{e^{-w/2}}{2^{\alpha+\beta}\Gamma(\alpha)\Gamma(\beta)}
\int_0^w t^{\alpha-1}(w-t)^{\beta-1}\,dt\\
&=\frac{w^{\alpha+\beta-1}e^{-w/2}}{2^{\alpha+\beta}\Gamma(\alpha+\beta)}
=G_{\alpha+\beta}(w).
\end{aligned}
$$
Conditional on $Z_1\ge x$, $E_x$ is still independent of $V$. Convolving its density bound with $G_{\nu/2}$, and using $\alpha=1$, gives the upper bound $(1+u^{-2})f_{\chi^2_{d+1}}$ for the density of $E_x+V$. The identity $R^2=x^2+E_x+V$ and its Jacobian $2r$ therefore give
$$
k(r,x)\le(1+u^{-2})\,2r\,f_{\chi^2_{d+1}}(r^2-x^2),\qquad x\ge u.
$$
The density on the right is extended by zero to nonpositive arguments, consistently with $k(r,x)=0$ for $r\le x$.

**8. Borel transport on the core.** Set $k(r,\infty)=0$. For $r\in[a,b]$, $T>b$ implies
$$
k(r,x_r)=k(r,y(r)):
$$
this is equality with the original cutoff if $x_r<T$, while both sides are zero if $x_r\ge T$ or $x_r=\infty$. Put
$$
s=r^2,\qquad \zeta(s)=s-y(\sqrt s)^2,\qquad c=1-\frac{4M_d}{a^2}>0.
$$
Positivity follows from $a\ge u\ge104$ and $M_d<1$. For $a^2\le s_1<s_2\le b^2$, part 6 gives
$$
\begin{aligned}
\zeta(s_2)-\zeta(s_1)
&\ge(s_2-s_1)-4M_d\log(s_2/s_1)\\
&\ge\left(1-\frac{4M_d}{a^2}\right)(s_2-s_1)=c(s_2-s_1),
\end{aligned}
$$
where $\log(s_2/s_1)=\int_{s_1}^{s_2}dt/t\le(s_2-s_1)/a^2$. Hence $\zeta$ is strictly increasing and Borel measurable, including its actual point values.

We now prove the needed domination without differentiating $\zeta$. If $I$ is a finite-length target interval, order monotonicity shows that $\zeta^{-1}(I)$ is an interval up to endpoints, possibly empty. For any two of its points $s_1<s_2$, the preceding inequality and the fact that their images lie in $I$ give $c(s_2-s_1)\le|I|$. Its diameter, and therefore its Lebesgue measure, is at most $|I|/c$. The same assertion is trivial for infinite-length intervals. Write any open set as a countable disjoint union of open intervals; countable additivity then gives
$$
\operatorname{Leb}\{s\in[a^2,b^2]:\zeta(s)\in O\}\le c^{-1}\operatorname{Leb}(O).
$$
For a Borel set $A$ of finite Lebesgue measure, choose open supersets of measure arbitrarily close to $\operatorname{Leb}(A)$ by outer regularity and use the same inequality. If its measure is infinite the bound is automatic. Thus the Borel pushforward of $ds$ by $\zeta$ is dominated by $c^{-1}$ times Lebesgue measure on all Borel sets. This interval argument remains valid at jumps, at skipped target intervals, and for the actual point values of $y$.

Domination first for simple functions and then by monotone convergence permits integration of any nonnegative Borel function. Applying it to the unit-integral density in part 7, and changing variables only by the smooth map $s=r^2$, gives
$$
\begin{aligned}
\int_a^b k(r,x_r)\,dr
&\le(1+u^{-2})\int_{a^2}^{b^2}f_{\chi^2_{d+1}}(\zeta(s))\,ds\\
&\le\frac{1+u^{-2}}c
=\frac{1+u^{-2}}{1-4M_d/a^2}.
\end{aligned}
$$

**9. Lower-radius envelope.** Let $L=a^2-u^2\ge0$ and $\nu=d-1$. If $a=u$, then $L=0$. Otherwise
$$
a^2=\frac{2704d}{u^2}\le\frac d4,
\qquad 0\le L\le\frac d4\le d-3=\nu-2,
$$
where $u^2\ge10816=4\cdot2704$ and $d\ge4$ were used. Thus $0\le L\le\nu-2$ in both cases. Differentiating the explicit density in part 7 shows that $f_{\chi^2_\nu}(v)$ is increasing on $0<v\le\nu-2$, and it extends continuously by zero at $v=0$ because $\nu\ge3$.

The independent decomposition $R^2=Z_1^2+V$ gives, for $u<r\le a$ and $u\le x<r$, the exact conditional radial density
$$
k(r,x)=\frac{2r}{Q(x)}\int_x^r\phi(z)f_{\chi^2_\nu}(r^2-z^2)\,dz.
$$
Indeed, condition first on $Z_1=z\ge x$, use the $V$ density, and then use the Jacobian $d(r^2)=2r\,dr$. All arguments $r^2-z^2$ in this integral lie in $[0,r^2-u^2]\subseteq[0,L]$, entirely below the density mode. Therefore
$$
k(r,x)\le\frac{2r f_{\chi^2_\nu}(r^2-u^2)}{Q(x)}\int_x^r\phi(z)\,dz
\le2r f_{\chi^2_\nu}(r^2-u^2).
$$
For $r\le u$ and $x\ge u$, or for $x\ge r$, the kernel is zero. The bound consequently holds for the supremum over all cutoffs where relevant, and
$$
\int_0^a f_{\chi_d}(r)\sup_{x\ge u}\frac{H_r(x)}{Q(x)}\,dr
\le\int_u^a2r f_{\chi^2_\nu}(r^2-u^2)\,dr
=\mathbb P(V\le L).
$$
The supremum is measurable, since continuity in finite $x$ permits taking a countable dense set of cutoffs together with $u$. If $a=u$, the integral is zero.

If $a>u$, its defining strict inequality gives
$$
d>\frac{u^4}{2704}\ge4u^2,\qquad
L\le\frac d4\le\frac{d-1}{3}=\frac\nu3.
$$
Also $\nu>4u^2-1\ge15u^2/4$, since $u\ge104$. A direct Gaussian scaling integral gives $\mathbb Ee^{-Z_j^2}=3^{-1/2}$, so independence gives $\mathbb Ee^{-V}=3^{-\nu/2}$. Markov's inequality applied to $e^{-V}$ yields
$$
\mathbb P(V\le L)\le e^L3^{-\nu/2}
\le\exp\left\{-\frac\nu2(\log3-2/3)\right\}.
$$
For the numerical inequality, substituting $t=(z-1)/(z+1)$ in $\int_1^3 dz/z$ gives
$$
\log3=2\int_0^{1/2}\frac{dt}{1-t^2}
>2\int_0^{1/2}(1+t^2)\,dt=\frac{13}{12}>\frac{16}{15}.
$$
Thus $\log3-2/3>2/5$, and the lower-radius integral is at most
$$
e^{-\nu/5}\le e^{-3u^2/4}.
$$
This also bounds its zero value when $a=u$.

**10. Upper-radius probability.** Gaussian scaling gives $\mathbb Ee^{\lambda Z_j^2}=(1-2\lambda)^{-1/2}$ for $\lambda<1/2$. Independence therefore yields $\mathbb Ee^{\lambda R^2}=(1-2\lambda)^{-d/2}$. Since $b^2>d$, Markov's inequality at $\lambda=(1-d/b^2)/2\in(0,1/2)$ gives
$$
\mathbb P(R>b)\le\exp\left\{-\frac{b^2-d-d\log(b^2/d)}2\right\}.
$$
Put $z=2u/\sqrt d>0$, so $b=\sqrt d(1+z)$. The inequality $\log(1+z)=\int_0^z(1+t)^{-1}dt\le z$ gives
$$
b^2-d-d\log(b^2/d)
=d\{2z+z^2-2\log(1+z)\}\ge dz^2=4u^2.
$$
Consequently $\mathbb P(R>b)\le e^{-2u^2}$. In this region we use only FDP$\le1$, with no cutoff regularity assertion.

**11. Assembly and the exact stated inequality.** In the lower and core regions the contact formula is $q\pi_0H_r(x_r)/Q(x_r)$ at finite contacts and zero otherwise. Parts 8 and 9 bound its radial integral after multiplying their kernels by precisely $q\pi_0$. Part 10 bounds the upper region by its probability. The radius has a density, so interval endpoints do not matter. Therefore
$$
\operatorname{FDR}_{\mathrm{pop}}(q;W,d)
\le q\pi_0\left\{e^{-3u^2/4}+\frac{1+u^{-2}}{1-4M_d/a^2}\right\}+e^{-2u^2}.
$$
Put $t=u^{-2}\le104^{-2}$. Since $M_d<1$ and $a\ge u$, $4M_d/a^2\le4t<1$. For $0\le t\le1/24$,
$$
\frac{1+t}{1-4t}\le1+6t,
$$
because this is equivalent to $t(1-24t)\ge0$. With $s=u^2\ge4$, the elementary exponential bound $e^{3s/4}\ge(3s/4)^2/2=9s^2/32\ge s$ gives $e^{-3u^2/4}\le u^{-2}$. The braces are thus at most $1+7/u^2<2$. Since $M_d>0$ and $\log(3u)>0$, it follows in particular that
$$
\operatorname{FDR}_{\mathrm{pop}}(q;W,d)
\le q\pi_0\{2+4M_d(1+u^{-2})\log(3u)\}+e^{-2u^2},
$$
which is the exact frozen inequality. The stronger intermediate estimate is used only to prove it.

**12. Uniformity and dependency closure.** The Mills bound proved in part 5 gives
$$
q=2Q(u)\ge\frac{2\phi(u)}{u+u^{-1}},\qquad
\frac{e^{-2u^2}}q\le\frac{\sqrt{2\pi}}2(u+u^{-1})e^{-3u^2/2}\longrightarrow0.
$$
As $q\downarrow0$, its inverse relation gives $u\to\infty$. Using $M_d\le1$ and $\pi_0\le1$, the right side of the frozen inequality is uniformly $O(q\log u)$, and division by $qu$ tends to zero because $\log(3u)/u\to0$ and the displayed exponential ratio tends to zero. Every preceding derivation was for an arbitrary fixed $d\ge4$ and arbitrary Borel $W$, with final constants independent of either. Thus $d=d(q)$ and $W=W_q$ are allowed.

The factor of two in each component comes from the two folded directional boundaries. The null rejection mass is $2\pi_0H_r(x_r)$ and the contact mass is $2Q(x_r)/q$, whose ratio is exactly $q\pi_0H_r(x_r)/Q(x_r)$. The kernel is conditioned on the single Gaussian event $Z_1\ge x$ of probability $Q(x)$, so it has no additional factor of two; its Jacobian is $2r$. All specialized bounds, constants, selection and measure arguments have been established above from the two approved definitions and the displayed elementary calculations. No draft definition, theorem dependency, candidate audit, or unproved transport assertion is assumed. The ten unsuccessful search rounds supply no proof step. The proof concerns only the frozen isotropic continuous population with zero residual variance; it asserts nothing about arbitrary finite Gaussian arrays or nonuniform directions. $\square$
