---
type: candidate
title: >-
  Arbitrary finite Gaussian BH models with at most three distinct true-null
  directions
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
slot: 1
direction: boundary_degenerate
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:31:02.996Z'
extension_version: 0.0.4
---

## Object

Take every finite model in the target statement whose true-null vectors have at most three distinct oriented values. More precisely, choose arbitrary positive integers $N,d$, arbitrary real means $\theta_i$, and arbitrary unit vectors $v_i\in\mathbb R^d$, subject only to
$$
K=\bigl|\{v_i:\theta_i\le0\}\bigr|\le3.
$$
All false-null means and directions are unrestricted, as are the number of tests, covariance rank, negative true-null means, and actual largest-rank BH cascades. All parameters may depend arbitrarily on $q$, with $0<q\le\overline\Phi(3)$. Write the distinct true-null directions as $w_1,\ldots,w_K$.

This is a genuinely new family beyond the common-direction and two-test obstructions: it includes arbitrary numbers of hypotheses, genuinely noncollinear true-null directions, unrestricted alternative geometry, and collapsing or nearly aligned direction configurations. The draft idea `idea_a86564a9c1fa` was read using native `show` to locate its proposed finite-label mechanism; all assertions used here are derived below rather than assumed from that draft.

## Checks

### H1

$N,d$ are positive finite integers and $\theta\in\mathbb R^N$ is arbitrary and finite.

### H2

Every $v_i$ is a unit vector and $\Sigma_{ij}=v_i\cdot v_j$ is positive semidefinite with unit diagonal. The observations $T_i=\theta_i+v_i\cdot G$ are exactly jointly Gaussian; no nonsingularity is required.

### H3

The level satisfies $0<q\le\overline\Phi(3)$, so $U=\overline\Phi^{-1}(q)\ge3$ and $H=h(U)\ge U\ge3$.

### H4

Use exactly the prescribed one-sided p-values, true-null set $I_0=\{i:\theta_i\le0\}$, ordinary largest-rank BH rule, non-strict inequalities, and all multiplicities. Define $R,V,f,B,F$ from those actual rejection sets, exactly as in the statement. No replacement of the common BH crossing or rejection ranks is made.

### H5

If $K=0$, then $f=B=0$ and $F=0$, so the target requires no tilted-measure assertion. Suppose henceforth $1\le K\le3$. Then $F>0$: any true null $i$ has positive probability of $p_i\le q/N$, on which the BH rule rejects it and $f\ge1/N$.

On $\{f>0\}$, define the terminal mark
$$
b=\frac Bf=\frac1{Vh(u_R)}\sum_{i\in\mathcal R\cap I_0}v_i.
$$
Since $u_R\ge U$ and $h$ is increasing, $\|b\|\le1/H$. Set $b=0$ on $\{f=0\}$. Use the target's exact terminal and path tilts and all its heat fields. The bounded-mark conditional-expectation identity is
$$
a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t].
$$
It follows directly by Bayes' formula from $B=fb$ and the original Brownian transition kernel, so it does not presume an endpoint trace identity.

### NOT

**Fails.** This entire class satisfies all well-posedness and endpoint claims and obeys the mixed budget with the universal constant $C=2$. The following proof first establishes the integrability and endpoint identity and then obtains a uniform trace estimate.

**1. Entropy energy and innovation.** Since $0\le f\le1$,
$$
0\le D=\frac1F\int f\log f\,d\gamma_d+\log(1/F)\le\log(1/F)<\infty.
$$
Nonnegativity follows from convexity of $u\log u$. Let $L_t=\mathcal H(t,W_t)/F$ under the original Wiener measure. It is the bounded density martingale $\mathbb E_{\mathbb P}[f(W_1)/F\mid\mathcal F_t]$, with $0<L_t\le1/F$ for $t<1$. For fixed $\tau<1$, Itô's formula for $L_t\log L_t$ yields
$$
\mathbb E_{\mathbb P}L_\tau\log L_\tau
=\frac12\mathbb E_{\mathbb P}\int_0^\tau
\frac{\|\nabla L_t\|^2}{L_t}\,dt
=\frac12\mathbb E_{\mathbb Q}\int_0^\tau\|\beta_t\|^2dt.
$$
Here and below a gradient applied to a time-indexed heat field means its spatial gradient at $W_t$. A complete localization is available by stopping on $|W_t|\le n$ for $t\le\tau$: the positive heat density, its reciprocal, and its derivatives are bounded on each such compact set. The entropy function is bounded on $[0,1/F]$. Dominated convergence removes these stops; monotone convergence handles the nonnegative energy. As $\tau\uparrow1$, $L_\tau\to f(W_1)/F$ almost surely, and boundedness of $u\log u$ gives
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt=2D<\infty.
$$
On every $[0,\tau]$, change of measure using the strictly positive density martingale shows that
$$
Z_t=W_t-\int_0^t\beta_sds
$$
is Brownian motion under $\mathbb Q$ in the original path filtration. These identifications are compatible as $\tau$ increases. The finite drift energy makes $\int_0^1\beta_sds$ finite almost surely, so $Z$ extends continuously to time one and is standard Brownian there as well.

**2. Absolute integrability and endpoint identity.** The quotient heat equation gives, under $\mathbb Q$,
$$
da_t=K_t\,dZ_t.
$$
This is also the stochastic differential of the bounded conditional-expectation martingale from H5. Its $L^2$ terminal limit is $b(W_1)$, and Itô isometry gives
$$
\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\mathrm{HS}}^2dt
=\mathbb E_Q\|b\|^2-\|\mathbb E_Q b\|^2\le H^{-2}.
$$
In particular,
$$
0\le x\le1,\qquad
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt\le\frac{\sqrt d}{H}<\infty,\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\cdot\beta_t|dt\le\frac{\sqrt{2D}}H<\infty.
$$
The dimension-dependent intermediate bound is used only for well-posedness in each finite model, not for the final budget.

The endpoint integral is absolutely finite because $\|B\|\le f/H\le1/H$ and $\int\|z\|d\gamma_d<\infty$. The terminal martingale representation and the cross isometry imply
$$
\mathbb E_{\mathbb Q}[b(W_1)\cdot Z_1]
=\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt.
$$
Moreover, $\|b\|\le1/H$ and the established drift energy permit conditional expectation and Fubini:
$$
\mathbb E_{\mathbb Q}\left[b(W_1)\cdot\int_0^1\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt.
$$
Combining these equalities with $W_1=Z_1+\int\beta$ and $F\mathbb E_{\mathbb Q}[b(W_1)\cdot W_1]=\int z\cdot B(z)d\gamma_d(z)$ proves
$$
\int z\cdot B(z)d\gamma_d(z)-F\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt
=F\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt
=\lim_{\tau\uparrow1}M_\tau.
$$
Thus the endpoint and signed trace agree without having assumed this identity in any preceding estimate.

**3. A randomized finite terminal label.** On $\{f>0\}$ let
$$
\alpha_g=\frac{|\{i\in\mathcal R\cap I_0:v_i=w_g\}|}{V},\qquad
\eta=\frac H{h(u_R)}\in(0,1].
$$
Introduce an auxiliary random label $J\in\{0,1,\ldots,K\}$ conditional on the terminal Gaussian value by
$$
p_g(G)=\mathbb Q(J=g\mid G)=\eta\alpha_g\quad(g\ge1),\qquad p_0(G)=1-\eta.
$$
Off $\{f>0\}$ take $p_0=1,p_g=0$. Assign marks $c_0=0$ and $c_g=w_g/H$. Then, exactly,
$$
\mathbb E[c_J\mid G]=\sum_g\frac{\eta\alpha_g}H w_g=b(G),\qquad
\mathbb E\|c_J\|^2=H^{-2}\mathbb E_Q\eta\le H^{-2}.
$$
The auxiliary label is not revealed in the Brownian filtration; adding this terminal randomization changes none of $\mathbb Q,W,a,K,\beta$ or $M$.

Let $\mu_j=\mathbb E_Qp_j$. Drop any label with $\mu_j=0$, since then $fp_j=0$ almost everywhere. Every retained posterior is strictly positive before time one and is
$$
\pi_j(t,z)=\frac{P_{1-t}(fp_j)(z)}{P_{1-t}f(z)},\qquad
\pi_{j,t}=\mathbb E[p_j(W_1)\mid\mathcal F_t].
$$
Write $g_{j,t}=\nabla\log\pi_j(t,W_t)$. Quotient heat calculus gives
$$
d\pi_{j,t}=\pi_{j,t}g_{j,t}\cdot dZ_t,\qquad
\sum_j\pi_{j,t}g_{j,t}=0,\qquad
a_t=\sum_j\pi_{j,t}c_j.
$$
This invokes no Fisher-information hypothesis. Its required finite score energy follows from bounded finite-label entropy. Indeed, applying Itô to $\sum_j\pi_j\log\pi_j$ yields
$$
\mathbb E\sum_j\pi_{j,\tau}\log\pi_{j,\tau}-\sum_j\mu_j\log\mu_j
=\frac12\mathbb E\int_0^\tau\sum_j\pi_{j,t}\|g_{j,t}\|^2dt.
$$
For an explicit justification, first stop on $|W_t|\le n$ for $t\le\tau<1$. The retained posterior probabilities are bounded away from zero on that compact set, so ordinary smooth Itô calculus applies. Remove these stops using boundedness of $\sum\pi\log\pi\in[-\log(K+1),0]$ and monotone convergence of the energy. Finally let $\tau\uparrow1$. Each bounded posterior martingale converges to $p_j(W_1)$, and bounded entropy gives
$$
\mathbb E\int_0^1\sum_j\pi_{j,t}\|g_{j,t}\|^2dt
=2\left[\mathbb E_Q\sum_jp_j\log p_j-\sum_j\mu_j\log\mu_j\right]
=2I(J;G)\le2\log(K+1).
$$
In particular the terminal entropy is that of the conditional probabilities $p(G)$; the label itself is not asserted to be determined by $G$.

**4. Posterior covariance controls the trace.** Differentiating the finite mark average and using $\sum\pi g=0$ gives the exact matrix identity
$$
K_t=\sum_j\pi_{j,t}(c_j-a_t)\otimes g_{j,t}.
$$
Therefore, with $V_t=\sum_j\pi_{j,t}\|c_j-a_t\|^2$ and $J_t=\sum_j\pi_{j,t}\|g_{j,t}\|^2$,
$$
|\operatorname{tr}K_t|\le\sqrt{V_tJ_t}.
$$
The integrated mark variance has the needed coherence deficit, including any randomness in the actual rank:
$$
\mathbb E\int_0^1V_tdt
=\mathbb E\|c_J\|^2-\mathbb E\int_0^1\|a_t\|^2dt
=\frac{\mathbb E_Q\eta-x}{H^2}
\le\frac{1-x}{H^2}.
$$
Cauchy--Schwarz in time and probability, followed by the entropy calculation, now gives
$$
|M|\le F\mathbb E\int_0^1|\operatorname{tr}K_t|dt
\le\frac FH\sqrt{2\log(K+1)(1-x)}.
$$

**5. Uniform conversion to the target scale.** Whenever a true null in direction $w_g$ is rejected, its statistic obeys $\theta_i+w_g\cdot G\ge u_R\ge U$. Since $\theta_i\le0$, this implies $w_g\cdot G\ge U$. Hence
$$
F\le\mathbb P(V>0)\le\sum_{g=1}^K\mathbb P(w_g\cdot G\ge U)=Kq.
$$
There is no restriction on the alternative geometry in this union bound. For $1\le K\le3$ and $H\ge3$,
$$
M_+\le\frac{Kq}H\sqrt{2\log(K+1)(1-x)}
\le\sqrt{2\log4}\,q\sqrt{1-x}
<2q\sqrt{1-x}.
$$
Adding the nonnegative entropy-linear term preserves the claimed bound with $C=2$. All constants are uniform over the class; the argument uses no fixed $N$, fixed dimension, fixed covariance rank, or order of limits. It does not settle the unrestricted target with an unbounded number of true-null directions.

## Failure

NOT fails: randomized terminal Mills amplitude gives a label with at most four values, whose bounded posterior entropy controls the trace by the square-root coherence deficit uniformly over arbitrary finite models with at most three distinct true-null directions.
