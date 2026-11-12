---
type: candidate
title: Two true nulls with arbitrary nonpositive Gaussian correlation
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
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:21:01.191Z'
extension_version: 0.0.4
---

## Object

For every \(0<q\le\overline\Phi(3)\) and \(-1\le\rho\le0\), take \(N=d=2\), \(\theta=(0,0)\), \(v_1=(1,0)\), \(v_2=(\rho,\sqrt{1-\rho^2})\), and \(T_i=v_i\cdot G\) for standard Gaussian \(G\in\mathbb R^2\). Write \(X_i=T_i\),
\[
 U=\overline\Phi^{-1}(q),\quad
 a=\overline\Phi^{-1}(q/2),\quad H=h(U),\quad h_a=h(a).
\]
Both coordinates are original true nulls. This is the familiar nonpositive-Gaussian-dependence stress family for uncorrected BH; no assertion that its FDR exceeds \(q\) is needed here.

This extends, rather than reuses, the earlier antipodal candidate. For \(\rho=-1\) the actual rank-two cell is empty; for every \(-1<\rho\le0\) it has positive Gaussian probability and supplies a third posterior state and a different vector \(b\). The earlier binary-tail calculation cannot simply be transferred. The ternary conditional-information calculation below controls this additional state uniformly.

## Checks

### H1

The displayed vectors have unit norm, so their Gram matrix is the unit-diagonal PSD matrix with off-diagonal \(\rho\). At \(\rho=-1\) its singularity is permitted. For every \(q,\rho\) the model has finite dimension and finite means, with no non-Gaussian randomization.

### H2

The original true-null set is \(\{1,2\}\). Ordinary largest-rank BH, including its non-strict inequalities, has the following disjoint rejection cells, up to null boundaries:
\[
 C_1=\{X_1\ge a,\ X_2<U\},\quad
 C_2=\{X_2\ge a,\ X_1<U\},\quad
 C_{12}=\{X_1\ge U,\ X_2\ge U\}.
\]
The first two cells have actual rank one, and the third has actual rank two. Off their union \(S\), BH rejects nothing. Thus \(f=\mathbf1_S\), \(F=\Pr(S)\), and \(Q=\gamma_2(\,\cdot\mid S)\).

For later estimates, nonpositive Gaussian correlation gives
\[
 \Pr(X_1\ge s,X_2\ge t)
 \le\overline\Phi(s)\overline\Phi(t)
 \qquad(s,t\in\mathbb R).
\]
For \(-1<\rho\le0\), condition on \(X_1=x\). The conditional upper-tail probability of \(X_2\ge t\) is nonincreasing in \(x\). Its covariance with the increasing indicator \(\mathbf1_{\{x\ge s\}}\) is nonpositive: this follows by expanding the expectation of
\((g(X_1)-g(X'_1))(\mathbf1_{\{X_1\ge s\}}-\mathbf1_{\{X'_1\ge s\}})\le0\)
for an independent copy \(X'_1\). The endpoint \(\rho=-1\) follows either directly or by Gaussian weak convergence. Consequently
\[
 q/2\le F\le q+q^2\le2q.
\]
The lower bound holds because \(X_1\ge a\) always forces some rejection. The upper bound is the union bound over \(X_1\ge a\), \(X_2\ge a\), and \(C_{12}\).

### H3

The range of \(q\) is exactly within the proposed small-level range, \(U\ge3\), and \(F>0\). The terminal tilt has finite relative entropy
\[
 D=\log(1/F).
\]
Since \(F\le2q=4\overline\Phi(a)\le4\phi(a)/a\) and \(a\ge3\),
\[
 D\ge a^2/2+\log(a\sqrt{2\pi}/4)\ge a^2/2.
\]
All assertions are uniform if \(\rho\) varies arbitrarily with \(q\).

### H4

The terminal field \(b=B/f\), with the conventions of the target definition, is constant on each nonempty cell:
\[
 b_1=v_1/h_a,\quad b_2=v_2/h_a,\quad
 b_{12}=(v_1+v_2)/(2H).
\]
All have norm at most \(1/H\). Empty cells, including \(C_{12}\) at \(\rho=-1\), are omitted from the formulas below.

Let \(\pi_j(t,W_t)=\mathbb Q(W_1\in C_j\mid\mathcal F_t)\). It is the ratio of the Gaussian heat probability of \(C_j\) to that of \(S\), exactly under the target path tilt. Therefore
\[
 a_t=\sum_j\pi_j b_j,\qquad
 \operatorname{tr}K_t
 =\sum_j\pi_j(b_j-a_t)\cdot\nabla\log\pi_j.
\]
These are spatial heat derivatives, not derivatives of sample paths.

For completeness the conditional-information identity used here is
\[
 \mathbb E_{\mathbb Q}\int_0^1
   \sum_j\pi_j\|\nabla\log\pi_j\|^2\,dt
   =2\,\mathcal E,\qquad
 \mathcal E=-\sum_j\pi_j(0)\log\pi_j(0)\le\log3.
\]
Indeed put \(\mathcal H(t,z)=P_{1-t}\mathbf1_S(z)\). For \(t<1\), the Doob heat transform has drift \(\nabla\log\mathcal H\); the quotient rule for heat solutions shows that each \(\pi_j\) has zero drift under this transform and spatial diffusion coefficient \(\nabla\pi_j\). Apply Itô's formula to \(\sum_j\pi_j\log\pi_j\), first on compact spatial sets and with \(\pi_j\) bounded away from zero. Its finite-variation term is one half the displayed nonnegative integrand. Let the localizations exhaust, using the bounded finite-state entropy and then monotone convergence. As \(t\uparrow1\), the conditional probabilities converge to the actual cell indicators, so the terminal entropy is zero. This gives the equality. The finite terminal relative entropy permits the Doob transform on every interval \(t\le\tau<1\); nothing asserts that \(W\) itself is Brownian under \(\mathbb Q\).

Write
\[
 \mathcal A=\mathbb E_{\mathbb Q}\int_0^1
       \sum_j\pi_j\|b_j-a_t\|^2dt
   =\mathbb E_{\mathbb Q}\int_0^1
       \|b(W_1)-a_t\|^2dt.
\]
Pointwise Cauchy--Schwarz in the finite states, then Cauchy--Schwarz over path and time, gives
\[
 \mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt
 \le\sqrt{2\mathcal E\mathcal A}.
\]
Thus any upper bound for \(\mathcal A\) proves the required absolute integrability as well as the signed-trace estimate.

Here is a finite Gaussian-bridge estimate for that variance. Let
\[
 e=(v_1-v_2)/\|v_1-v_2\|,\qquad
 \widehat b_t=
 \begin{cases}b_1,&e\cdot W_t\ge0,\\ b_2,&e\cdot W_t<0.\end{cases}
\]
Call \(C_{12}\) bad, and also call a rank-one endpoint bad if its other coordinate exceeds \(a/2\). The joint-tail bound above gives
\[
 \Pr_Q(\mathrm{bad})
 \le\frac{q\,\overline\Phi(a/2)+q^2}{F}
 \le2\overline\Phi(a/2)+2q\le12/a^2.
\]
The last inequality only uses \(\overline\Phi(z)\le1/z^2\) for \(z>0\) and \(q=2\overline\Phi(a)\); no independence is imposed.

At a good \(C_1\) endpoint \(g\),
\[
 e\cdot g=\frac{X_1-X_2}{\sqrt{2(1-\rho)}}\ge a/4.
\]
At a good \(C_2\) endpoint it is at most \(-a/4\). Conditional on \(W_1=g\), the path under \(\mathbb Q\) is the original Gaussian Brownian bridge, since the tilt depends only on the endpoint. For \(0<t<1\) the wrong-sign probability is therefore at most
\[
 \overline\Phi\!\left({a\over4}\sqrt{t/(1-t)}\right)
 \le\exp(-a^2t/32).
\]
Both a wrong decision and a bad endpoint cost at most \(4/H^2\) in squared norm. Conditional expectation minimizes squared error, so
\[
 \mathcal A
 \le\mathbb E_{\mathbb Q}\int_0^1
       \|b(W_1)-\widehat b_t\|^2dt
 \le {4\over H^2}\left({12\over a^2}
       +\int_0^1e^{-a^2t/32}dt\right)
 \le {176\over H^2a^2}.
\]
In particular \(M\) exists with the exact target cutoff convention, and
\[
 |M|\le {F\sqrt{352\log3}\over Ha}
       \le {40q\over Ha}.
\]
Also \(0\le x\le1\), since \(a_t\) is a conditional average of vectors with norm at most \(1/H\).

### H5

A lower bound for the actual coherence deficit is needed; the trace bound alone would not exclude a counterexample.

Jensen's inequality for \(a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]\) gives
\[
 1-x\ge1-H^2\mathbb E_Q\|b\|^2
 \ge\min\{1-(H/h_a)^2,\ 1/2\}.
\]
To bound the first term without invoking an unverified result, let \(Z_u\) be a standard normal conditioned to be at least \(u>0\). Its excess satisfies
\[
 \Pr(Z_u-u\ge z)
 ={\overline\Phi(u+z)\over\overline\Phi(u)}
 \le e^{-uz}\quad(z\ge0).
\]
Consequently \(\operatorname{Var}(Z_u)\le\mathbb E(Z_u-u)^2\le2/u^2\). Direct differentiation of the Gaussian tail and its first two truncated moments gives
\[
 h'(u)=1-\operatorname{Var}(Z_u)\ge1-2/u^2\ge7/9
 \quad(u\ge3).
\]
Integration by parts also gives \(u\le h(u)\le u+1/u\). Hence
\[
 \log2=\int_U^a h(u)\,du\le h_a(a-U),\qquad
 h_a\le(10/9)a,
\]
and therefore
\[
 1-H/h_a={h_a-H\over h_a}
 \ge {7(a-U)\over9h_a}
 \ge {63\log2\over100a^2}.
\]
Putting \(c_*=63\log2/100\), which satisfies \(c_*/a^2<1/2\), we obtain
\[
 1-x\ge c_*/a^2.
\]
This includes the singular endpoint and permits arbitrary \(q\)-dependent nonpositive correlations.

### NOT

NOT fails for the whole family. Combining H3--H5 and \(H\ge U\ge3\),
\[
 {M_+\over q\sqrt{1+D}(1-x)}
 \le {40q/(Ha)\over q(a/\sqrt2)c_*/a^2}
 ={40\sqrt2\over Hc_*}<100.
\]
Thus one universal choice \(C=100\), on the entire proposed small-level interval, bounds every model of this family. It cannot make the normalized positive trace diverge. The additional positive-probability rank-two cell does not repair the earlier antipodal candidate into a counterexample.

This scoped analytic exclusion is not a proof of the target in models with alternatives, positive correlations or growing numbers of directions. In particular it gives no sign or matching asymptotic rate for the unresolved correlated strong-alternative test case.

## Failure

NOT fails: the entire two-null, nonpositive-correlation Gaussian family, including its actual rank-two third posterior state, satisfies the candidate budget with the uniform constant \(C=100\).
