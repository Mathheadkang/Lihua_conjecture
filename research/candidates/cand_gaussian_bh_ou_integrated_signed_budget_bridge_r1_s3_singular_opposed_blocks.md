---
type: candidate
title: Singular opposed blocks with imbalanced labels and negative-null boundary
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
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T21:56:18.237Z'
extension_version: 0.0.4
---

## Object

Let integers N >= 2 and 1 <= n < N vary, and put p=n/N. Let 0<q<=S(1), delta>=0, b=u(q), and c=u(qp). On G~N(0,1), take n identical null scores G-delta and N-n identical alternative scores b+c+delta-G. This pushes singular covariance, simultaneous ties, negative null means approaching zero, and arbitrarily imbalanced labels to their allowed edges. All parameters, including N and delta, may vary with q.

## Checks

### H1

N is finite and positive for every family member.

### H2

The mean vector is real: n entries equal -delta<=0 and N-n entries equal b+c+delta>0. Thus the true-null set is precisely the first n coordinates, and pi_0=p.

### H3

The covariance is vv^T for v=(1,...,1,-1,...,-1). It is positive semidefinite with unit diagonal, including its singular rank-one form.

### H4

The level obeys exactly 0<q<=S(1), so c>b>=1.

### H5

The displayed representation has finite latent dimension d=1 and unit loadings +1 and -1 with the prescribed Gram matrix.

### H6

The full original ordinary-BH FDP, including all alternatives and their original labels, is

$$
f(x)=p\,\mathbf 1\{x\ge b+\delta\}+(1-p)\,\mathbf 1\{x>c+\delta\}.
$$

Indeed, below b+delta no true null can be rejected because each null score is below u(q). On [b+delta,c+delta], every score is at least b, so the largest qualifying rank is N and FDP=p. Above c+delta the alternative scores are below b and cannot be rejected at any BH threshold; all n nulls qualify at their rank-n threshold c, giving FDP=1. Endpoints and simultaneous ties do not change the Gaussian expectation. Hence

$$
F=pS(b+\delta)+(1-p)S(c+\delta)\le qp(2-p).
$$

For each null, the conditional null-p path has null scores u(t) and alternative scores b+c-u(t). Its actual BH rank is n for 0<t<qp and N for qp<t<q. Thus A(t)=t/(qp) in the first interval and t/q in the second, with its only net jump charge A(qp^-)-A(qp^+)=1-p. For delta>=0, the weighted net charge and weighted positive charge are both

$$
(1-p)g(qp)=(1-p)\exp\{-\delta c-\delta^2/2\}.
$$

They are recorded separately from F; they are not substituted for the OU norm. The path baseline is B=g(q)-integral A dg, and the exact identity reads F=qp[B+(1-p)g(qp)]. At delta=0, B=1 and F=qp(2-p).

### H7

F>0 because both finite Gaussian upper-tail probabilities are strictly positive.

### NOT

This family does not refute the universal BH gate. Direct Mehler differentiation for one half-line at a gives

$$
\partial_xT_t\mathbf 1_{[a,\infty)}(x)=\frac{\rho}{\sqrt{1-\rho^2}}\phi\!\left(\frac{a-\rho x}{\sqrt{1-\rho^2}}\right),\qquad \rho=e^{-t}.
$$

Its Gaussian integral is rho phi(a). Both net FDP jumps are positive; the full signed derivative is formed first and is nonnegative. Tonelli therefore gives the exact full-FDP quantity

$$
J(f)=p\phi(b+\delta)+(1-p)\phi(c+\delta).
$$

This also verifies the proposed signed-mixture reduction for this particular family: its L1 norm equals its total mass because both net coefficients are positive. Since phi(z)>=zS(z) for z>=1, J(f)>=F. Consequently

$$
0\le\frac{F(F-qp)_+}{qJ(f)}\le\frac{(F-qp)_+}{q}\le p(1-p)\le\frac14.
$$

This bound holds uniformly over the whole displayed family, including q tending to zero, unbounded N, p tending to either label boundary, and delta tending to zero or infinity. A large finite ratio or an unverified numerical truncation is not being used as a refutation.

## Failure

NOT fails: the exact full-FDP ratio is uniformly at most 1/4 throughout this singular, negative-null, imbalanced-label family.
