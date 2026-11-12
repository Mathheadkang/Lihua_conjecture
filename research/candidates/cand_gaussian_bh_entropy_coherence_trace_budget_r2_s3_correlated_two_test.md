---
type: candidate
title: All correlated two-test one-null models satisfy a stronger trace-deficit bound
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
slot: 3
direction: idea_19c44519bec3
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:21:01.191Z'
extension_version: 0.0.4
---

# All correlated two-test one-null models satisfy a stronger trace-deficit bound

## Object

This tests the unfinished strong-alternative family in [the saved two-test stress test](../ideas/idea_19c44519bec3.md), including arbitrary level-dependent parameters. In fact the calculation covers its entire correlated composite-null extension, rather than merely one large-alternative limit.

Fix any \(0<q\le\overline\Phi(3)\), any finite \(\theta_0\le0\), any finite \(\mu>0\), and any \(-1\le\rho\le1\). Let \(G=(G_1,G_2)\) be standard two-dimensional Gaussian and set
$$
N=d=2,\qquad v_1=e_1,\qquad
v_2=\rho e_1+\sqrt{1-\rho^2}\,e_2,\qquad
T_1=\theta_0+G_1,\qquad T_2=\mu+v_2\cdot G.
$$
Use the actual ordinary one-sided BH rule. Write
$$
u_1=\overline\Phi^{-1}(q/2),\qquad u_2=U=\overline\Phi^{-1}(q),\qquad
A=u_1-\theta_0,\qquad B_0=U-\theta_0,
$$
$$
c_j=\frac1{h(u_j)},\qquad H=h(U),\qquad
d_0=c_2-c_1>0,\qquad \delta=Hd_0\in(0,1).
$$
The letter \(B_0\) denotes a scalar cutoff and is distinct from the target's vector field \(B\). Define the exact terminal cells
$$
\mathcal A=\{G_1\ge A,\ T_2<U\},\qquad
\mathcal C=\{G_1\ge B_0,\ T_2\ge U\}.
$$
No assertion below substitutes a terminal alternative facet for the complete heat trace.

## Checks

### H1

Both loading vectors have norm one, so this is an exactly jointly Gaussian finite model with unit-diagonal positive-semidefinite covariance
$$
\Sigma=\begin{pmatrix}1&\rho\\\rho&1\end{pmatrix}.
$$
The endpoints \(\rho=\pm1\) are admissible singular cases; the latent realization above remains valid there.

### H2

The original null set is exactly \(\{1\}\), since \(\theta_0\le0<\mu\). All chosen levels satisfy the candidate's required small-level domain. Every parameter may vary with \(q\); all estimates below are uniform in these choices.

### H3

The largest-rank rule gives \(R=2\) precisely when both statistics are at least \(U\). If the true null is selected with only one rejection, its statistic is at least \(u_1\) and the alternative is below \(U\). Consequently the actual FDP and vector field, at every latent point, are
$$
f=\mathbf1_{\mathcal A}+\frac12\mathbf1_{\mathcal C},\qquad
B=e_1\left(c_1\mathbf1_{\mathcal A}+\frac{c_2}{2}\mathbf1_{\mathcal C}\right).
$$
In particular,
$$
f=0\quad\hbox{when }G_1<B_0,\qquad
\frac12\le f\le1\quad\hbox{when }G_1\ge A.
$$
On \(B_0\le G_1<A\), its only possible values are \(0\) and \(1/2\). These assertions retain all threshold equalities and the original means. They use no conditional independence of the two statistics.

### H4

The last pointwise bounds imply
$$
0<\frac12\overline\Phi(A)\le F=\mathbb Ef
\le\mathbb P(G_1\ge B_0)\le q.
$$
Thus the terminal and path tilts in the stated definition exist. Put
$$
p=Q(\mathcal A),\qquad
\pi_t=\mathbb E_{\mathbb Q}[\mathbf1_{\mathcal A}(W_1)\mid\mathcal F_t].
$$
The terminal field and its complete heat posterior are exactly
$$
b=e_1(c_2-d_0\mathbf1_{\mathcal A}),\qquad
a_t=e_1(c_2-d_0\pi_t).
$$
This follows by Bayes' rule from \(B=fb\), including when one of the cells has zero probability.

### H5

Here \(f\) takes only \(0,1/2,1\). Hence
$$
0\le D=D(Q\Vert\gamma_2)\le\log(1/F)<\infty.
$$
For clarity, the stochastic identities needed below can be established directly for these bounded terminal functions. Let
$$
\beta_t=\nabla\log(P_{1-t}f)(W_t).
$$
Apply Itô's formula to the bounded density martingale
\(P_{1-t}f(W_t)/F\), localizing before its logarithm approaches zero. Applying the same formula to its entropy gives
$$
\frac12\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2\,dt=D.
$$
The cutoff identities pass to time one by monotonicity of the density-martingale entropy and its finite terminal value; equivalently the terminal density is bounded and its \(r\log r\) is integrable. Girsanov's formula on every cutoff then shows that
$$
\mathcal W_t=W_t-\int_0^t\beta_s\,ds
$$
is Brownian motion under \(\mathbb Q\). Finite drift energy makes its time-one limit exist in \(L^2\), so \(\mathbb E_{\mathbb Q}\mathcal W_1=0\). The heat quotient and Itô's formula give
$$
a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t],\qquad
da_t=K_t\,d\mathcal W_t.
$$
The bounded terminal field makes this an \(L^2\) martingale. Consequently
$$
\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\mathrm{HS}}^2\,dt
=\mathbb E_Q\|b\|^2-\|\mathbb E_Qb\|^2\le c_2^2.
$$
Only the first row of \(K\) can be nonzero. Cauchy--Schwarz therefore implies
$$
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|\,dt
\le
\left(\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\mathrm{HS}}^2\,dt\right)^{1/2}
<\infty.
$$
Also \(0\le x\le H^2c_2^2=1\). Thus all the target's finiteness assertions hold in this family.

The cross-isometry of the two \(L^2\) stochastic integrals \(a_t-a_0\) and \(\mathcal W_t\), followed by their \(L^2\) terminal limits, gives the complete signed trace identity
$$
M=F\mathbb E_Q[b(W_1)\cdot\mathcal W_1]
=-Fd_0\mathbb E_{\mathbb Q}
 [\mathbf1_{\mathcal A}(W_1)\mathcal W_{1,1}].
$$
If \(p>0\), this is
$$
M=Fd_0p\,\mathbb E_{\mathbb Q}
\left[\left.\int_0^1\beta_{t,1}\,dt-G_1\,\right|\,W_1\in\mathcal A\right].
$$
If \(p=0\), \(a_t=c_2e_1\) is constant and \(M=0\). No sign of an individual terminal face was used.

Finally, the posterior martingale formula gives an exact deficit expression:
$$
1-x=2\delta p-\delta^2\int_0^1
\mathbb E_{\mathbb Q}\pi_t^2\,dt
\ge\delta(2-\delta)p,
$$
because \(0\le\pi_t\le1\) and \(\mathbb E_{\mathbb Q}\pi_t=p\).

### NOT

This check fails throughout the stated family. A bounded-reweighting comparison and a conditional Brownian bridge bound give, uniformly in all its parameters,
$$
\boxed{\quad M_+\le\frac{4q}{H}(1-x).\quad}
$$
The complete argument is as follows.

Fix \(t<1\), a current latent point \(z\), and write \(\sigma=\sqrt{1-t}\). Under the unweighted remaining Gaussian law, its first terminal coordinate \(Z\) has law \(N(z_1,\sigma^2)\). Integrate \(f(Z,G_2)\) over the remaining second coordinate to obtain a scalar weight \(w(Z)\). By H3, \(1/2\le w(u)\le1\) for \(u\ge A\), and \(w\ge0\) everywhere. Any mass below \(A\) has first coordinate at most \(A\); its addition can only decrease the mean of the weighted law restricted to \(Z\ge A\).

Let \(\nu\) be \(N(z_1,\sigma^2)\) conditioned on \(Z\ge A\). It has mean
$$
m_A=z_1+\sigma h(k),\qquad k=(A-z_1)/\sigma,
$$
and variance at most \(\sigma^2\). Indeed its variance is
\(\sigma^2\{1+k h(k)-h(k)^2\}=\sigma^2\{1-h'(k)\}\le\sigma^2\), since \(h'(k)=h(k)(h(k)-k)>0\).
On this tail the normalized bounded reweighting satisfies
$$
\frac{\mathbb E_\nu[w(Z)Z]}{\mathbb E_\nu w(Z)}-m_A
=\frac{\mathbb E_\nu[(w(Z)-3/4)(Z-m_A)]}
       {\mathbb E_\nu w(Z)}
\le\frac{\sigma}{2}.
$$
Here \(|w-3/4|\le1/4\), \(\mathbb E_\nu w\ge1/2\), and
\(\mathbb E_\nu|Z-m_A|\le\sigma\). After adding any lower-coordinate mass, the full weighted terminal mean remains at most \(m_A+\sigma/2\). Differentiating the scalar Gaussian convolution therefore gives the pointwise bound on the full marginal drift:
$$
\beta_1(t,z)
=\frac{\mathbb E[Zf\mid W_t=z]/\mathbb E[f\mid W_t=z]-z_1}{\sigma^2}
\le\frac{h((A-z_1)/\sigma)}{\sigma}
  +\frac{1}{2\sigma}.
$$
This step does not impose any sign or magnitude assumption on the alternative's covariance, and it remains valid at the singular endpoints.

Given a terminal latent point \(g\), the path law under \(\mathbb Q\) is the original Gaussian Brownian bridge to \(g\), because the change of measure depends only on the terminal point. For \(g\in\mathcal A\), \(g_1\ge A\), and
$$
W_{t,1}=tg_1+\sqrt{t(1-t)}\,Z_0,\qquad Z_0\sim N(0,1).
$$
The Mills ratio is increasing, and \(h(y)\le y_++h(0)\). The latter follows from \(0<h'(y)<1\), using the same truncated-normal variance formula for the upper derivative bound. Since \(A>0\), these facts imply
$$
\mathbb E\left[\left.
\frac{h((A-W_{t,1})/\sqrt{1-t})}{\sqrt{1-t}}
\right|W_1=g\right]
\le A+\frac{h(0)(1+\sqrt t)}{\sqrt{1-t}}.
$$
Integrating \(t\in(0,1)\) yields
$$
\mathbb E\left[\left.\int_0^1\beta_{t,1}\,dt\right|W_1=g\right]
\le A+h(0)(2+\pi/2)+1<A+4\le g_1+4.
$$
Conditional integrability holds for \(Q\)-almost every \(g\) by the finite drift energy in H5, so the conditional bound can be integrated over \(\mathcal A\). Substituting into the exact trace identity gives
$$
M_+\le4Fd_0p
\le\frac{4F}{H(2-\delta)}(1-x)
\le\frac{4q}{H}(1-x).
$$
When \(p=0\) this also holds since \(M=0\). On the allowed interval \(H\ge U\ge3\), this implies the proposed inequality with the fixed universal choice \(C=2\), since \(D\ge0\). It therefore excludes every diverging-alternative or correlation-endpoint sequence within this family, including parameters chosen jointly with \(q\).

This is a scoped analytic exclusion of a candidate family, not an independent proof verification of the target lemma and not an assertion for more than two tests or multiple true null directions.

## Failure

NOT fails: the complete correlated two-test, one-composite-null family satisfies \(M_+\le(4q/H)(1-x)\), uniformly over the positive alternative mean, all correlations including singular endpoints, and all allowed levels; it cannot refute the proposed entropy-amplified trace budget.
