---
type: candidate
title: >-
  Three equilateral null directions have a rank-cutoff deficit absorbing
  positive trace
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 5
slot: 2
direction: small_cases
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:31:02.996Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$ take $N=3$, $d=2$, $\theta=(0,0,0)$ and
$$
v_1=(1,0),\qquad v_2=(-1/2,\sqrt3/2),\qquad v_3=(-1/2,-\sqrt3/2).
$$
Write $T_i=v_i\cdot G$, $A=\overline\Phi^{-1}(q/3)$, $J=\overline\Phi^{-1}(2q/3)$, $U=\overline\Phi^{-1}(q)$, $h_1=h(A)$, $h_2=h(J)$, $H=h(U)$ and $c=1/h_1$.

This is a different geometric family from common-direction nulls, the orthogonal pair, and the antipodal pair. It has three distinct true-null directions, a genuine rank-two rejection region, and cancellation within each rank-two vector mark.

## Checks

### H1

The level belongs to the displayed full small-level range. In particular $U\ge3$, and $N,d$ are positive finite integers. The calculations below are uniform over this range, so cover every sequence $q\downarrow0$ in this family.

### H2

Every $v_i$ has norm one. Their Gram matrix has diagonal one and off-diagonal entries $-1/2$, and is positive semidefinite because it is a Gram matrix. It has rank two. The statistics are jointly Gaussian by their displayed linear representation, and all three means are zero true nulls.

### H3

Use $p_i=\overline\Phi(T_i)$ and the ordinary largest-rank BH rule with multiplicities and non-strict inequalities. Since $T_1+T_2+T_3=0$ and $U>0$, rank three is impossible. Its exact positive-rank regions are
$$
E_{ij}=\{T_i\ge J,T_j\ge J\}\quad(i<j),\qquad
E_i=\{T_i\ge A\}\setminus\bigcup_{j<k}E_{jk}.
$$
The $E_{ij}$ are pairwise disjoint: overlap would force all three statistics to be positive. On $E_{ij}$ the actual rank is two; the third statistic is at most $-2J<0$. On $E_i$ it is one, and two different $E_i$ cannot overlap because $A>J$. Outside these cells it is zero. Thus the cells give the actual BH rule, rather than a prescribed rank surrogate. On these cells,
$$
f=1,\qquad b=B/f=
\begin{cases}
v_i/h_1,&E_i,\\
(v_i+v_j)/(2h_2)=-v_k/(2h_2),&E_{ij},\quad\{i,j,k\}=\{1,2,3\}.
\end{cases}
$$
All boundaries have Gaussian measure zero; the specified non-strict rule handles them without changing the integrals.

### H4

Let $E$ be the union of these cells. Then $f=\mathbf1_E$. Each $E_i$ contains a nonempty open neighborhood of $t v_i$ for a sufficiently large $t$, so $F=\gamma_2(E)>0$. Every positive-rank outcome has some $T_i\ge J$, and each $T_i$ is standard normal. Consequently
$$
0<F\le\sum_{i=1}^3\mathbb P(T_i\ge J)=2q<1,\qquad D=\log(1/F)<\infty.
$$
The tilt is exactly the target's indicator-event tilt; no label-selected or separately conditioned law is substituted.

### H5

This check establishes all well-posedness and endpoint assertions before estimating the budget. First, the terminal mark is uniformly bounded by $c$. To see this without a numerical approximation, the normal hazard obeys
$$
0<h'(u)=h(u)(h(u)-u)<1.
$$
The upper bound follows from the positive variance $1+u h(u)-h(u)^2$ of a standard normal conditioned to exceed $u$. Also $h(u)>u$ for $u>0$. Since
$$
\log3=\int_U^A h(s)\,ds\ge H(A-U),
$$
we get
$$
h_1\le H+(A-U)\le H+\frac{\log3}{H}<2H\le2h_2,
$$
where $H\ge U\ge3$. Hence both types of terminal marks have norm at most $c$, and $c<1/H$.

For completeness the needed path identities can be obtained directly for this event. Let $L_t=\mathcal H(t,W_t)/F$. On every $t<1$ it is a strictly positive density martingale, bounded above by $1/F$. Localized Ito calculus for $L_t\log L_t$, followed by bounded convergence of this continuous bounded function on $[0,1/F]$, gives
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt=2D.
$$
Indeed $L_t\to\mathbf1_E(W_1)/F$ almost surely, so its entropy tends to $\log(1/F)$. Localized Girsanov and the finite displayed energy give a Brownian motion under $\mathbb Q$,
$$
Z_t=W_t-\int_0^t\beta_s\,ds.
$$
Bayes' formula identifies $a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]$. Differentiating the heat-quotient equation and applying Ito under this same tilt yields $da_t=K_t\,dZ_t$. The bounded vector martingale converges in $L^2$ to $b(W_1)$, so
$$
\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\mathrm{HS}}^2dt
=\mathbb E_Q\|b\|^2-\|a_0\|^2\le c^2.
$$
Therefore, in dimension two,
$$
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt\le\sqrt2 c,
\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\cdot\beta_t|dt\le c\sqrt{2D},
\qquad 0\le x\le H^2c^2<1.
$$
The endpoint integral is finite because $B$ is bounded and Gaussian first moments are finite. Apply the product rule to $a_t\cdot W_t$, first with stopping and then removing the stopping:
$$
F\mathbb E_{\mathbb Q}[a_\tau\cdot W_\tau]
=F\mathbb E_{\mathbb Q}\int_0^\tau
\{a_t\cdot\beta_t+\operatorname{tr}K_t\}\,dt.
$$
Removal is justified by the two absolute-integral estimates and $\mathbb E_{\mathbb Q}\sup_t\|W_t\|^2<\infty$, the latter following from the bounded terminal density $\mathbf1_E/F$. As $\tau\uparrow1$, boundedness and $L^2$ convergence of $a_\tau$, together with $L^2(\mathbb Q)$ convergence of $W_\tau$, give
$$
\int z\cdot B(z)\,d\gamma_2
=F\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt
+F\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt.
$$
Absolute trace integrability proves the cutoff limit equals the final trace integral, establishing exactly the required endpoint identification. These arguments prove rather than assume the representations used below.

### NOT

This check fails: a universal square-root budget already holds throughout the displayed family. The trace-energy estimate and $F\le2q$ give
$$
M_+\le |M|\le\sqrt2 F c\le\frac{2\sqrt2 q}{h_1}.
$$
There is a uniform rank-cutoff deficit. Here is an elementary explicit hazard bound to quantify it. Set $r(u)=\overline\Phi(u)/\phi(u)$ and $g(u)=(u^2+2)/(u^3+3u)$ for $u>0$. Since $r'=ur-1$ and
$$
g'-ug+1=-\frac6{u^2(u^2+3)^2}<0,
$$
integration after multiplication by $e^{-u^2/2}$, using the zero limit at infinity, gives $g(u)-r(u)>0$. Thus
$$
h(u)>u+\frac{u}{u^2+2},\qquad
h'(u)>\frac{u^2}{u^2+2}\ge\frac9{11}\quad(u\ge3).
$$
Using $d[-\log\overline\Phi(u)]=h(u)du$, this implies
$$
h_1^2-H^2
=\int_U^A2h(u)h'(u)du
\ge\frac{18}{11}\log3=:c_0.
$$
Since $x\le H^2/h_1^2$,
$$
1-x\ge\frac{c_0}{h_1^2},\qquad
M_+\le\frac{2\sqrt2}{\sqrt{c_0}}q\sqrt{1-x}
\le3q\sqrt{1-x}.
$$
The final numerical inequality follows already from $\log3>1$. Adding the nonnegative entropy-linear term preserves the target bound with $C=3$. This checks only the fixed equilateral three-null family; it gives no uniform result for arbitrary numbers or geometries of directions.

## Failure

NOT fails: cancellation in the rank-two marks and the rank-one cutoff's $\log3$ hazard gap force enough coherence deficit to absorb the dimension-two trace energy uniformly.
