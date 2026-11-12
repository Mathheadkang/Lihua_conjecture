---
type: candidate
title: Three coalescing actual-rank bands with unequal conservative null means
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
round: 4
slot: 1
direction: boundary_degenerate
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:20:56.688Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$ and every finite $\delta>0$, put
$$
A=\overline\Phi^{-1}(q/3),\qquad C=\overline\Phi^{-1}(2q/3),\qquad U=\overline\Phi^{-1}(q),\qquad H=h(U).
$$
Take $N=3,d=1$, $v_1=v_2=v_3=1$, and
$$
\theta_1=0,\qquad \theta_2=-(A-C+\delta),\qquad \theta_3=-(A-U+2\delta).
$$
The scalar latent variable $Z$ is standard normal. The three actual-rank thresholds are $A,A+\delta,A+2\delta$. The regime $\delta\downarrow0$, arbitrarily fast as $q\downarrow0$, tests degeneracy of two simultaneous rank bands.

This is outside the board's checked two-terminal-mark family: it has three distinct terminal Mills marks, and both interior rank intervals have positive Gaussian mass for every $\delta>0$. The calculation below does not replace them by a two-mark approximation.

## Checks

### H1

The level satisfies $0<q\le\overline\Phi(3)$, so $A>C>U\ge3$. Every parameter is finite. No relation between $q$ and $\delta$ is imposed.

### H2

The dimensions are positive integers, all observation vectors have norm one, and the covariance matrix is the positive-semidefinite all-ones matrix. Singular covariance is permitted. The displayed three means are real and nonpositive, with $0>\theta_2>\theta_3$.

### H3

Use precisely $p_i(z)=\overline\Phi(\theta_i+z)$. All three indices are true nulls under the target's nonpositive-mean convention. Thus the actual FDP is one whenever BH rejects, and zero otherwise.

### H4

The statistics are ordered $T_1>T_2>T_3$. The qualifying inequalities for ranks one, two and three are, respectively,
$$
z\ge A,\qquad z\ge A+\delta,\qquad z\ge A+2\delta.
$$
Consequently the largest qualifying rank, with the target's non-strict convention, is
$$
R(z)=\begin{cases}
0,&z<A,\\
1,&A\le z<A+\delta,\\
2,&A+\delta\le z<A+2\delta,\\
3,&z\ge A+2\delta.
\end{cases}
$$
There are exactly $R$ p-values below its threshold, including at each boundary. Hence
$$
f(z)=\mathbf1_{[A,\infty)}(z),\quad F=q/3,
$$
$$
B(z)=f(z)b(z),\qquad
b(z)=\begin{cases}
1/h(A),&A\le z<A+\delta,\\
1/h(C),&A+\delta\le z<A+2\delta,\\
1/H,&z\ge A+2\delta,
\end{cases}
$$
with $b=0$ off the FDP support. These are the actual BH fields; no ranks or multiplicities are suppressed.

### H5

Since $F=q/3>0$, every tilt in the statement is required. Let $\mathbb Q$ be Wiener measure conditioned on $W_1\ge A$, and let $Q$ be its terminal law. Then
$$
D=\log(3/q)<\infty,\qquad
\mathcal H(t,z)=\overline\Phi\left(\frac{A-z}{\sqrt{1-t}}\right),
$$
$$
a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t],\qquad
0\le a_t\le 1/H.
$$
These are exactly the target's ratios of heat convolutions. In particular $0\le x\le1$ and $D=\log(1/F)$.

For completeness, verify the well-posedness conclusions before using the trace representation. The usual entropy identity can here be obtained directly from the bounded density martingale $L_t=\mathcal H(t,W_t)/F$: apply Itô's formula to $L_t\log L_t$ with stopping away from zero, then remove the stopping and let $t\uparrow1$. Since $0\le L_t\le1/F$ and $L_t\to\mathbf1_{[A,\infty)}(W_1)/F$, bounded convergence for $L_t\log L_t$ gives
$$
\mathbb E_{\mathbb Q}\int_0^1\beta_t^2\,dt=2D.
$$
The same localization gives the innovation Brownian motion $\widetilde W_t=W_t-\int_0^t\beta_sds$ under $\mathbb Q$. Smoothness at every $t<1$ and the heat quotient equation imply
$$
da_t=K_t\,d\widetilde W_t.
$$
The bounded conditional-expectation martingale $a_t$ converges in $L^2$ to $b(W_1)$. Its quadratic-variation identity therefore gives
$$
\mathbb E_{\mathbb Q}\int_0^1 K_t^2dt
=\mathbb E_Q b^2-a_0^2\le H^{-2}.
$$
It follows that
$$
\mathbb E_{\mathbb Q}\int_0^1|K_t|dt\le H^{-1},\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\beta_t|dt\le H^{-1}\sqrt{2D}.
$$
The endpoint $\int zB(z)d\gamma_1(z)$ is absolutely finite because $|B|\le1/H$. To establish the endpoint identity, apply the product formula to $W_ta_t$ under $\mathbb Q$, obtaining, first with localization and then without it,
$$
\mathbb E_{\mathbb Q}[W_\tau a_\tau]
=\mathbb E_{\mathbb Q}\int_0^\tau(a_t\beta_t+K_t)dt.
$$
The martingale terms have expectation zero. One justification on the full interval is $\mathbb E_{\mathbb Q}\sup_{t\le1}|W_t|^2<\infty$, which follows from the bounded terminal density $f/F$, together with the displayed finite $K$ energy and the martingale maximal inequality. These give integrability of the stochastic product terms by Cauchy--Schwarz and the Burkholder--Davis--Gundy inequality. Also $a_\tau\to b(W_1)$ in $L^2$, and $W_\tau\to W_1$ in $L^2(\mathbb Q)$. Absolute integrability of the two drift terms permits passage to $\tau\uparrow1$. Multiplying by $F$ proves all stated identifications:
$$
\lim_{\tau\uparrow1}M_\tau
=F\mathbb E_{\mathbb Q}\int_0^1K_tdt
=\int zB(z)d\gamma_1(z)-F\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt=M_*.
$$
Thus no finiteness or endpoint identity is being assumed in the following calculation.

### NOT

Fail: the proposed conclusion holds uniformly for this whole family, including collapsing intervals and arbitrary dependence of $\delta$ on $q$.

Write $b_*=1/H$. The innovation decomposition gives $\mathbb E_QW_1=\mathbb E_{\mathbb Q}\int_0^1\beta_tdt$. Subtracting the constant mark $b_*$ in the now-established endpoint identity yields
$$
\frac MF=\mathbb E_Q[W_1(b(W_1)-b_*)]
-\mathbb E_{\mathbb Q}\int_0^1(a_t-b_*)\beta_tdt.
$$
The first term is nonpositive: $W_1\ge A>0$ on the terminal support and $b\le b_*$. Since $y=Ha_t\in[0,1]$ satisfies $(1-y)^2\le1-y^2$,
$$
\mathbb E_{\mathbb Q}\int_0^1(a_t-b_*)^2dt\le H^{-2}(1-x).
$$
Cauchy--Schwarz and the checked entropy identity now give
$$
M_+\le \frac F H\sqrt{2D}\sqrt{1-x}.
$$
Here $F=q/3$ and $D=\log(3/q)$. For $U\ge3$, integration on $[U,U+1]$ gives $q\ge\phi(U+1)$, and hence
$$
D\le\log3+\tfrac12\log(2\pi)+\tfrac12(U+1)^2\le2U^2.
$$
The last inequality holds at $U=3$ and its difference has positive derivative thereafter. Also $H=h(U)\ge U$. Consequently
$$
M_+\le\frac{2q}{3}\sqrt{1-x}
\le\frac{2q}{3}\left\{\sqrt{1-x}+\sqrt{1+D}(1-x)\right\}.
$$
Every constant is uniform in $q,\delta$, so no degeneration in this three-mark family disproves the asserted universal mixed budget. This is only a scoped failed search, not a proof of the unrestricted lemma.

## Failure

NOT fails: all three terminal marks stay nonnegative and below $1/H$ on a positive scalar terminal support, making the centered endpoint term nonpositive and allowing entropy energy to control every collapsing rank band simultaneously.
