---
type: candidate
title: >-
  Extremely imbalanced signed null clones give a divergent Mills trace to
  coherence-deficit ratio
status: survived
target_asset: gaussian_bh_entropy_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: pass
mode: refute
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:31:00.636Z'
extension_version: 0.0.4
---

## Object

This is a candidate counterfamily to the auxiliary entropy-coherence trace budget, not to either main FDR upper bound. In fact its actual FDR equals its nominal level exactly.

For each integer n at least 3, put
$$
q_n=\overline\Phi(n),\qquad
N_n=\left\lceil\frac{\overline\Phi(n)}{\overline\Phi(n^3)}\right\rceil,
\qquad p_n=\frac1{N_n}.
$$
Let d=1, let G be standard normal, set every mean to zero, and take N_n-1 statistics equal to G and one statistic equal to -G. Thus the unit loading vectors are N_n-1 copies of +1 and one copy of -1.

More generally, for a finite N at least 6 and q with U equal to the upper q quantile at least 3, write
$$
p=\frac1N,\qquad
a=\overline\Phi^{-1}(q(1-p)),\qquad
b=\overline\Phi^{-1}(qp),\qquad
H=h(U),\qquad
c_a=\frac1{h(a)},\quad c_b=\frac1{h(b)},\quad \ell=c_a+c_b.
$$
The argument below uses b at least 4a. The explicit n-family satisfies this condition.

This family differs essentially from the already excluded two-test antipodal family. Its two actual rejection ranks have multiplicities N-1 and 1; the two tail cutoffs have arbitrarily different sizes. The symmetric two-tail proof does not control this rare, distant branch.

## Checks

### H1

For each n, N_n and d=1 are finite positive integers and every loading has norm one. The covariance is the rank-one Gram matrix vv-transpose, where v has N_n-1 entries +1 and one entry -1. It is positive semidefinite with unit diagonal. The model is exactly jointly Gaussian; singularity is allowed.

### H2

Every original mean is zero, so every index is an original one-sided true null. No false-null label or positive-mean substitution is used.

### H3

Use the actual ordinary largest-rank BH rule at q. Since q is below one half, all qualifying statistics must be positive. On G positive, the negative-direction statistic cannot be rejected. The N-1 positive-direction statistics have equal p-values; if any rank inside that tied block qualifies, its endpoint rank N-1 qualifies. Thus their actual rejection count is N-1 precisely on G at least a. On G negative, only the negative-direction singleton can qualify, and it does so precisely on G at most -b. The rank N never qualifies because it would require both G and -G to exceed U positive. Therefore, up to endpoints which have Gaussian probability zero,
$$
R=(N-1)\mathbf1_{\{G\ge a\}}+\mathbf1_{\{G\le-b\}},
\qquad
f=\mathbf1_{\{G\ge a\}\cup\{G\le-b\}}.
$$
These statements retain all multiplicities and the prescribed non-strict inequalities. The exact field from the target definition is
$$
B(G)=b_{\rm term}(G)
=c_a\mathbf1_{\{G\ge a\}}-c_b\mathbf1_{\{G\le-b\}},
$$
where b_term denotes B/f on f positive.

### H4

The FDR is positive and exactly
$$
F=\overline\Phi(a)+\overline\Phi(b)
=q(1-p)+qp=q.
$$
Consequently Q is standard Gaussian conditioned on the disjoint two-tail event, its negative-branch probability is p, and
$$
D=D(Q\Vert\gamma_1)=\log(1/q).
$$
In the explicit family U_n=n, so q_n tends to zero. It therefore enters every positive universal q_0 interval. No fixed-dimension or fixed-covariance restriction is imposed by the target.

### H5

The heat fields are precisely those specified in the target. Write s=1-t and, at heat state z, put
$$
z_+=\frac{a-z}{\sqrt{s}},\qquad
z_-=\frac{b+z}{\sqrt{s}},\qquad
H_+=\overline\Phi(z_+),\quad
H_-=\overline\Phi(z_-),\qquad
\pi(t,z)=\frac{H_-}{H_++H_-}.
$$
Bayes' formula gives
$$
\pi_t=\mathbb Q(G\le-b\mid\mathcal F_t),\qquad
a_t=c_a-\ell\pi_t.
$$
Direct spatial differentiation, with the Jacobian convention in the target, yields
$$
K_t
=\ell\pi_t(1-\pi_t)
\frac{h(z_+)+h(z_-)}{\sqrt{1-t}}
\ge0.
$$
There is no terminal-face replacement in this identity.

All required quantities are finite. Indeed a_t is the bounded martingale
$$
a_t=\mathbb E_{\mathbb Q}[b_{\rm term}(W_1)\mid\mathcal F_t].
$$
For every cutoff t below one, the positive smooth Doob heat density gives the transformed generator one half of the second derivative plus the logarithmic heat derivative times the first derivative. Write tilde-W for its Brownian innovation, distinct from the canonical coordinate W. Itô's formula for a(t,W_t), or direct differentiation of its heat quotient, therefore gives da_t=K_t d(tilde-W_t). Applying the bounded-martingale square identity up to cutoffs and localization gives
$$
\mathbb E_{\mathbb Q}\int_0^1 K_t^2\,dt
\le \mathbb E_Q b_{\rm term}^2<\infty.
$$
Cauchy-Schwarz then gives absolute trace integrability on the unit time interval. Also |a_t| is at most c_a, which is smaller than 1/H, since a is larger than U. Hence x is finite and strictly below one. The field and covariance are one-dimensional throughout; no factor-dimension approximation is involved.

### NOT

We prove a diverging normalized positive trace, retaining the full heat trace.

First, some elementary normal-tail facts used below are recorded explicitly. The Mills ratio is increasing and has derivative between zero and one: the identity
$$
h'(u)=h(u)\{h(u)-u\}
=1-\operatorname{Var}(Z\mid Z\ge u)
$$
and the ordinary upper Mills bound give these facts for positive u. Also h(z) is at least z for every real z. For positive z this follows from the upper Mills bound; for nonpositive z it follows from positivity of h.

Since -log(1-p) is at most 2p for p at most one half,
$$
H(a-U)
\le\int_U^a h(y)\,dy
=-\log(1-p)\le2p,
$$
and therefore
$$
h(a)\le H+\frac{2p}{H},\qquad
Hc_a\ge1-\frac{2p}{H^2},\qquad Hc_b\le1.
$$
The terminal mean and the constant mean of its martingale satisfy
$$
H\mathbb E_Q b_{\rm term}
=H\{(1-p)c_a-pc_b\}
\ge1-2p-\frac{2p}{H^2}\ge1-3p.
$$
Here H is at least U at least 3. For p at most one sixth, this lower bound is positive. Jensen at each time gives the crucial upper bound on the actual integrated coherence deficit:
$$
x=H^2\int_0^1\mathbb E_{\mathbb Q}a_t^2\,dt
\ge H^2(\mathbb E_Q b_{\rm term})^2
\ge(1-3p)^2,
\qquad
0<1-x\le6p.
$$
This bound involves the full posterior process, not only a terminal norm.

For a lower bound on M, let Q_minus denote the path law conditioned on the negative terminal branch G at most -b. The posterior identity gives, for every nonnegative F_t-measurable function L_t,
$$
\mathbb E_{\mathbb Q}[\pi_t(1-\pi_t)L_t]
=p\,\mathbb E_{Q_{\rm minus}}[(1-\pi_t)L_t].
$$
Thus the exact nonnegative trace satisfies
$$
M=q\ell p\int_0^1
\mathbb E_{Q_{\rm minus}}\left[
(1-\pi_t)\frac{h(z_+)+h(z_-)}{\sqrt{1-t}}
\right]dt.
$$
Because h(z) is at least z on the whole line,
$$
\frac{h(z_+)+h(z_-)}{\sqrt{1-t}}
\ge\frac{a+b}{1-t}\ge b.
$$
Moreover, by monotonicity of the normal survival function,
$$
W_t\ge\frac{a-b}{2}
\quad\Longrightarrow\quad
H_+\ge H_-
\quad\Longrightarrow\quad
1-\pi_t\ge\frac12.
$$

The negative terminal branch has probability at least 1-exp(-1) of ending in the interval [-b-1/b,-b]. To see this without an asymptotic approximation, for every y at least b the density ratio at y+1/b and y is at most exp(-1-1/(2b^2)), so
$$
\frac{\overline\Phi(b+1/b)}{\overline\Phi(b)}
\le e^{-1}.
$$
Given a terminal g in that interval, W_t has its exact original Gaussian Brownian-bridge law, with mean tg and variance t(1-t). This remains true under the endpoint tilt. For every t between zero and one quarter, b at least 4a and a at least 3 imply
$$
tg\ge-\frac{b+1/b}{4}\ge\frac{a-b}{2}.
$$
The bridge therefore has probability at least one half to lie above (a-b)/2. Integrating over the indicated endpoint interval gives
$$
\mathbb P_{Q_{\rm minus}}\left(W_t\ge\frac{a-b}{2}\right)
\ge\frac{1-e^{-1}}2,\qquad
\mathbb E_{Q_{\rm minus}}(1-\pi_t)
\ge\frac{1-e^{-1}}4
\quad(0\le t\le1/4).
$$
Keeping this actual portion of the nonnegative trace integral gives
$$
M\ge\frac{1-e^{-1}}{16}\,q\ell p b
\ge\frac{1-e^{-1}}{32}\frac{qpb}{H}>0.
$$
The last inequality uses Hc_a at least one half, which follows from the earlier bound.

Combining this lower bound with the upper bound on 1-x and the exact entropy yields
$$
\frac{M_+}{q\sqrt{1+D}(1-x)}
\ge
\frac{1-e^{-1}}{192}\,
\frac{b}{H\sqrt{1+\log(1/q)}}.
$$

It remains to check the explicit finite n-family simultaneously satisfies all conditions and makes the last expression diverge. Normal density translation gives
$$
\frac{\overline\Phi(n^3)}{\overline\Phi(n)}
\le\exp\left\{-\frac{n^6-n^2}{2}\right\}.
$$
Hence N_n is at least 6 and p_n is at most one sixth for every n at least 3. By its defining ceiling,
$$
b_n=\overline\Phi^{-1}(q_n/N_n)\ge n^3.
$$
The preceding quantile-gap estimate also gives
$$
a_n\le n+\frac{2p_n}{H_n}\le n+\frac1{3n},
\qquad b_n\ge4a_n.
$$
Finally, integration by parts gives the lower Mills bound
$$
\overline\Phi(n)\ge\frac{\phi(n)n}{n^2+1},
\qquad H_n\le n+\frac1n\le2n,
$$
and
$$
D_n\le\frac{n^2}{2}
+\log\!\left(\sqrt{2\pi}\left(n+\frac1n\right)\right)
\le n^2\qquad(n\ge3).
$$
For the last elementary inequality, bound the logarithm's argument by (10/3)n, verify log(10) below 9/2 at n=3, and differentiate log((10/3)n)-n^2/2, whose derivative is negative for n at least 3. Thus sqrt(1+D_n) is at most 2n, and the normalized ratio is bounded below by
$$
\frac{M_{n,+}}{q_n\sqrt{1+D_n}(1-x_n)}
\ge\frac{1-e^{-1}}{768}\,n
\longrightarrow\infty.
$$
For every proposed finite universal C and every proposed positive q_0, take n large enough that this bound exceeds C and q_n is at most q_0. This violates the proposed auxiliary trace budget within its full Gaussian hypotheses. Its FDR is nevertheless F_n=q_n, so the construction does not refute the one-sided or two-sided universal-order FDR target.
