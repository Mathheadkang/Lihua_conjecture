---
type: candidate
title: Scalar true-null boundary has zero bridge numerator
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
slot: 1
direction: boundary_degenerate
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T21:56:18.237Z'
extension_version: 0.0.4
---

## Object

For every $0<q\leq S(1)$ and finite $a\geq0$, take $N=d=1$, $\theta_1=-a$, $v_1=1$, and $\Sigma=(1)$. Write $b=u(q)+a$. The full actual BH FDP is $f(x)=\mathbf1\{x\geq b\}$.

## Checks

### H1

$N=1$ is finite and positive.

### H2

$\theta_1=-a$ is finite and real; $I_0=\{1\}$ and $\pi_0=1$.

### H3

$\Sigma=(1)$ is positive semidefinite with unit diagonal.

### H4

The whole specified family has $0<q\leq S(1)$.

### H5

$G\sim\gamma_1$ and $T_1=-a+G$ give the required finite representation with $\|v_1\|=1$.

### H6

Ordinary BH rejects its sole coordinate exactly when $S(-a+x)\leq q$, equivalently $x\geq b$. Its full actual FDP is the indicated step function, with net jump $+1$ at $b$; no cutoff or smoothing is used. Direct Mehler differentiation and Gaussian convolution give $\mathbb E|\partial_xT_tf|=e^{-t}\phi(b)$, so $J(f)=\phi(b)>0$. This also verifies the proposed signed-mixture formula for this one-jump object: the mixture is $\phi(b)\varphi_{\sqrt{1-\rho^2}}(\cdot-\rho b)$ and its norm is $\phi(b)$.

For the conditional p-path, $R_1(t)=1$ for $0<t<q$ and $A_1(t)=t/q$, with no jumps. Both the exact net jump charge and positive jump charge are zero. The negative-mean baseline in the finite identity equals $F/q$, rather than automatically one.

### H7

$F=S(b)>0$ for each finite $a$ and $q>0$.

### NOT

$F=S(u(q)+a)\leq q=q\pi_0$, hence $F(F-q\pi_0)_+/(qJ(f))=0$ identically. This remains zero as $a\to\infty$ or $q\downarrow0$; the limiting zero mean FDP does not create a legal positive-numerator zero-budget model.

## Failure

NOT fails: the entire scalar true-null family has nonpositive FDR excess and bridge ratio zero.
