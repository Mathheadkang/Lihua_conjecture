---
type: candidate
title: Single zero-loading null at the upper consequence level
status: failed
target_asset: gaussian_bh_one_sided_free_central_window_core
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 779c4649ca5118819e8dfa6dbce8e2a5f940384b9968185d078f02aeffa659b9
performed_by: unknown
created_at: '2026-11-06T22:40:10.866Z'
extension_version: 0.0.4
---

## Object

Take $q=1/10$, $N=d=1$, $\theta_1=0$, $a_1=0$, and independent standard normal variables $Z,\varepsilon_1$. Thus $T_1=\varepsilon_1$, $r_1=0$, $s_1=1$, $\gamma_1=1$. Use the one-sided track and the prescribed central-event convention $Y_1=-\infty$.

## Checks

### H1

Pass: $0<q=1/10<1/2$, and also $q\le1/10$ as required for the consequence. Put $U=\overline\Phi^{-1}(1/10)=1.2815515655446006$.

### H2

Pass: $N=d=1$ are positive finite integers.

### H3

Pass: $a_1=0$ has norm at most one, and $T_1=0+a_1 Z+\sqrt{1-\lVert a_1\rVert^2}\varepsilon_1$ is an admissible Gaussian multifactor representation.

### H4

Pass: $\theta_1=0\le0$, so $I_0=\{1\}$ under the one-sided track.

### NOT

Fail: $\rho_0(v,y)=1$, so the pointwise inequality is equality, $\phi(y)=\phi((-y)_+) $ for $y\le0$ and $\phi(y)\le\phi(0)$ for $y>0$. The kernel integral is $\Phi(U)=0.9$, whereas its claimed bound is

$$
\frac12+\frac{U}{\sqrt{2\pi}}=1.011265104010389.
$$

For the central contribution, the single null is always assigned to Ce; BH rejects exactly when $\overline\Phi(T_1)\le q$. Therefore $\mathrm{Ce}=q=0.1$, and the asserted bound is $q(1/2+U/\sqrt{2\pi})=0.10112651040103891>0.1$.

## Failure

NOT fails: both kernel bounds and the central-contribution consequence hold for this single zero-loading null.
