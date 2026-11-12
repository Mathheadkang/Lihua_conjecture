---
type: candidate
title: Independent mixed-label Gaussian pair has strictly negative Mills heat trace
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
slot: 2
direction: small_cases
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:09:57.508Z'
extension_version: 0.0.4
---

## Object

For any $0<q\le\overline\Phi(3)$ and any $\mu>0$, take $N=d=2$,
$v_1=e_1$, $v_2=e_2$, and $\theta=(0,\mu)$. Put
$U=\overline\Phi^{-1}(q)$, $A=\overline\Phi^{-1}(q/2)$,
$L=U-\mu$, $H=h(U)$, $b=1/H$, $c=1/h(A)$ and $\Delta=b-c>0$.
Thus $\Sigma=I_2$ and $I_0=\{1\}$. Define the disjoint sets
$$
E=\{z_1\ge U,\ z_2\ge L\},\qquad
J=\{z_1\ge A,\ z_2<L\}.
$$
This tests two genuinely noncollinear directions. The new mechanism is that
the trace differentiates the true-null coordinate while the alternative
coordinate controls which of two different BH rank cutoffs applies.
The board's antialigned scalar families do not cover this geometry.

## Checks

### H1

The testing level is positive and at most $\overline\Phi(3)$, so $U\ge3$.
Both latent dimensions and the number of tests are positive integers.
The two vectors have unit norm and their Gram matrix is the identity.
Consequently the displayed model is exactly jointly Gaussian and satisfies
the full covariance hypotheses, without any marginal transformation.

### H2

The means are $(0,\mu)$ with $\mu>0$. With the prescribed one-sided
p-values $p_1=\overline\Phi(z_1)$ and
$p_2=\overline\Phi(\mu+z_2)$, exactly test 1 is a true null.

### H3

The largest qualifying BH rank is two exactly when both p-values are at
most $q$, namely on $E$. There $f=1/2$ and $B=(b/2)e_1$.
If test 1 is rejected alone, it must satisfy $p_1\le q/2$, and failure
of rank two then forces $p_2>q$. This is exactly $J$, where $f=1$ and
$B=ce_1$. In every other region $f=B=0$, even if only the alternative is
rejected. Thus the actual BH rule, including the largest rank convention,
gives
$$
f=\tfrac12\mathbf1_E+\mathbf1_J,
\qquad B=e_1\bigl(\tfrac b2\mathbf1_E+c\mathbf1_J\bigr).
$$
Boundary equalities have Gaussian measure zero and are assigned according
to the stated non-strict BH convention.

### H4

Write $r=\overline\Phi(L)\in(0,1)$. Independence gives
$$
\gamma_2(E)=qr,\qquad \gamma_2(J)=\tfrac q2(1-r),
\qquad F=\tfrac q2>0.
$$
Under the prescribed terminal tilt, $Q(E)=r$ and $Q(J)=1-r$.
The density is $1/q$ on $E$, $2/q$ on $J$, and zero elsewhere; hence
$$
D=r\log(1/q)+(1-r)\log(2/q)
 =\log(2/q)-r\log2\in[0,\log(1/F)].
$$
For $s=1-t>0$, set
$$
p_a(t,z)=\overline\Phi\bigl((a-z)/\sqrt s\bigr).
$$
The exact heat fields are
$$
\mathcal H=\tfrac12p_U(t,z_1)p_L(t,z_2)
             +p_A(t,z_1)(1-p_L(t,z_2)),
$$
$$
\mathcal L=e_1\bigl(\tfrac b2p_U(t,z_1)p_L(t,z_2)
             +c p_A(t,z_1)(1-p_L(t,z_2))\bigr).
$$
All factors lie strictly between zero and one. Therefore $\mathcal H>0$
and, with
$$
\pi(t,z)=\frac{\tfrac12p_U(t,z_1)p_L(t,z_2)}{\mathcal H(t,z)},
$$
we have $a=e_1(c+\Delta\pi)$ and $0<\pi<1$.
These are the target's heat fields, not a replacement tilt.

### H5

Here are independent integrability and endpoint checks before using the
signed trace to test the budget. Put $Z_t=\mathcal H(t,W_t)/F$.
Under Wiener measure this is the positive density martingale
$\mathbb E_{\mathbb P}[f(W_1)/F\mid\mathcal F_t]$ and satisfies
$dZ_t=Z_t\beta_t\cdot dW_t$ on $t<1$.
Applying Itô's formula to $Z\log Z$, with localization at positive lower
and finite upper cutoffs followed by convex regularization at zero, gives
$$
\mathbb E_{\mathbb P}[Z_t\log Z_t]
=\tfrac12\mathbb E_{\mathbb Q}\int_0^t\|\beta_u\|^2du.
$$
The density is bounded by $1/F$. Conditional-expectation convergence and
continuity of $z\log z$ at zero therefore yield
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt=2D<\infty.
$$
Local Girsanov, extended to time one by this finite energy, makes
$\widetilde W_t=W_t-\int_0^t\beta_u\,du$ Brownian under $\mathbb Q$.
Define the bounded terminal vector $\xi=B(W_1)/f(W_1)$ on the support
of $\mathbb Q$. The conditional density formula gives
$a_t=\mathbb E_{\mathbb Q}[\xi\mid\mathcal F_t]$.
Differentiating the heat quotient and using the backward heat equations
gives
$$
da_t=K_t\,d\widetilde W_t.
$$
Since $\xi$ equals $be_1$ on $E$ and $ce_1$ on $J$, the bounded
martingale and Itô isometry give the explicit energy identity
$$
\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\rm HS}^2dt
=\mathbb E_{\mathbb Q}\|\xi-\mathbb E_{\mathbb Q}\xi\|^2
=r(1-r)\Delta^2<\infty.
$$
Only the first row of $K$ can be nonzero, so
$|\operatorname{tr}K|=|K_{11}|\le\|K\|_{\rm HS}$. Consequently
$$
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt
\le\sqrt{r(1-r)}\,\Delta<\infty.
$$
Also $\|a_t\|\le b=1/H$, which proves $0\le x\le1$ and, by
Cauchy--Schwarz and the drift energy identity,
$$
\mathbb E_{\mathbb Q}\int_0^1|a_t\cdot\beta_t|dt
\le b\sqrt{2D}<\infty.
$$
For the endpoint identity, Itô isometry for the two martingales $a$ and
$\widetilde W$ gives, for $\tau<1$,
$$
\mathbb E_{\mathbb Q}[a_\tau\cdot\widetilde W_\tau]
=\mathbb E_{\mathbb Q}\int_0^\tau\operatorname{tr}K_tdt.
$$
The martingale property of $a$ and conditioning at time $t$ also give
$$
\mathbb E_{\mathbb Q}\left[a_\tau\cdot\int_0^\tau\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^\tau a_t\cdot\beta_tdt.
$$
The preceding absolute bounds justify conditioning and integration.
Adding these identities proves the desired cutoff product identity.
As $\tau\uparrow1$, $a_\tau\to\xi$ in $L^2(\mathbb Q)$.
Also $W_\tau\to W_1$ in $L^2(\mathbb Q)$ because
$d\mathbb Q/d\mathbb P\le1/F$. Thus the endpoint converges in $L^1$,
and
$$
\lim_{\tau\uparrow1}M_\tau
=\int z\cdot B(z)\,d\gamma_2(z)
-F\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt
=F\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt.
$$
The first endpoint integral is finite and is explicitly
$$
\int z\cdot B(z)\,d\gamma_2(z)
=\tfrac b2\phi(U)r+c\phi(A)(1-r)=\tfrac q2.
$$
Hence all well-posedness claims needed for this candidate and both
representations of $M$ have been established without assuming them.

### NOT

The conclusion does not fail. Indeed $h$ is strictly increasing:
$h'(y)=h(y)(h(y)-y)>0$, where $h(y)>y$ follows from the conditional
mean of a standard normal variable above $y$ (and is immediate for
$y\le0$). Since $U<A$,
$$
\partial_{z_1}\log\frac{\pi}{1-\pi}
=\frac{h((U-z_1)/\sqrt s)-h((A-z_1)/\sqrt s)}{\sqrt s}<0.
$$
Therefore
$$
\operatorname{tr}K_t
=\Delta\,\partial_{z_1}\pi(t,W_t)<0
\qquad(0\le t<1).
$$
Absolute integrability was proved in H5, so $M<0$ and $M_+=0$.
The proposed mixed budget holds for this entire independent two-test
mixed-label family, for every positive constant $C$. This eliminates
this specific noncollinear small case only; it gives no claim about
correlated pairs or unrestricted multidirectional models.

## Failure

NOT fails: independence places the larger Mills mark on the region with the lower true-null cutoff, so the corresponding posterior decreases in the trace coordinate and $M<0$.
