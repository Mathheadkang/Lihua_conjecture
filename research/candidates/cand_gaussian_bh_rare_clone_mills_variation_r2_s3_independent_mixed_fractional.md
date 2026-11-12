---
type: candidate
title: Independent zero-null and alternative with actual fractional clone FDP
status: failed
target_asset: gaussian_bh_rare_clone_mills_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: idea_9604780f9209
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:05:18.154Z'
extension_version: 0.0.4
---

## Object

Set $N=2$, $q=1/4$, $\theta=(0,1)$, $\Sigma=I_2$, $G=(G_1,G_2)$ standard independent Gaussian, and $v_1=e_1,v_2=e_2$. Choose $i=1$. Thus $T_1=G_1$ is a true null, $T_2=1+G_2$ is an independent alternative, and the clone labels are $(\ell_1,\ell_2)=(1,0)$.

Use exactly the target offset law and midpoint quantiles, without modifying the minority law or its atom. Write
$$
U=S^{-1}(q),\quad u_1=S^{-1}(q/2),\quad
u(x)=S^{-1}(qx/2),\quad
L=2\{h(U)/U-1\},\quad \alpha=\varepsilon L,\quad \delta=\varepsilon/U.
$$
Take
$$
0<\varepsilon<\varepsilon_0:=\min\{1/(2L),\ U(u_1-U)/2\}.
$$
In particular $\alpha<1/2$ and $\delta<u_1-U$. This is a sufficiently small interval of parameters, not a new hypothesis on the target. All calculations below hold throughout this interval. This settles the concrete open test in idea_9604780f9209.

## Checks

### H1

The original model has the finite positive integer $N=2$.

### H2

The testing level $q=1/4$ belongs to $(0,1/2)$.

### H3

The means are the permitted fixed real vector $(0,1)$. Their actual one-sided null labels are exactly $(1,0)$, including the chosen coordinate at mean zero.

### H4

$\Sigma=I_2$ is positive definite and has unit diagonal.

### H5

The displayed representation has finite dimension two and unit directions with $v_j\cdot v_k=\Sigma_{jk}$. The Gaussian observations are exactly $G_1$ and $1+G_2$.

### H6

The chosen coordinate is $i=1\in[2]$, and only this coordinate receives the prescribed downward offsets. Every other coordinate is copied exactly $K$ times.

### H7

The parameters satisfy $\varepsilon L<1$. The extra restriction for a positive chosen mean is inapplicable because $\theta_i=0$. All data other than $K$ and $\varepsilon$ remain fixed in both limits.

### NOT

**Fail.** The actual finite-copy limit, its fractional FDP, and its derivative agree with the target, as follows. The normalization, labels and cost assertions also hold for this object.

#### Offset law and its quantile

Integration of $(\phi(v)/v)'=-\phi(v)-\phi(v)/v^2$ gives
$$
\int_U^\infty\frac{\phi(v)}{v^2}\,dv
=\frac{\phi(U)}U-q.
$$
Consequently the continuous part has mass $\alpha=\varepsilon L$, $L>0$ is finite, and the remaining mass $1-\alpha$ is at zero. The positive offset map $v\mapsto\varepsilon(1/U-1/v)$ is increasing from zero to $\delta$, never reaching $\delta$. It has no atoms, so there is no atom at the upper endpoint or additional atom at zero.

For $v\ge U$, put
$$
z(v)=\frac2q\{\phi(v)/v-S(v)\},\qquad D(v)=1/U-1/v.
$$
The offset CDF evaluated at $\varepsilon D(v)$ is $1-\varepsilon z(v)$. Here $z(U)=L$, $z(\infty)=0$, and $z'(v)=-(2/q)\phi(v)/v^2<0$. Therefore the left quantile $Q=Q_\varepsilon$ satisfies
$$
Q(c)=0\quad(0\le c\le1-\alpha),\qquad
Q(1-\varepsilon z(v))=\varepsilon D(v).
$$
In formulas involving the compact interval $[0,1]$, define only the endpoint extensions $Q(0)=0,Q(1)=\delta$. The extended $Q$ is continuous; $Q(1-\alpha)=0$ agrees with the required left-inverse convention. Every midpoint lies below one and hence has $0\le d_l<\delta$.

The finite clones have scores $T_1-d_l$ and $T_2$, so all variances remain one, all directions remain unchanged, and their actual means are respectively $-d_l\le0$ and $1>0$. Joint Gaussianity and the stated labels follow. At zero offset exact copying preserves the original BH rejection blocks for every $K$.

#### Actual finite-copy BH, before taking a limit

For $r=1,2$ define
$$
g_{r,K}(l)=u(r-1+l/K)+d_l,\qquad
\tau_{r,K}=\min_{1\le l\le K}g_{r,K}(l).
$$
For a null-score value $t$, let $c_K(t)=l_K(t)/K$, where $l_K(t)$ is the largest $l\in[K]$ satisfying $g_{2,K}(l)\le t$; leave $c_K$ undefined if there is no such $l$.

If the alternative score $b<U$, it cannot be rejected at any rank of the $2K$-coordinate BH procedure, since every BH score threshold is at least $U$. A null rejection exists exactly when $t\ge\tau_{1,K}$, and its FDP is exactly one, however many null clones are selected.

If $b\ge U$, any putative null-only rejection requires $t\ge u_1$. But then $t-d_K>U$ because $d_K<\delta<u_1-U$, so all $2K$ coordinates qualify at the terminal rank. Thus a nonzero null FDP in this regime always uses a joint crossing with the exact alternative block.

At a proposed joint rank $K+l$, the necessary and sufficient inequalities are
$$
t\ge g_{2,K}(l),\qquad b\ge u(1+l/K).
$$
These are the actual sorted-score BH inequalities, including ties. The alternative condition becomes weaker as $l$ increases. It follows that, if a joint rank with null discoveries exists, its largest rank is precisely $K+l_K(t)$, and it exists exactly when
$b\ge u(1+c_K(t))$. If this inequality fails at the largest unconstrained null rank, it fails at every smaller qualifying null rank. Its exact FDP is $c_K(t)/(1+c_K(t))$.

Independence now gives the following exact finite-$K$ identity, where the second integrand is zero when $c_K$ is undefined:
$$
F_{K,\varepsilon}
=\Phi(U-1)S(\tau_{1,K})
+\int_{\tau_{2,K}}^\infty
\phi(t)\frac{c_K(t)}{1+c_K(t)}
S\bigl(u(1+c_K(t))-1\bigr)\,dt. \tag{1}
$$
This computes the common largest BH rank; there is no independent optimization of the two possible FDP faces in (1).

#### Population limit and the fractional denominator

Set
$$
g_r(c)=u(r-1+c)+Q(c),\qquad
\tau_r=\inf_{0<c\le1}g_r(c).
$$
Both minima occur with $c\ge1-\alpha$. On $0<c\le1-\alpha$, $g_r$ decreases because $Q=0$. For $c=1-\varepsilon z(v)$ with $v>U$, differentiation gives
$$
g_r'(c)=\frac q2
\left\{\frac1{\phi(v)}-\frac1{\phi(u(r-1+c))}\right\}.
$$
Since $v$ increases strictly with $c$, whereas $u(r-1+c)$ decreases strictly, the derivative switches sign exactly once from negative to positive. Thus $g_r$ has a unique minimum and an increasing upper branch. In particular, for $t>\tau_2$, let $c_+(t)$ be the largest $c\in(0,1]$ with $g_2(c)\le t$. Then
$$
1-\alpha\le c_+(t)\le1,\qquad
c_+(t)=1\quad\hbox{if }t\ge U+\delta.
$$
The value at $t=\tau_2$ can be defined by its unique minimizer and is immaterial to expectation.

The quantile function is uniformly continuous on $[0,1]$. Hence
$$
\max_{1\le l\le K}|d_l-Q(l/K)|\longrightarrow0.
$$
The minima $\tau_{r,K}$ converge to $\tau_r$. For $r=1$, $g_1(c)\to\infty$ as $c\downarrow0$, so this minimum comparison takes place on a compact interval bounded away from zero. For $r=2$, $g_2(0)=u_1$ and $\tau_2\le U+\delta<u_1$, so its minimizing interval is likewise bounded away from zero. The continuous upper branch implies $c_K(t)\to c_+(t)$ for every $t>\tau_2$ except, harmlessly, its endpoint value; below $\tau_2$ no positive null joint crossing eventually exists. Approximating strictly interior points of the upper sublevel interval supplies the lower bound on the largest discrete rank, while uniform convergence supplies the upper bound. The tangency score $t=\tau_2$ has Gaussian probability zero.

All FDPs are bounded by one, so dominated convergence in (1) yields
$$
F_{\mathrm{pop},\varepsilon}
=\Phi(U-1)S(\tau_1)
+\int_{\tau_2}^\infty
\phi(t)\frac{c_+(t)}{1+c_+(t)}
S\bigl(u(1+c_+(t))-1\bigr)\,dt. \tag{2}
$$
This is also the expectation of the target's actual common-population-crossing FDP: for $b<U$ the largest positive rank is the largest null-only crossing and its FDP is one; for $b\ge U$ the largest joint crossing is $1+c_+(t)$ whenever $b\ge u(1+c_+(t))$, and otherwise it has no null rejection. A remaining alternative-only crossing has null FDP zero. The quantile condition $Q(c)\le t-u(r-1+c)$ is exactly the population qualifying-count condition.

For completeness, $H$ is nondecreasing and its supremal qualifying rank $\rho>0$ itself qualifies: take qualifying $x_n\to\rho$ from below and use $H(\rho)\ge H(x_n)\ge x_n$. If $H(\rho)>\rho$ and $\rho<2$, monotonicity would make a slightly larger rank qualify, a contradiction. At $\rho=2$, $H\le2$ gives equality too. Thus $H(\rho)=\rho$ and the actual FDP denominator is $\rho$. In particular, null-only fractional ranks below one have FDP $\rho/\rho=1$, rather than $\rho/(\rho\vee1)$; joint fractional ranks have FDP $c/(1+c)$, rather than $1/2$. The terminal crossing $\rho=2$ is present whenever $b\ge U$ and $t\ge U+\delta$.

#### Expansion with the mixed fractional FDP retained

Write $u_2=U$ and $A_r=q/(2\phi(u_r))$. Uniformly over $v\in[U,\infty]$, boundedness of $z(v)$ and a Taylor expansion of $u$ near the fixed rank $r$ give
$$
g_r(1-\varepsilon z(v))
=u_r+\varepsilon\{A_r z(v)+D(v)\}+O(\varepsilon^2).
$$
The minimum is in this interval, so the remainder remains uniform under minimization. Moreover
$$
\frac d{dv}\{A_rz(v)+D(v)\}
=\frac{1-\phi(v)/\phi(u_r)}{v^2}.
$$
The minimum is therefore at $v=u_r$ (the endpoint $v=U$ when $r=2$), with value
$$
\beta_r=1/U-m(u_r).
$$
It follows that $\tau_r=u_r+\varepsilon\beta_r+O(\varepsilon^2)$.

Equation (2) still has the actual mixed fractional FDP. To estimate its effect, put $c=c_+(t)$. Its deviation from the full-group factor satisfies
$$
\left|\frac c{1+c}-\frac12\right|
\le\frac{\alpha}{2(2-\alpha)},\qquad
0\le u(1+c)-U\le u(2-\alpha)-U=O(\alpha).
$$
Since $S$ has bounded derivative, the whole product
$[c/(1+c)]S(u(1+c)-1)$ differs from $S(U-1)/2$ by $O(\alpha)$, uniformly. The difference vanishes for $t\ge U+\delta$. Also $U\le\tau_2\le U+\delta$. Integration against the bounded density over $[\tau_2,U+\delta]$ therefore gives an $O(\alpha\delta)=O(\varepsilon^2)$ error. This includes the alternative atom's clipping condition, through the exact factor $S(u(1+c)-1)$; it has not been omitted or inferred merely from the face coefficients. Consequently
$$
F_{\mathrm{pop},\varepsilon}
=\Phi(U-1)S(\tau_1)
+\tfrac12S(U-1)S(\tau_2)+O(\varepsilon^2).
$$
At zero offset this gives the original FDR
$$
F=\Phi(U-1)S(u_1)+\tfrac12S(U-1)S(U)=q/2.
$$
Thus the iterated derivative, with $K\to\infty$ taken first as required, is
$$
-\beta_1\phi(u_1)\Phi(U-1)
-\tfrac12\beta_2\phi(U)S(U-1). \tag{3}
$$
The original face jumps are $\Delta_{1,1}=\mathbf1_{\{T_2<U\}}$ and $\Delta_{1,2}=\tfrac12\mathbf1_{\{T_2>U\}}$ outside the zero-probability alternative boundary. These follow directly by taking the ordinary largest original BH rank on both sides: at $u_1$ a lone null rejection is born only when the alternative is below $U$; at $U$ the selected null joins a qualifying two-group rank only when the alternative is above $U$. Hence
$$
\mu_{1,1}(E_1)=\phi(u_1)\Phi(U-1),\qquad
\mu_{1,2}(E_1)=\tfrac12\phi(U)S(U-1),
$$
so (3) is precisely the proposed signed-face formula. Numerically $U\simeq0.6744897502$, $u_1\simeq1.1503493804$, $L\simeq1.7690900132$, and the derivative is approximately $-0.1364984497$.

#### Parameter costs

Only the first of two distinct unit directions is shifted, so the continuous measure loses exactly $\alpha/2$ mass from the original first-group parameter. Thus $d_{\mathrm{TV}}(\pi_\varepsilon,\pi)=\alpha/2=\varepsilon\{h(U)/U-1\}$. For the midpoint array, if $n_+$ offsets are positive, the midpoint counting error gives $n_+/K\le\alpha+1/K$, and therefore
$$
d_{\mathrm{TV}}(\pi_{K,\varepsilon},\pi)=n_+/(2K)
\le\alpha/2+1/(2K).
$$
Coupling every clone parameter to its original parameter moves only that shifted mass by a mean distance at most $\delta$ and leaves directions and labels fixed. Both claimed $W_1$ bounds follow by multiplying these respective bounds by $\delta=\varepsilon/U$. Together with the normalization and labels above, all four target conclusions hold in this concrete family.

## Failure

NOT fails: the independent two-coordinate mixed-label object has the actual finite-copy limit and signed derivative asserted by the target, with its mixed fractional FDP and alternative-atom clipping contributing only $O(\varepsilon^2)$ beyond the two face shifts.
