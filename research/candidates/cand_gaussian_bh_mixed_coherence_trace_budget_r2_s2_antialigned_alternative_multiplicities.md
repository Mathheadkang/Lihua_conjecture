---
type: candidate
title: >-
  Arbitrary null and antialigned alternative multiplicities have nonpositive
  Mills trace
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
round: 2
slot: 2
direction: extremal
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:04:05.474Z'
extension_version: 0.0.4
---

## Object

Let $0<q\le\overline\Phi(3)$ and choose arbitrary positive integers $m,k$ and a real $\mu>2U$, where $U=\overline\Phi^{-1}(q)$. Set $N=m+k$, $d=1$, and
$$
(\theta_i,v_i)=\begin{cases}(0,1),&1\le i\le m,\\(\mu,-1),&m<i\le N.\end{cases}
$$
Thus there are $m$ identical true nulls and $k$ identical false nulls, the latter perfectly anticorrelated with the former. Both multiplicities and $\mu$ may depend arbitrarily on $q$.

Put
$$
w=\frac mN,\qquad A=\overline\Phi^{-1}(qw)>U,\qquad T=\mu-U>U,\qquad L=\max(A,T),
$$
$$
b=\frac1{h(U)},\qquad c=\frac1{h(A)}<b.
$$
The proposed extremal mechanism is to use a large alternative block and its loss at a tail boundary to change the FDP tilt and the Mills ratio abruptly. This is not the constant-terminal-ratio family on the board: both posterior components below have positive Gaussian measure and their ratios $b$ and $c$ differ.

## Checks

### H1

The levels lie in the required small-level range, with $U\ge3$. The calculation below works throughout $0<q\le\overline\Phi(3)$, hence for every smaller proposed universal $q_0$. It imposes no uniform bound on $m,k$ or $\mu$.

### H2

The dimension and number of hypotheses are finite positive integers. Every $v_i$ has norm one. The covariance matrix is the Gram matrix of the displayed vectors, hence is positive semidefinite with diagonal one. Its rank is one. With $G\sim N(0,1)$, the observations are exactly $G$ on the null block and $\mu-G$ on the alternative block.

### H3

Because $\mu>0$, the true-null set is exactly $I_0=\{1,\ldots,m\}$. The one-sided p-values are $\overline\Phi(z)$ on this block and $\overline\Phi(\mu-z)$ on the alternative block. Negative correlations do not alter these labels or p-value definitions.

### H4

Apply ordinary BH with the largest qualifying rank, retaining both multiplicities. Both blocks are rejected exactly when both p-values are at most $q$, namely on
$$
E=[U,T].
$$
There $R=N$, $V=m$, $f=w$, and $B=wb$.

Outside $E$, true nulls are rejected exactly when $z\ge A$. To verify both directions, a null-only rejection must have $R=m$ and its qualifying endpoint requires $\overline\Phi(z)\le qm/N$. Conversely, if $z\ge A$ outside $E$, then $z\ge U$ and the alternative p-value exceeds $q$: otherwise both blocks would pass rank $N$. Thus the null block qualifies at rank $m$ and no alternative is rejected. This null-only region agrees, up to endpoints of measure zero, with
$$
J=(L,\infty).
$$
There $R=V=m$, $f=1$ and $B=c$. On the remaining region $V=0$, regardless of whether the alternative block alone is rejected. Consequently the actual largest-rank procedure gives
$$
f=w\mathbf1_E+\mathbf1_J,\qquad B=wb\mathbf1_E+c\mathbf1_J.
$$
If $T<A$, the interval $(T,A)$ has no true-null rejection. This gap is retained rather than filled by a relaxed rank rule.

### H5

Write $p_E=\Phi(T)-\Phi(U)>0$ and $p_J=\overline\Phi(L)>0$. Then
$$
F=wp_E+p_J>0.
$$
Use exactly the target's terminal and path tilts and heat fields. Their scalar terminal ratio is $b$ on $E$ and $c$ on $J$. All ingredients therefore exist with the prescribed conventions.

### NOT

This check fails: every well-posedness assertion holds, and the signed trace is strictly negative, so the proposed estimate holds with any positive $C$.

Here are the finiteness and identity details, included so the endpoint formula is not assumed. For $t<1$, $s=1-t$, and a current spatial value $z$, let $\nu_{t,z}$ be the conditional terminal measure with density proportional to
$$
\bigl(w\mathbf1_E(y)+\mathbf1_J(y)\bigr)\phi_s(y-z),
$$
where $\phi_s$ is the centered Gaussian density of variance $s$. If $\pi(t,z)=\nu_{t,z}(E)$, then
$$
a(t,z)=c+(b-c)\pi(t,z),\qquad c\le a(t,z)\le b=H^{-1}.
$$
Differentiation under the finite Gaussian integrals gives
$$
\partial_z\pi(t,z)=\frac1s\operatorname{Cov}_{\nu_{t,z}}(\mathbf1_E,Y)
=\frac{\pi(1-\pi)}s\bigl(\mathbb E[Y\mid E]-\mathbb E[Y\mid J]\bigr)<0.
$$
Indeed $E\subset(-\infty,T]$, $J\subset(L,\infty)$ and $L\ge T$, and both conditional components have positive mass. Hence
$$
K(t,z)=\partial_za(t,z)<0
$$
for every $t<1,z$. Also $0\le x\le H^2b^2=1$.

The entropy has the finite explicit expression
$$
D=\frac{wp_E}{F}\log\frac wF+\frac{p_J}{F}\log\frac1F.
$$
Its nonnegativity follows from relative entropy, and $D\le\log(1/F)$ follows from $0\le f\le1$.

For completeness, set $Z_t=\mathcal H(t,W_t)/F$ under Wiener measure. This is a positive martingale for $t<1$, bounded above by $1/F$, with terminal value $f(W_1)/F$. Applying Itô's formula to $Z_t\log Z_t$, first with localization away from zero, gives
$$
\frac12\mathbb E_{\mathbb Q}\int_0^\tau|\beta_t|^2\,dt
=\mathbb E_{\mathbb P}[Z_\tau\log Z_\tau],\qquad \tau<1.
$$
Localization is removed by the bounded density and the lower bound $z\log z\ge-e^{-1}$. As $\tau\uparrow1$, bounded convergence on the compact interval $[0,1/F]$ gives the terminal entropy. Thus
$$
\mathbb E_{\mathbb Q}\int_0^1|\beta_t|^2dt=2D<\infty,
\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\beta_t|dt\le b\sqrt{2D}<\infty.
$$
The endpoint integral $J_0=\int zB(z)\gamma_1(dz)$ is finite because $|B|\le b$; explicitly
$$
J_0=wb\{\phi(U)-\phi(T)\}+c\phi(L).
$$
For each fixed $t<1$, write $\mathcal L=P_{1-t}B$. Gaussian convolution and integration give
$$
\mathbb E_{\mathbb P}[\partial_z\mathcal L(t,W_t)]=J_0.
$$
For example $B$ is a finite linear combination of interval indicators, so this identity follows directly from their endpoint Gaussian densities; its expectation is convolution with total variance one. Differentiating $a=\mathcal L/\mathcal H$ now gives, without using any endpoint trace identity,
$$
F\mathbb E_{\mathbb Q}K_t
=\mathbb E_{\mathbb P}[\partial_z\mathcal L(t,W_t)]
-F\mathbb E_{\mathbb Q}[a_t\beta_t]
=J_0-F\mathbb E_{\mathbb Q}[a_t\beta_t].
$$
Every term is integrable on each truncated time interval. Since $K_t<0$, integration to $\tau<1$ gives
$$
F\mathbb E_{\mathbb Q}\int_0^\tau|K_t|dt
=-\tau J_0+F\mathbb E_{\mathbb Q}\int_0^\tau a_t\beta_tdt
\le |J_0|+Fb\sqrt{2D}.
$$
Monotone convergence proves absolute trace integrability on $[0,1)$. The preceding identity and absolute integrability of the drift then prove
$$
\lim_{\tau\uparrow1}M_\tau
=F\mathbb E_{\mathbb Q}\int_0^1K_tdt
=J_0-F\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt.
$$
Thus both representations of $M$ agree as required. Strict negativity of $K_t$ implies $M<0$ and hence $M_+=0$. The full mixed budget follows uniformly, with no restriction on the extremal multiplicities or their rates of growth.

## Failure

NOT fails: the antialigned positive-mean alternative block puts the larger terminal Mills ratio on the lower rejection component, making the heat posterior nonincreasing and the signed trace nonpositive for all multiplicities.
