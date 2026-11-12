---
type: candidate
title: >-
  Common true-null direction with noncollinear alternatives and variable BH
  ranks
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
slot: 3
direction: drop_hypothesis
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:20:56.688Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$, set $N=4$, $d=2$, and use independent
standard normal latent coordinates $(Z_0,Z_1)$. Let the test statistics be
$$
T_1=Z_0,\quad T_2=Z_0-q,\quad T_3=q+Z_1,\quad
T_4=2q+(Z_0-Z_1)/\sqrt2.
$$
The true-null means are zero and $-q$; their common observation vector is
$v=e_0$. The two alternative observation vectors are $e_1$ and
$(e_0-e_1)/\sqrt2$.

The calculation below applies more generally to every finite model whose
nonempty true-null set has a common unit observation vector $v$, with
arbitrary nonpositive null means and arbitrary unit observation vectors and
positive means for its alternatives. Thus the number of tests, covariance
rank, alternative geometry, and actual-rank changes can grow with $q^{-1}$.
The common true-null direction is essential to this scoped calculation.

Unlike the excluded constant-posterior family, the explicit four-test
object has two distinct terminal Mills marks on sets of positive tilted
probability, as checked below. Unlike the earlier pair calculations, this
object has multiple selected nulls, three observation directions, and
alternative-driven changes in the actual selected rank.

## Checks

### H1

The displayed testing range gives $U=\overline\Phi^{-1}(q)\ge3$ and
$H=h(U)$. The specified dimensions are positive and finite. The same
calculation uses arbitrary positive finite $N,d$ in the common-null-vector
family, without a dimension-dependent constant.

### H2

The four observation vectors $e_0,e_0,e_1,(e_0-e_1)/\sqrt2$ are unit
vectors. Their Gram matrix is positive semidefinite with diagonal one,
and their linear construction from $(Z_0,Z_1)$ is exactly jointly Gaussian.
Its singular covariance in four coordinates is permitted.

### H3

Use $p_i=\overline\Phi(T_i)$ and the one-sided null convention. Then
$I_0=\{1,2\}$ exactly. In the general family $I_0$ consists of the
coordinates with nonpositive means, and each has observation vector $v$.
All stated means and vectors obey the required model assumptions.

### H4

Apply ordinary BH with its largest qualifying rank, all multiplicities and
non-strict inequalities. Write $f=V/(R\vee1)$ and use the prescribed $B$.
On $\{f>0\}$ in any common-null-vector model, direct cancellation gives
$$
\frac{B}{f}=v s,\qquad s=\frac1{h(u_R)},\qquad 0<H s\le1.
$$
Define $s=0$ off this support. If any true null is selected, then its
statistic satisfies $\theta_i+v\cdot G\ge u_R\ge U$; since $\theta_i\le0$,
this implies $v\cdot G\ge U$. Consequently
$$
0<F=\mathbb E f\le\mathbb P(v\cdot G\ge U)=q
$$
whenever the tilt is required. If there are no true nulls or $F=0$, no
tilted assertion is needed.

For completeness, the explicit object has $F>0$ and a nonconstant terminal
mark. Put $A=\overline\Phi^{-1}(q/2)=u_2$. At the latent point
$(Z_0,Z_1)=(A+2q,0)$ both nulls exceed $A$, whereas both alternatives have
statistics below $U$. To verify the latter for $T_4$, the identity
$\log2=\int_U^A h(t)dt$ and $h(t)\ge t$ yield
$A-U\le\log2/U<1/3$. Since $q\le\overline\Phi(3)<1/100$ and $U\ge3$,
$$
(A+2q)/\sqrt2+2q
< U/\sqrt2+1/(3\sqrt2)+(\sqrt2+2)/100<U.
$$
Thus the actual rank is two in a neighborhood of this point, with
$f=1$ and $s=1/h(A)$. At $(Z_0,Z_1)=(4U,U)$ all four statistics strictly
exceed $U$, so the actual rank is four in a neighborhood, with $f=1/2$
and $s=1/H$. Both neighborhoods have positive Gaussian probability, so
both marks have positive probability under $Q$.

### H5

Use exactly the prescribed terminal and path tilts and heat fields. The
following independently checks their required integrability and endpoint
identity before using either representation of $M$.

Since $0\le f\le1$ and $F>0$, relative entropy obeys
$0\le D\le\log(1/F)<\infty$. Under Wiener measure put
$Z_t=\mathcal H(t,W_t)/F$. Conditional Jensen bounds the expected entropy
$\mathbb E[Z_\tau\log Z_\tau]$ at any stopped time before one by $D$.
Applying Ito's formula to $Z\log Z$ on localized compact intervals and
using monotone convergence therefore gives
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt\le2D<\infty.
$$
Indeed its finite-variation term under Wiener measure is
$\tfrac12 Z_t\|\beta_t\|^2dt$, and changing measure converts its expectation
to that under $\mathbb Q$. Local change of measure thus supplies a
$\mathbb Q$-Brownian motion
$$
\widetilde W_t=W_t-\int_0^t\beta_sds.
$$
Finite energy extends this Brownian motion continuously to time one.

Bayes' rule for the terminal tilt shows that the heat quotient is
$$
a_t=v k_t,\qquad
k_t=\mathbb E_{\mathbb Q}[s(W_1)\mid\mathcal F_t],\qquad
0\le k_t\le 1/H.
$$
The heat quotient equation and Ito's formula give
$dk_t=\nabla k(t,W_t)\cdot d\widetilde W_t$. Boundedness, terminal
$L^2$ convergence, and Ito isometry yield
$$
\mathbb E_{\mathbb Q}\int_0^1\|\nabla k(t,W_t)\|^2dt
=\operatorname{Var}_Q(s)<\infty.
$$
As $K_t=v\otimes\nabla k(t,W_t)$, Cauchy--Schwarz gives
$$
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt
\le\sqrt{\operatorname{Var}_Q(s)}<\infty.
$$
Also $|a_t|\le1/H$, so
$\mathbb E_{\mathbb Q}\int|a_t\cdot\beta_t|dt\le\sqrt{2D}/H<\infty$.
Conditional Jensen establishes both the coherence bound and the useful
quantitative deficit bound
$$
0\le x=H^2\int_0^1\mathbb E_{\mathbb Q}k_t^2dt
\le H^2\mathbb E_Q s^2\le1,
\qquad 1-x\ge\mathbb E_Q[1-H^2s^2].
$$
The endpoint integral is finite because $B$ is bounded and the underlying
Gaussian has finite first moments. Ito covariance for the square-integrable
martingales $k_t$ and $v\cdot\widetilde W_t$ gives
$$
\mathbb E_{\mathbb Q}[s(W_1)v\cdot\widetilde W_1]
=\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt.
$$
Conditioning $s(W_1)$ at time $t$, using the adaptedness of $\beta_t$ and
the preceding integrability, gives
$$
\mathbb E_{\mathbb Q}\left[s(W_1)v\cdot\int_0^1\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt.
$$
Since $F\mathbb E_Q[s(W_1)v\cdot W_1]=\int z\cdot B(z)\gamma_d(dz)$,
adding these identities proves precisely
$$
\int z\cdot B\,d\gamma_d
-F\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt
=F\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt
=\lim_{\tau\uparrow1}M_\tau.
$$
The last equality uses the established absolute trace integrability, and
requires no endpoint heat-field values.

### NOT

Now use the already verified identity
$M=F\mathbb E_{\mathbb Q}[s(W_1)v\cdot\widetilde W_1]$.
The scalar $v\cdot\widetilde W_1$ is a standard normal under $\mathbb Q$;
independence from $s(W_1)$ is neither asserted nor needed. It has mean zero
and second moment one. Centering $s$ at the deterministic value $1/H$ and
applying Cauchy--Schwarz yields
$$
|M|\le F\sqrt{\mathbb E_Q(s-1/H)^2}.
$$
For $0\le s\le1/H$, the pointwise inequality
$(s-1/H)^2\le H^{-2}-s^2$ holds. Hence
$$
M_+\le|M|
\le\frac FH\sqrt{\mathbb E_Q(1-H^2s^2)}
\le\frac qH\sqrt{1-x}
\le q\sqrt{1-x}.
$$
This is uniform over the whole finite common-null-vector family, including
arbitrary alternative rank cascades. It verifies the square-root part of
the proposed budget with $C=1$ and cannot refute the mixed estimate.
It supplies no bound for multiple distinct true-null directions.

## Failure

NOT fails: common true-null direction gives $F\le q$ and a bounded scalar
terminal Mills mark; centering that mark at $1/H$ yields
$M_+\le(q/H)\sqrt{1-x}$ despite arbitrary alternative geometry and ranks.
