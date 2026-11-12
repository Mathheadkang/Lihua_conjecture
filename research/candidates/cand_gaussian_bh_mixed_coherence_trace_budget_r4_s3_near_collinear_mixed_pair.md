---
type: candidate
title: Nearly collinear correlated mixed pair at the null-mean boundary
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

For every $0<q\le\overline\Phi(3)$ put $N=d=2$, $\theta=(-q,q)$,
$\rho=1-q^2$, $v_1=e_1$, and $v_2=(\rho,\sqrt{1-\rho^2})$.
Set $T_i=\theta_i+v_i\cdot G$ for $G\sim\gamma_2$.
Both means approach the true-null boundary, and the full-rank covariance
approaches the singular equal-direction covariance as $q\downarrow0$.

This changes the earlier independent mixed-pair geometry: its factorization
and trace-sign argument do not apply when $\rho>0$. The calculation below
instead uses the fact that a pair with exactly one true null has only two
terminal Mills marks, both along that null's vector. It also proves the same
bound for every two-test model with exactly one true null and arbitrary
correlation whenever its tilted measure exists.

## Checks

### H1

The testing levels obey the required small-level range, and $N=d=2$ are
positive finite integers. Define $U=\overline\Phi^{-1}(q)\ge3$,
$A=\overline\Phi^{-1}(q/2)>U$, $H=h(U)$, $b=1/H$, $c=1/h(A)$,
$\Delta=b-c>0$, and $r=Hc\in(0,1)$.

### H2

Both observation vectors have norm one. Their Gram matrix is
$\begin{pmatrix}1&\rho\\\rho&1\end{pmatrix}$, whose eigenvalues $1\pm\rho$
are strictly positive because $0<\rho<1$. The displayed construction is
exactly jointly Gaussian, with unit marginal variances.

### H3

Use the prescribed one-sided p-values $p_i=\overline\Phi(T_i)$.
The true-null set is exactly $I_0=\{1\}$ because $\theta_1=-q<0<q=\theta_2$.
In particular $p_1$ is superuniform:
$\mathbb P(p_1\le t)=\overline\Phi(\overline\Phi^{-1}(t)+q)\le t$.

### H4

Write $y_i=v_i\cdot z$. Ordinary largest-rank BH gives the two disjoint
FDP-supporting regions
$$
E=\{y_1\ge U+q,\ y_2\ge U-q\},\qquad
J=\{y_1\ge A+q,\ y_2<U-q\}.
$$
On $E$ the actual rank is two, and on $J$ only the null is rejected.
Every other region has FDP zero. Thus
$$
f=\tfrac12\mathbf1_E+\mathbf1_J,\qquad
B=v_1\bigl(\tfrac b2\mathbf1_E+c\mathbf1_J\bigr).
$$
Boundary conventions agree with non-strict BH, and boundaries have Gaussian
measure zero. Both displayed regions contain open sets, so $F>0$.
More generally, a null with $p_1>q$ contributes nothing; for $q/2<p_1\le q$
its FDP is at most $1/2$; and for $p_1\le q/2$ it is at most one. Therefore
$$
F\le\tfrac12\mathbb P(p_1\le q/2)+\tfrac12\mathbb P(p_1\le q)
\le\tfrac{3q}{4}.
$$

### H5

Use exactly the terminal and path tilts and heat fields in the statement.
Under $Q$, the scalar terminal mark $\kappa=B\cdot v_1/f$ equals $b$ on
$E$ and $c$ on $J$. Put $p=Q(J)$; then $0<p<1$ and
$$
a_t=v_1 k_t,\qquad k_t=\mathbb E_{\mathbb Q}[\kappa(W_1)\mid\mathcal F_t],
\qquad \operatorname{Var}_Q(\kappa)=\Delta^2p(1-p).
$$
The conditional-expectation formula follows directly by Bayes' rule for the
terminal density $f(W_1)/F$ and the Brownian transition kernel.

Here are independent integrability and identity checks before using $M$.
Since $0\le f\le1$, entropy is finite and obeys
$0\le D\le\log(1/F)$. To obtain the drift-energy bound, let
$Z_t=\mathcal H(t,W_t)/F$ under Wiener measure. On each localized interval
before time one, Ito's formula gives
$d(Z_t\log Z_t)=(1+\log Z_t)dZ_t+\tfrac12Z_t\|\beta_t\|^2dt$.
Conditional Jensen bounds the expected entropy at every stopped time by
$\mathbb E_{\mathbb P}[Z_1\log Z_1]=D$. Localization, nonnegativity of the
energy, and monotone convergence therefore give
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt\le2D<\infty.
$$
The change of measure consequently yields a $\mathbb Q$-Brownian motion
$\widetilde W_t=W_t-\int_0^t\beta_sds$ on $[0,1]$ (first on compact
subintervals, then at the endpoint by the finite energy bound).
The heat quotient satisfies
$$
dk_t=\nabla k(t,W_t)\cdot d\widetilde W_t,
\qquad
\mathbb E_{\mathbb Q}\int_0^1\|\nabla k(t,W_t)\|^2dt
=\operatorname{Var}_Q(\kappa).
$$
The last equality is the Ito isometry and $L^2$ terminal convergence for the
bounded conditional-expectation martingale $k_t$. As
$K_t=v_1\otimes\nabla k(t,W_t)$ and $\|v_1\|=1$, it follows that
$$
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt
\le\sqrt{\operatorname{Var}_Q(\kappa)}<\infty.
$$
Also $|a_t|\le b$, so its product with $\beta_t$ is integrable by
Cauchy--Schwarz. Conditional Jensen gives
$$
0\le x=H^2\int_0^1\mathbb E_{\mathbb Q}k_t^2dt
\le H^2\mathbb E_Q\kappa^2
=1-p(1-r^2)\le1.
$$
The endpoint integral is finite because $B$ is bounded and Gaussian first
moments are finite. To check its stated identity, Ito covariance gives
$$
\mathbb E_{\mathbb Q}[\kappa(W_1)v_1\cdot\widetilde W_1]
=\mathbb E_{\mathbb Q}\int_0^1v_1\cdot\nabla k(t,W_t)dt.
$$
All terms are integrable by the preceding energy bounds. Conditional
expectation and Fubini also give
$$
\mathbb E_{\mathbb Q}\!\left[\kappa(W_1)v_1\cdot\int_0^1\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt.
$$
Adding the two equalities, using $W_1=\widetilde W_1+\int\beta$, and
$F\mathbb E_Q[\kappa(W_1)v_1\cdot W_1]=\int z\cdot B(z)\gamma_2(dz)$
proves the required endpoint identity. Absolute trace integrability proves
that this equals $\lim_{\tau\uparrow1}M_\tau$, with no endpoint heat-field
value assumed.

### NOT

The trace-energy estimate just established gives
$$
M_+\le |M|\le F\Delta\sqrt{p(1-p)}.
$$
Together with $1-x\ge p(1-r^2)$ and $F\le3q/4$, this implies
$$
M_+\le\frac{3q}{4}\frac{\Delta}{\sqrt{1-r^2}}\sqrt{1-x}
=\frac{3q}{4H}\sqrt{\frac{1-r}{1+r}}\sqrt{1-x}
\le q\sqrt{1-x}.
$$
Thus this full parameter family satisfies even the square-root term alone
with $C=1$, uniformly as its covariance becomes singular and its two means
approach zero. It cannot violate the proposed mixed budget. The argument
does not assert a trace sign and does not extend to multiple selected true
null directions or more than two terminal Mills marks.

## Failure

NOT fails: the unique-null Mills field is a bounded scalar martingale with
two terminal marks; its trace energy and the same mark mass in $1-x$ yield
$M_+\le q\sqrt{1-x}$ for the correlated, nearly singular mixed pair.
