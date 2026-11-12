---
type: candidate
title: Identical true nulls at the maximal-coherence boundary
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
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T09:57:49.237Z'
extension_version: 0.0.4
---

## Object

Choose any finite positive integer N, let d=1, put v_i=1 for every i, and let every mean equal the same finite theta <= 0. Choose any 0<q<=barPhi(3). Write U=barPhi^{-1}(q), H=h(U), and c=U-theta. The covariance is the all-ones matrix, of rank one. All p-values coincide. This family includes arbitrary duplication, the zero-mean boundary, strictly negative null means, and limits F tending to zero through theta tending to minus infinity.

## Checks

### H1

The chosen q is positive and at most barPhi(3); in particular U>=3. The calculations below hold for every such q and hence for every possible smaller universal q_0.

### H2

N and d=1 are positive finite integers.

### H3

Each mean is finite and real and every v_i=1 has Euclidean norm one. The covariance is positive semidefinite with unit diagonal, including the permitted singular case N>1.

### H4

Use exactly the specified one-sided p-values and ordinary largest-rank BH rule. All coordinates are true nulls. Because every p-value equals barPhi(theta+z), BH rejects every coordinate if this common value is at most q, and otherwise rejects none: if any rank qualifies, rank N qualifies. Thus

$$
R(z)=V(z)=N1_{\{z\ge c\}},\qquad f(z)=1_{\{z\ge c\}},\qquad B(z)=H^{-1}1_{\{z\ge c\}}.
$$

The non-strict boundary at z=c has Gaussian measure zero and is included as prescribed.

### H5

The tilted-measure applicability condition holds:

$$
F=\overline\Phi(c)>0.
$$

### NOT

The proposed conclusion does not fail. In fact all well-posedness assertions and the estimate hold exactly in this family.

The density of Q is 1_{[c,infinity)}/F, so D=log(1/F), which is finite. Since B=f/H, heat convolution gives

$$
a(t,z)=H^{-1},\qquad K_t=0,\qquad x=H^2\int_0^1H^{-2}dt=1.
$$

For completeness, writing s=1-t, the scalar heat field and its logarithmic derivative are

$$
\mathcal H(t,z)=\overline\Phi((c-z)/\sqrt s),\qquad
\beta(t,z)=s^{-1/2}h((c-z)/\sqrt s)>0.
$$

The Doob transform for conditioning W_1>=c has drift beta. Its entropy-energy identity is

$$
\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt=2\log(1/F)<\infty.
$$

One can obtain this directly by applying Ito's formula to log(mathcal H(t,W_t)/F) under the conditional law: its drift is beta_t^2/2; the expected logarithm increases to log(1/F). Indeed the terminal conditional density is bounded by 1/F, and the heat density martingale converges to 1/F under the conditional law. Localization, followed by entropy convergence for this bounded density, justifies the identity. Consequently the absolute drift integral is finite by Cauchy-Schwarz, while the absolute trace integral is zero. The conditional Brownian decomposition, with the finite-energy drift, also yields

$$
\mathbb E_{\mathbb Q}\int_0^1\beta_tdt=\mathbb E_QZ=h(c).
$$

Both terms in the required endpoint identity are therefore finite and equal:

$$
\int zB(z)\gamma_1(dz)=\frac{\phi(c)}H
=\frac{Fh(c)}H
=F\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt.
$$

Thus M_*=0=M_tau=M, including the asserted signed-trace identification and absolute integrability. Finally M_+=0 and 1-x=0, so the mixed budget is 0<=0 for every C>0. Allowing N, theta, or q to vary cannot turn this exact equality into a violation.

## Failure

NOT fails: arbitrary identical null multiplicities have maximal coherence x=1 but the heat posterior is constant, forcing M=0 exactly.
