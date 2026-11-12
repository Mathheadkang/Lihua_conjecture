---
type: candidate
title: Parallel composite nulls obey a stronger trace deficit bound
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
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:12:17.023Z'
extension_version: 0.0.4
---

## Object

For arbitrary finite integers \(N,d\ge1\), choose a unit vector \(v\in\mathbb R^d\), set \(v_i=v\) for every test, and allow arbitrary finite means \(\theta_i\le0\). Thus all hypotheses are true nulls, including genuinely negative null means, and the Gaussian covariance has rank one. Take any \(0<q\le\overline\Phi(3)\). These models test the singular-covariance, parallel-direction and composite-null edges simultaneously.

This entire family satisfies the stronger bound

$$
M_+\le \frac{3q}{H}(1-x)\le q(1-x)
      \le q\sqrt{1+D}(1-x).
$$

Consequently it cannot refute the target, even with parameters depending arbitrarily on \(q\). The \(N=1\) subfamily with \(\theta_1\to-\infty\) additionally approaches the excluded \(F=0\) boundary without violating the conclusion.

## Checks

### H1

The integers \(N,d\) are finite and positive; every \(v_i=v\) has norm one. With \(Y=v\cdot G\sim N(0,1)\), the exact joint Gaussian statistics are \(T_i=\theta_i+Y\), and \(\Sigma_{ij}=1\) is a unit-diagonal positive-semidefinite matrix. Singular covariance is permitted.

### H2

The testing level satisfies \(0<q\le\overline\Phi(3)\), so \(U=\overline\Phi^{-1}(q)\ge3\) and \(H=h(U)>U\ge3\). This covers a fixed universal small-\(q\) interval, rather than one finite level.

### H3

Sort the original means as \(\theta_{(1)}\ge\cdots\ge\theta_{(N)}\). The observed ordering is the same ordering for every \(Y\), including ties. Write \(u_r=\overline\Phi^{-1}(qr/N)\) as in the target and put

$$
A=\min_{1\le r\le N}\{u_r-\theta_{(r)}\}\ge U.
$$

The actual largest qualifying BH rank is exactly

$$
R(Y)=\max\bigl(\{0\}\cup
 \{r:Y\ge u_r-\theta_{(r)}\}\bigr).
$$

No rank or threshold is freely substituted. Because all original means are nonpositive, all rejected hypotheses are true nulls, and hence

$$
f(Y)=\mathbf1_{\{Y\ge A\}},\qquad F=\overline\Phi(A)\le q.
$$

Non-strict endpoint inequalities are the original BH inequalities and affect no Gaussian integral.

### H4

Every mean is finite, so \(A\) is finite and \(F=\overline\Phi(A)>0\). The terminal tilt is precisely the normal law conditioned on \(Y\ge A\), with independent unaffected orthogonal Gaussian coordinates. Thus \(D=\log(1/F)<\infty\).

### H5

All heat fields are the target's actual fields, not a proxy. On \(\{Y\ge A\}\), the sum of the rejected null vectors is \(R(Y)v\), so

$$
b(Y)=B(Y)=\frac{v}{h(u_{R(Y)})}.
$$

Define, only on this terminal support,

$$
\eta(Y)=1-\frac{H}{h(u_{R(Y)})}\in[0,1],
\qquad \overline\eta=\mathbb E_Q\eta.
$$

Let \(Y_t=v\cdot W_t\), and let
\(\pi_t=\mathbb E_{\mathbb Q}[\eta(Y_1)\mid\mathcal F_t]\).
All orthogonal coordinates factor out of the scalar and vector heat convolutions. Therefore the exact heat-posterior vector is

$$
a_t=\frac{v}{H}(1-\pi_t),\qquad
\operatorname{tr}K_t=-\frac{\kappa_t}{H},
\qquad
\kappa_t=\left.\partial_y
\mathbb E_{\mathbb Q}[\eta(Y_1)\mid Y_t=y]\right|_{y=Y_t}.
$$

For completeness, the path tilt in this model has scalar density martingale

$$
\ell_t=\frac{\overline\Phi((A-Y_t)/\sqrt{1-t})}{F},
\qquad
\beta_t=\frac{h((A-Y_t)/\sqrt{1-t})}{\sqrt{1-t}}.
$$

Itô differentiation gives \(d\ell_t=\ell_t\beta_t\,dY_t\) under Wiener measure. Girsanov at finite cutoffs gives
\(dY_t=d\widetilde W_t+\beta_t\,dt\) under \(\mathbb Q\). The entropy identity follows by Itô differentiation of \(\log\ell_t\):

$$
\frac12\mathbb E_{\mathbb Q}\int_0^1\beta_t^2\,dt
=\log(1/F).
$$

The endpoint passage is legitimate: \(0\le\ell_t\le1/F\), the continuous function \(z\log z\) is bounded on this compact interval, and the density martingale converges to \(\mathbf1_{\{Y_1\ge A\}}/F\). Thus the finite-cutoff entropies converge by dominated convergence, while the nonnegative energy integral converges monotonically.

The conditional-expectation quotient defining \(\pi\) satisfies the backward equation with drift \(\beta\); its Itô differential is
\(d\pi_t=\kappa_t\,d\widetilde W_t\).
Since \(\eta\) is bounded, the bounded martingale identity gives

$$
\mathbb E_{\mathbb Q}\int_0^1\kappa_t^2\,dt
=\operatorname{Var}_Q(\eta)\le1.
$$

Cauchy--Schwarz therefore yields
\(\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt<\infty\).
Also \(0\le\pi_t\le1\), so the actual coherence is finite and belongs to \([0,1]\):

$$
x=\mathbb E_{\mathbb Q}\int_0^1(1-\pi_t)^2dt,\qquad
1-x
=\mathbb E_{\mathbb Q}\int_0^1(2\pi_t-\pi_t^2)dt
\ge \overline\eta.
$$

All integrations here use the original terminal and path tilts. There is no independence assumption among the tests.

### NOT

This check fails: a uniform stronger estimate holds throughout the proposed family.

First, Itô's product rule for \(Y_t\pi_t\) gives

$$
\mathbb E_Q[Y_1\eta(Y_1)]
=\mathbb E_{\mathbb Q}\int_0^1\pi_t\beta_t\,dt
 +\mathbb E_{\mathbb Q}\int_0^1\kappa_t\,dt.
$$

The finite-energy and bounded-martingale estimates in H5 justify the products and the endpoint limit by localization and Cauchy--Schwarz. Because \(\beta_t\) is adapted and \(\pi_t\) is the conditional mean of \(\eta(Y_1)\), this is equivalent to the exact trace identity

$$
M=\frac{F}{H}\mathbb E_{\mathbb Q}
\left[\eta(Y_1)
\left\{\int_0^1\beta_t\,dt-Y_1\right\}\right].
$$

We next bound the conditional drift integral uniformly at every terminal point \(g\ge A\). The tilt depends only on the terminal event, so the conditional law of the path given \(Y_1=g\) is an ordinary Brownian bridge. At time \(t\) its scalar coordinate has the representation

$$
Y_t=tg+\sqrt{t(1-t)}Z,\qquad Z\sim N(0,1).
$$

The Mills ratio is increasing and satisfies \(h(z)\le z_++h(0)\) for every real \(z\). Indeed \(h'=h(h-z)>0\), and the positive conditional variance of a truncated normal equals \(1-h'(z)\), so \(h'<1\); for \(z\ge0\), \(h(z)-z\le h(0)\), while for \(z\le0\), \(h(z)\le h(0)\).

The bridge with endpoint \(g\ge A\) has a pointwise larger time-\(t\) location, under this coupling, than the bridge with endpoint \(A\). Since \(\beta(t,y)\) decreases in \(y\),

$$
\mathbb E_{\mathbb Q}[\beta_t\mid Y_1=g]
\le
\frac{\mathbb E\,h(A\sqrt{1-t}-\sqrt t\,Z)}{\sqrt{1-t}}
\le
A+\frac{\sqrt t}{\sqrt{2\pi}\sqrt{1-t}}
 +\frac{h(0)}{\sqrt{1-t}}.
$$

Tonelli's theorem applies because the drift is nonnegative. Integration gives

$$
\mathbb E_{\mathbb Q}\left[
\left.\int_0^1\beta_tdt\right|Y_1=g\right]
\le A+\frac{\pi}{2\sqrt{2\pi}}+2\sqrt{\frac2\pi}
<A+3.
$$

Consequently the conditional expectation of
\(\int_0^1\beta_tdt-Y_1\), given \(Y_1=g\ge A\), is at most \(3\).
Since \(\eta\ge0\) depends only on \(Y_1\), the exact trace identity and H5 imply

$$
M_+\le\frac{3F}{H}\overline\eta
\le\frac{3q}{H}(1-x)
\le q(1-x)
\le q\sqrt{1+D}(1-x).
$$

This is a bound with \(C=1\) on the whole interval \(0<q\le\overline\Phi(3)\), independent of every dimension, mean and rank parameter. If \(\eta=0\), then \(a_t=v/H\), \(x=1\) and \(M=0\) exactly. In particular \(N=1\) has this exact behavior for every finite negative mean, even as that mean tends to minus infinity and \(F\downarrow0\).

## Failure

NOT fails: every all-null parallel Gaussian model with arbitrary nonpositive means satisfies the stronger uniform estimate \(M_+\le(3q/H)(1-x)\). Singular rank-one covariance and negative-null-mean limits in this family do not produce a counterexample.
