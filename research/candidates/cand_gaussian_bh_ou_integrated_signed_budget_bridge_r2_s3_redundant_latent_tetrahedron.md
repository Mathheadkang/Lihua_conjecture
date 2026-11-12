---
type: candidate
title: Rank-three tetrahedron with arbitrarily many unused latent coordinates
status: failed
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:02:23.534Z'
extension_version: 0.0.4
---

## Object

For every integer d>=3 and 0<q<=S(1), set N=4 and theta=(0,0,0,0). In the first three coordinates of R^d take
v_1=(1,1,1)/sqrt(3), v_2=(1,-1,-1)/sqrt(3),
v_3=(-1,1,-1)/sqrt(3), v_4=(-1,-1,1)/sqrt(3),
and append zeros in every remaining coordinate. Set T_i=v_i dot G, G standard Gaussian in R^d, and apply ordinary non-strict BH at q. All four hypotheses are null, so the full actual FDP is f=1_{R_q>0}. Let a=u(q)>=1 and
$$
k_3(a)=\mathbb E[(a-\|G_3\|)_+]
=\int_0^a\mathbb P(\|G_3\|<s)\,ds.
$$
This tests a rank-three singular model and the boundary operation of sending latent dimension to infinity through unused coordinates. It is not an antipodal block or a rank-at-most-two model.

## Checks

### H1

Pass. N=4 is a positive finite integer for every family member.

### H2

Pass. theta is finite and I_0=[4], pi_0=1.

### H3

Pass. The Gram matrix has diagonal 1 and every off-diagonal entry -1/3. Its eigenvalues are 0 once and 4/3 three times. Thus it is positive semidefinite, unit-diagonal, singular, and has actual rank three.

### H4

Pass. The family ranges over exactly 0<q<=S(1), including the upper endpoint. No q=0 model is asserted.

### H5

Pass. Every loading has norm one and the prescribed Gram matrix. Each d is finite. Adding unused coordinates changes neither the score vector nor its law.

### H6

Pass. Since all labels are null, f is precisely the original BH FDP, with no cutoff or altered rejection procedure. It depends only on the first three coordinates. Mehler averaging preserves that independence and its remaining spatial derivatives vanish, so F and the full signed J(f) equal their three-dimensional values for every d.

The following direct lower bound uses the gradient of the entire smoothed FDP, without replacing it by positive jumps. On ||x||<a all scores are <a; any nonzero BH rejection requires at least one score >=u(qR/4)>=a. Hence f=0 on that ball. Put psi_a(x)=(a-||x||)_+, which is bounded and 1-Lipschitz on R^3. Then f psi_a=0 and E psi_a=k_3(a).

Here is a direct justification of the needed covariance calculation, rather than an invocation of a draft rank-two observation. For t>0 write rho=e^{-t}, s=sqrt(1-rho^2). Differentiating the Gaussian convolution gives
$$
\nabla T_t f(x)=\frac{\rho}{s}\mathbb E[Y f(\rho x+sY)],
\qquad \|\nabla T_t f(x)\|\leq\sqrt3\frac{\rho}{s}.
$$
The derivative follows by differentiating its smooth Gaussian density; f is bounded. Thus J(f)<=sqrt(3) pi/2 is finite. For smooth test functions, Gaussian integration by parts and the OU generator give
$$
\frac{d}{dt}\mathbb E[(T_t f)\psi_a]
=-\mathbb E\langle\nabla T_t f,\nabla\psi_a\rangle.
$$
For psi_a this follows by ordinary smooth mollification, keeping the Lipschitz bound at most one, and passing to the limit. Integrate first over epsilon<=t<=M. This f is constant on cells cut by the finite hyperplane set T_i=u(qk/4), so its discontinuity set has Gaussian measure zero. Mehler coupling and bounded convergence give T_epsilon f -> f and T_M f -> F in L1 as epsilon decreases to zero and M increases to infinity. The displayed integrable gradient bound permits the limits on the right. Consequently
$$
-F k_3(a)=\operatorname{Cov}(f,\psi_a)
=\int_0^\infty\mathbb E\langle\nabla T_t f,\nabla\psi_a\rangle\,dt,
\qquad J(f)\geq F k_3(a).
$$
All norms here are taken after forming the full smoothed function; cancellation has been retained. The exact finite signed conditional-p-path identity, if denoting its four expected net charges by C_i, reads sum_i C_i=4(F/q-1). Positive conditional charges are separate quantities and are not evaluated or substituted for J in this test.

### H7

Pass. The event T_1>=u(q/4) has probability q/4. It forces at least one BH rejection, and every rejection is null. Thus F>=q/4>0. Moreover R_q>0 implies max_i T_i>=a, so the union bound gives F<=4S(a)=4q.

### NOT

Fail. Since k_3(a)>=k_3(1)>0,
$$
\frac{F(F-q)_+}{qJ(f)}
\leq\frac{F}{q k_3(a)}
\leq\frac4{k_3(1)}<\infty.
$$
This bound is independent of q and the arbitrarily large latent dimension d. Its denominator is positive by H7 and H6. Explicitly k_3(1)>=(1/2)P(||G_3||<=1/2)>=(pi/12)(2pi)^{-3/2}exp(-1/8)>0. Therefore no sequence in this family has unbounded ratio. This does not bound families whose actual rank and N both grow, and it makes no claim of a universal bridge.

## Failure

NOT fails: unused latent coordinates preserve the full signed OU budget, and the rank-three hole covariance bound keeps this family's ratio uniformly finite.
