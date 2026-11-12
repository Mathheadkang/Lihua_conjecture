---
type: candidate
title: Coalescing actual-rank band controlled by its posterior mass
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
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:09:57.508Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$, set
$$
U=\overline\Phi^{-1}(q),\qquad A=\overline\Phi^{-1}(q/2),\qquad
0<\delta<1/A,\qquad c=A-U+\delta,\qquad T=A+\delta.
$$
Take $N=2$, $d=1$, $v_1=v_2=1$, and $\theta=(0,-c)$, so the two statistics are $Y$ and $Y-c$ for $Y\sim N(0,1)$. The entire displayed range of $\delta$ is checked, including arbitrary dependence on $q$ and $\delta\downarrow0$.

This examines the previously uncovered coalescing-cutoff boundary. The board's separated-cutoff calculation requires $c\ge A-U+1/A$, whereas here $c<A-U+1/A$. Its estimate by $\Delta\phi(T)$ loses the probability of the shrinking rank-one band and therefore does not by itself control the ratio when $\delta\downarrow0$. The calculation below retains the square root of that probability, using a centered posterior and entropy. This is the new failure mechanism, rather than a reapplication of the separated-cutoff obstruction.

## Checks

### H1

The testing level is positive and at most $\overline\Phi(3)$, so $U\ge3$. This is a family for arbitrarily small $q$, as required for testing a uniform small-level assertion.

### H2

The dimensions $N=2,d=1$ are positive integers and $\theta=(0,-c)\in\mathbb R^2$, with $c>0$.

### H3

Both vectors have unit norm. The covariance matrix is
$$
\Sigma=\begin{pmatrix}1&1\\1&1\end{pmatrix},
$$
which is positive semidefinite with unit diagonal. The statistics are exactly jointly Gaussian; the singular covariance is permitted.

### H4

Both coordinates are true nulls because their means are nonpositive. The p-values are exactly $\overline\Phi(Y)$ and $\overline\Phi(Y-c)$. The largest-rank BH rule gives
$$
R(Y)=\begin{cases}
0,&Y<A,\\
1,&A\le Y<T,\\
2,&Y\ge T.
\end{cases}
$$
Indeed, rank two qualifies precisely when the smaller statistic $Y-c$ is at least $U$, equivalently $Y\ge U+c=T$. Below $T$, only the first coordinate can qualify at rank one, precisely when $Y\ge A$. Equality points obey the displayed non-strict convention and have Gaussian probability zero.

### H5

Consequently
$$
f(Y)=\mathbf1_{\{Y\ge A\}},\qquad F=q/2>0,\qquad
D=\log(2/q).
$$
The terminal and path tilts are precisely the prescribed tilts by this $f/F$. Put
$$
b_2=1/H,\quad b_1=1/h(A),\quad\Delta=b_2-b_1>0,\quad
r=Hb_1\in(0,1),\quad E=[A,T),\quad p=Q(E)\in(0,1).
$$
The actual Mills field is $B=fb$, where $b=b_1$ on $E$ and $b=b_2$ on $[T,\infty)$. The strict inequalities for $\Delta,r$ follow from the strict increase of the Gaussian Mills ratio on positive arguments. Under the required path tilt let
$$
\rho_t=\mathbb Q(Y\in E\mid\mathcal F_t),\qquad
\pi_t=1-\rho_t=\mathbb Q(Y\ge T\mid\mathcal F_t).
$$
The prescribed field is exactly $a_t=b_2-\Delta\rho_t=b_1+\Delta\pi_t$; no modified rejection field is used.

### NOT

**Fail:** every well-posedness assertion holds in this family, and its positive trace satisfies $M_+\le q\sqrt{1-x}$ uniformly, including the coalescing boundary $\delta\downarrow0$.

Here are the integrability and identity checks before using the trace estimate. Write $\mathcal H(t,z)=\overline\Phi((A-z)/\sqrt{1-t})$. Its drift $\beta=\partial_z\log\mathcal H$ is positive. The density martingale $\mathcal H(t,W_t)/F$ is bounded by $1/F$. Applying Itô's formula to its entropy, first with stopping and then by bounded-density entropy convergence, gives
$$
\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt=2D<\infty.
$$
Equivalently, the usual change of measure yields $dW_t=d\widetilde W_t+\beta_tdt$ under $\mathbb Q$ on every compact time interval. Both statements can be derived with stopping before $\mathcal H$ approaches zero; the bound on the density and its finite terminal entropy remove the stops. Since $0<a_t\le1/H$, Cauchy--Schwarz gives absolute integrability of $a_t\beta_t$. Also $|YB(Y)|\le |Y|/H$, giving absolute endpoint integrability.

For $s=1-t$, differentiation of the conditional Gaussian kernel gives
$$
\partial_z\pi(t,z)=\frac{\pi(t,z)(1-\pi(t,z))}{s}
\left(\mathbb E[Y\mid Y\ge T,W_t=z]-\mathbb E[Y\mid A\le Y<T,W_t=z]\right)>0.
$$
Conditional expectations here use the Gaussian kernel with mean $z$ and variance $s$, restricted as displayed. Thus $K_t=\Delta\partial_z\pi(t,W_t)\ge0$. The bounded conditional-expectation martingale $a_t=\mathbb E_{\mathbb Q}[b(Y)\mid\mathcal F_t]$ satisfies $da_t=K_t\,d\widetilde W_t$. Product Itô, followed by expectation, gives for every $\tau<1$
$$
F\mathbb E_{\mathbb Q}\int_0^\tau K_tdt
=F\mathbb E_{\mathbb Q}[W_\tau a_\tau]
-F\mathbb E_{\mathbb Q}\int_0^\tau a_t\beta_tdt
=\tau\mathbb E[YB(Y)]-F\mathbb E_{\mathbb Q}\int_0^\tau a_t\beta_tdt.
$$
The last equality follows because the tilt depends only on $Y=W_1$, leaving the Brownian bridge conditional on $Y$ unchanged. On compact time intervals the product identity is justified by stopping; boundedness of $a$, the Gaussian moments under a bounded density, and the smooth heat fields remove those stops. Since $K_t,a_t,\beta_t$ are nonnegative, the last display is bounded above by $\mathbb E[YB(Y)]$. Monotone convergence proves absolute trace integrability. Passing to the limit proves the exact required endpoint identity and signed heat-trace identity, rather than assuming them.

Conditional Jensen and $\mathbb E_{\mathbb Q}\rho_t=p$ now give
$$
0\le x=H^2\int_0^1\mathbb E_{\mathbb Q}a_t^2dt
\le H^2\mathbb E_Q b(Y)^2=1-p(1-r^2)<1.
$$
To estimate the trace while retaining the vanishing band mass, center the endpoint identity at the larger constant $b_2$. The drift identity $\mathbb E_QY=\mathbb E_{\mathbb Q}\int_0^1\beta_tdt$ follows from the displayed change of measure and its finite energy. Therefore
$$
M=-F\Delta\mathbb E_Q[Y\mathbf1_E]
+F\Delta\mathbb E_{\mathbb Q}\int_0^1\rho_t\beta_tdt
\le F\Delta\sqrt{2Dp},
$$
because $Y\ge A>0$ on $E$ and $\int_0^1\mathbb E\rho_t^2dt\le p$. As $M\ge0$ already,
$$
\frac{M_+}{q\sqrt{1-x}}
\le\frac{F}{q}\frac{\Delta\sqrt{2D}}{\sqrt{1-r^2}}
=\frac{\sqrt{2D}}{2H}\sqrt{\frac{1-r}{1+r}}.
$$
Finally $H\ge U$ and the elementary Mills lower bound $q\ge\phi(U)U/(U^2+1)$ imply
$$
D\le U^2/2+\log\!\left(2\sqrt{2\pi}(U+U^{-1})\right)\le U^2\qquad(U\ge3).
$$
For the last inequality, it holds directly at $U=3$, and the derivative of the logarithm is less than $1/U$, while the derivative of $U^2/2$ is $U$. Hence the ratio is at most $1/\sqrt2<1$. The square-root term alone controls this near-equality family; the entropy-linear term need not be used. All constants are independent of $q,\delta,c$.

## Failure

NOT fails: centering at the upper terminal Mills mark retains a square root of the thin rank-one band's tilted probability, which also appears in the coherence deficit, so the positive trace obeys $M_+\le q\sqrt{1-x}$ even as the band collapses.
