---
type: candidate
title: Mixed-label antipodal rank loss gives a negative heat trace
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:04:05.474Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$ put
$$
U=\overline\Phi^{-1}(q),\quad A=\overline\Phi^{-1}(q/2),\quad L=A+1,
\quad H=h(U),\quad k_0=H^{-1},\quad k_1=h(A)^{-1}.
$$
Take $N=2,d=1$, $v_1=1,v_2=-1$, and $\theta_1=0$, $\theta_2=U+L$. Thus $T_1=G$ is the only true null and $T_2=U+L-G$ is a false null. This is a new mixed-label case: the previous antipodal pair had two true nulls, whereas here a sufficiently strong false null makes the actual rank drop from two to one inside the true-null rejection tail. The terminal ratio is nonconstant, so the constant-posterior obstruction does not apply.

## Checks

### H1

The testing level obeys the full stated range with $q_0=\overline\Phi(3)$; in particular $U\ge3$, $A>U$, and $L>A$.

### H2

Both dimensions are positive finite integers and both observation vectors are unit vectors. The covariance matrix is
$$
\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix},
$$
which is positive semidefinite with unit diagonal. The real mean $U+L>0$ is permitted to depend on $q$. Exactly $I_0=\{1\}$.

### H3

Rank two qualifies precisely when both statistics are at least $U$, namely when $U\le G\le L$. In that interval ordinary BH rejects both tests, even in the portion $G<A$ where rank one would not qualify for the null alone. For $G>L$ the second test has statistic less than $U$; because $G>L>A$, the true null qualifies at rank one and is the only rejection. For $G<U$ no true null can be rejected: a true-null rank-one rejection requires $G\ge A$, and a rank-two rejection requires $G\ge U$. Consequently, up to irrelevant endpoint conventions,
$$
f(g)=\tfrac12\mathbf1_{\{g\ge U\}}+\tfrac12\mathbf1_{\{g\ge L\}},
$$
$$
B(g)=\tfrac{k_0}{2}\mathbf1_{\{g\ge U\}}
 +(k_1-\tfrac{k_0}{2})\mathbf1_{\{g\ge L\}}.
$$
This uses the largest qualifying rank and all multiplicities. Values at the two endpoints can be taken according to the non-strict BH convention and do not alter any convolution or integral.

### H4

The tilt exists since
$$
F=\tfrac12\overline\Phi(U)+\tfrac12\overline\Phi(L)>0.
$$
All heat fields below are exactly those of the statement. Write $s=1-t>0$ and
$$
T_c(t,z)=\overline\Phi((c-z)/\sqrt s),\qquad
\mathcal H(t,z)=\tfrac12(T_U+T_L),\qquad
\pi(t,z)=\frac{T_L}{\mathcal H}=\frac{2T_L}{T_U+T_L}.
$$
Then $0<\pi<1$ and the posterior field is
$$
a(t,z)=k_0+(k_1-k_0)\pi(t,z).
$$
In particular, it is not constant.

### NOT

This check fails: every well-posedness assertion and the endpoint identity hold, and $M<0$ makes the proposed budget automatic.

First, $h$ is strictly increasing: $h'(u)=h(u)(h(u)-u)>0$, using $h(u)>u$ for $u>0$ from the elementary Gaussian tail bound, and $h(u)>0\ge u$ for $u\le0$. Hence $0<k_1<k_0=1/H$. Since $0<\pi<1$, $0<a\le1/H$, and therefore $0\le x\le1$. Also $0\le f\le1$ gives
$$
0\le D=\int (f/F)\log(f/F)\,d\gamma_1\le\log(1/F)<\infty.
$$
The lower bound is Jensen's inequality.

For completeness, the heat-score energy identity holds here without assuming any target assertion. Under Wiener measure let $Z_t=\mathcal H(t,W_t)/F=\mathbb E[f(W_1)/F\mid\mathcal F_t]$. This is a bounded positive martingale for $t<1$, with $dZ_t=Z_t\beta_t\,dW_t$, $Z_0=1$, and bounded terminal value $Z_1=f(W_1)/F$. Apply Ito's formula to $(Z_t+\varepsilon)\log(Z_t+\varepsilon)$, first stopping and then passing to the bounded martingale limit at $t=1$. Letting $\varepsilon\downarrow0$ gives, by monotone convergence on the quadratic-variation term and bounded convergence on the terminal term,
$$
\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt
=\mathbb E_{\mathbb P}\int_0^1\frac{|\nabla Z_t|^2}{Z_t}dt=2D<\infty.
$$
Thus Cauchy--Schwarz and $|a|\le1/H$ yield
$$
\mathbb E_{\mathbb Q}\int_0^1|a_t\beta_t|dt\le\sqrt{2D}/H<\infty.
$$

Next, $T_L/T_U$ is strictly increasing in $z$, since
$$
\partial_z\log(T_L/T_U)
=\frac{h((L-z)/\sqrt s)-h((U-z)/\sqrt s)}{\sqrt s}>0.
$$
It follows that $\partial_z\pi>0$. Because $\partial_z\mathcal H>0$,
$$
0<\mathcal H\,\partial_z\pi
=\partial_zT_L-\frac{T_L}{\mathcal H}\partial_z\mathcal H
\le\partial_zT_L
=\frac1{\sqrt s}\phi((L-z)/\sqrt s).
$$
Therefore the scalar Jacobian $K=\partial_za=(k_1-k_0)\partial_z\pi$ is strictly negative. For every $t<1$, conditioning the terminal tilt and convolving Gaussian densities give
$$
F\mathbb E_{\mathbb Q}|K_t|
=\mathbb E_{\mathbb P}[\mathcal H(t,W_t)|K(t,W_t)|]
\le(k_0-k_1)\phi(L).
$$
Here the last equality uses $W_t\sim N(0,t)$ and $s+t=1$. Integrating proves absolute trace integrability on the entire interval and
$$
-F(k_0-k_1)\phi(L)/F\le M<0;
$$
equivalently, $-(k_0-k_1)\phi(L)\le M<0$. Strict negativity follows since $K(t,z)<0$ everywhere for every $t<1$.

To verify the endpoint representation independently, let $\mathcal L=P_{1-t}B=\mathcal H a$. For each $t<1$, differentiating this product gives
$$
\mathcal H\,\partial_za=\partial_z\mathcal L-a\partial_z\mathcal H.
$$
The explicit Gaussian convolution yields the time-independent identity
$$
\mathbb E_{\mathbb P}\partial_z\mathcal L(t,W_t)
=\tfrac{k_0}{2}\phi(U)+(k_1-\tfrac{k_0}{2})\phi(L)
=\int gB(g)\,\gamma_1(dg).
$$
The last integral is absolutely finite because $|B|\le1/H$. Moreover,
$$
\mathbb E_{\mathbb P}[a(t,W_t)\partial_z\mathcal H(t,W_t)]
=F\mathbb E_{\mathbb Q}[a_t\beta_t].
$$
Integrate these equalities over $0\le t\le\tau$ and then let $\tau\uparrow1$. The absolute trace estimate and the already proved cross-term integrability justify this passage and give exactly
$$
M=\lim_{\tau\uparrow1}M_\tau
=\int gB(g)\,\gamma_1(dg)
-F\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt=M_*.
$$
Finally $M_+=0$, so the mixed budget holds for this whole family with any fixed $C>0$, uniformly for $0<q\le\overline\Phi(3)$. The new actual-rank jump lowers the terminal Mills ratio; its posterior derivative has the opposite sign from the positive trace required for a counterexample.

## Failure

NOT fails: in this mixed-label antipodal family the actual-rank loss makes the scalar posterior field strictly decreasing, so the finite signed heat trace is negative and $M_+=0$.
