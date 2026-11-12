---
type: candidate
title: Rank-one mixed-label Gaussian cascades with one true null
status: failed
target_asset: gaussian_bh_entropy_coherence_trace_budget
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
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:31:00.636Z'
extension_version: 0.0.4
---

## Object

This is a family with an arbitrary finite number of tests, exactly one original true null, and an arbitrary number of actual BH rank changes. Its new feature relative to the two-test families on the board is a genuine multistate posterior: the explicit three-test subfamily below has three distinct, positive-probability selected-null ranks. The argument uses monotonicity on the actual selection support rather than a binary-state calculation or the all-null parallel-loading halfspace reduction.

Let $N\ge3$ and $Y\sim N(0,1)$. The true null is
$$
T_0=\theta_0+Y,\qquad \theta_0\le0.
$$
Each of the other $N-1$ tests has an arbitrary finite positive mean $\mu_j>0$ and a loading $\epsilon_j\in\{-1,1\}$:
$$
T_j=\mu_j+\epsilon_jY\quad(1\le j\le N-1).
$$
Use the original one-sided p-values and the ordinary largest-rank BH procedure. Set $0<q\le\overline\Phi(3)$, $u_r=\overline\Phi^{-1}(qr/N)$, $U=u_N$ and $H=h(U)$. On the support $S$ where the true null is selected, $f=1/R$ and $b=1/h(u_R)$; off that support $f=0$.

An explicit three-test subfamily realizes the ranks $3$, $2$ and $1$ in that order. Here $N=3$, $\theta_0=0$ and both alternatives have loading $-1$. Define
$$
e=\frac{u_1-u_2}{4},\qquad c_3=u_2+e,\qquad c_2=u_1+2e,
$$
$$
\mu_1=u_2+c_2=u_1+u_2+2e,\qquad
\mu_2=U+c_3=U+u_2+e.
$$
Then $\mu_1>\mu_2>0$, and on the true-null selection support the exact largest BH rank is
$$
R(Y)=\begin{cases}
3,&U\le Y\le c_3,\\
2,&c_3<Y\le c_2,\\
1,&Y>c_2.
\end{cases}
$$
Every interval has positive Gaussian probability. The true null is not selected for $Y<U$. Thus this is a real $3\to2\to1$ Gaussian BH cascade, not a free rank assignment or a duplicated two-state example.

## Checks

### H1

The family has finite $N$, latent dimension $d=1$, and unit loading vectors $v_0=1$, $v_j=\epsilon_j$. The covariance matrix $\Sigma_{ij}=v_iv_j$ is a positive-semidefinite Gram matrix with unit diagonal. Its singular rank-one form is explicitly allowed by the target. Each selected value of $q$ gives finite positive means in the explicit subfamily; this allowed dependence on $q$ does not change admissibility.

### H2

The original true-null set is exactly $I_0=\{0\}$ because $\theta_0\le0$ and every $\mu_j>0$. In particular no negative-loading alternative has been relabelled a null. The whole family retains arbitrary finite negative true-null means. The explicit three-test subfamily uses the admissible value $\theta_0=0$.

### H3

First verify the displayed three-test ranks. The larger alternative is always $\mu_1-Y$. For $Y\ge U$, rank three qualifies exactly when the smaller alternative also reaches $U$, namely $Y\le\mu_2-U=c_3$. If $Y>c_3$, the smaller alternative is below $U$, so rank three fails. On that region a qualifying rank two containing the null requires and, because $Y>c_3>u_2$, is equivalent to $\mu_1-Y\ge u_2$, or $Y\le c_2$. If $Y>c_2$, neither rank three nor rank two qualifies; the null itself exceeds $u_1$ since $c_2>u_1$, so rank one qualifies and selects the null. For $Y<U$, no BH rank can select it because every $u_r\ge U$. These statements use the largest qualifying rank and non-strict inequalities throughout. Boundary values have the stated largest ranks, and the Gaussian measure of all boundaries is zero.

Next prove the monotonicity needed for the entire family. Let $y_1<y_2$ be any two points of $S$, the actual support where the original true null is selected, and write $r_k=R(y_k)$. Suppose for contradiction that $r_2>r_1$. At $y_1$ the null statistic is at least $u_{r_1}>u_{r_2}$. Every positive-loading alternative is still larger than that null statistic, since $\mu_j>\theta_0$. Therefore every positive-loading statistic, including the null, is already at least $u_{r_2}$ at $y_1$. Each negative-loading alternative selected at $y_2$ has a larger statistic at $y_1$, so it too is at least $u_{r_2}$ at $y_1$. Consequently all $r_2$ statistics selected at $y_2$ reach $u_{r_2}$ at $y_1$. Rank $r_2$ would qualify at $y_1$, contradicting that $r_1$ is its largest qualifying rank. Hence
$$
y_1<y_2,\quad y_1,y_2\in S\quad\Longrightarrow\quad R(y_1)\ge R(y_2).
$$
No monotonicity is asserted off $S$; the selection support can have gaps in the general family. This distinction matters for the posterior calculation.

### H4

If $Y\ge u_1-\theta_0$, the null p-value is at most $q/N$, so the actual BH procedure selects it. On that event $f=1/R\ge1/N$. It follows that
$$
F\ge\frac{\overline\Phi(u_1-\theta_0)}N>0.
$$
Every terminal FDP is in $[0,1]$. On its positive support it is at least $1/N$, so $\log(f/F)$ is bounded for each fixed finite model and $D<\infty$. More generally $D\le\log(1/F)$ since $\log f\le0$ on the terminal tilted support.

For the explicit three-test subfamily, its exact FDR is
$$
F=\frac q3+\frac{\overline\Phi(c_3)}6+
\frac{\overline\Phi(c_2)}2>0,
$$
obtained by integrating the displayed ranks with their actual FDP values $1/3,1/2,1$.

### H5

All fields in this check are those in the target definition; none is replaced by a selected rank independent of the Gaussian data. The Mills ratio is increasing: for positive $u$, integration of $z\phi(z)$ gives $\phi(u)>u\overline\Phi(u)$, and therefore
$$
h'(u)=h(u)\{h(u)-u\}>0.
$$
As $R$ increases, $u_R$ decreases and $1/h(u_R)$ increases. The result of H3 thus shows that $b(y)=1/h(u_{R(y)})$ is a nonincreasing function of $y$ on $S$. Also $0<b\le1/H$ on $S$.

For $t<1$, put $s=1-t$. The posterior probability measure given a heat state $w$ is
$$
\nu_{t,w}(dy)=
\frac{f(y)\exp\{-(y-w)^2/(2s)\}\,dy}
{\int f(z)\exp\{-(z-w)^2/(2s)\}\,dz}.
$$
Its support is contained in $S$, and the exact heat field is
$$
a(t,w)=\mathbb E_{\nu_{t,w}}b(Y).
$$
The boundedness of $b$ and $f$ permits differentiation of the Gaussian convolution. The scalar spatial Jacobian is
$$
K(t,w)=\partial_w a(t,w)
=\frac{\operatorname{Cov}_{\nu_{t,w}}(b(Y),Y)}s\le0.
$$
For completeness, if $Y'$ is an independent variable with the same posterior law, twice that covariance is the expectation of
$$
\{b(Y)-b(Y')\}(Y-Y'),
$$
which is nonpositive because both variables lie in $S$ and $b$ is nonincreasing on that support. This argument is valid even when $S$ is disconnected.

The bounded Doob posterior $a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]$ is a square-integrable martingale under the path tilt. Here this follows directly by conditioning Wiener measure with its terminal likelihood $f(W_1)/F$, since $B=fb$. If $\beta=\partial_w\log P_{1-t}f$, the quotient of the two heat equations satisfies
$$
\partial_t a+\tfrac12\partial_w^2 a+\beta\partial_w a=0.
$$
On every interval ending before one, the usual likelihood change of measure and Itô formula therefore give $da_t=K_t\,dW_t^{\mathbb Q}$, where $W^{\mathbb Q}$ is its Brownian innovation. The bounded martingale extends to terminal value $b(W_1)$, so localization and monotone convergence in the Itô isometry imply
$$
\mathbb E_{\mathbb Q}\int_0^1 K_t^2\,dt
=\operatorname{Var}_Q b\le H^{-2}.
$$
Consequently
$$
\mathbb E_{\mathbb Q}\int_0^1|K_t|\,dt\le H^{-1}<\infty,
\qquad 0\le x=H^2\mathbb E_{\mathbb Q}\int_0^1 a_t^2\,dt\le1.
$$
Thus the signed trace and coherence are finite in the exact conventions of the target.

### NOT

The full spatial Jacobian, not merely an isolated terminal face, is nonpositive at every heat state by H5. Therefore
$$
M=F\mathbb E_{\mathbb Q}\int_0^1K_t\,dt\le0,
\qquad M_+=0.
$$
The proposed budget holds for this entire family with any positive constant $C$, on every $0<q\le\overline\Phi(3)$. In particular the explicit three-state mixed-label cascade cannot supply an unbounded normalized positive trace. This excludes only the rank-one, exactly-one-true-null family specified above; it says nothing about nonparallel directions or multiple true nulls.

## Failure

NOT fails: in every admissible one-true-null rank-one mixed-loading model, including the explicit three-state BH cascade, the complete heat Jacobian trace is pointwise nonpositive and $M_+=0$.
