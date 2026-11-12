---
type: candidate
title: One-coordinate two-clone deterministic mean split
status: failed
target_asset: gaussian_bh_correlated_clone_first_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:10:17.525Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $K=2$, $q=1/4$, $\theta_1=0$, $\Sigma=[1]$, $d=1$, $v_1=1$, $i=1$, $w_1=w_2=0$, $c_1=0$, and $c_2=-1$. Thus $G=Z\sim N(0,1)$, $E_i=\{0\}$, and the clone scores are $Z$ and $Z-\varepsilon$. Set $u=\overline\Phi^{-1}(1/4)$, $v=\overline\Phi^{-1}(1/8)$, and $\delta=v-u>0$.

## Checks

### H1

Pass: $N=1$ and $K=2$ are positive integers.

### H2

Pass: $q=1/4\in(0,1/2)$.

### H3

Pass: the mean is real and $\Sigma=[1]$ has unit diagonal and is positive definite.

### H4

Pass: the finite-dimensional representation has $G\sim N_1(0,I_1)$, $\|v_1\|=1$, and $v_1\cdot v_1=1$.

### H5

Pass: use $p=\overline\Phi(T)$, original label $I_0=\{1\}$, and ordinary BH with largest qualifying rank and non-strict inequalities.

### H6

Pass: $i=1\in[N]$.

### H7

Pass: both $w_b$ lie in $E_i=\{0\}$, and both $c_b\le0$ as required at $\theta_i=0$.

### H8

Pass: for every $\varepsilon\ge0$ the clone means are $0,-\varepsilon$, so both remain true nulls. Both marginal variances are one, and the clone vector is jointly Gaussian. The nonzero-mean sign condition is vacuous.

### NOT

Fail: all four assertions hold for this object. At $\varepsilon=0$, BH rejects both clones exactly when $Z\ge u$; if the first rank qualifies, then the second qualifies as well. This includes equality and gives exact-copy invariance. The original FDP is $\mathbf 1\{Z\ge u\}$, its only face jump is $1$, and $\mu_{1,1}=\phi(u)\delta_0$, which has the stated finite moment bound.

For $0<\varepsilon<\delta$, the two-clone procedure rejects both exactly when $Z\ge u+\varepsilon$. Partial rejection would require simultaneously $Z\ge v$ and $Z<u+\varepsilon$, which is impossible. Thus its rejection set equals BH on the minimum score $H=Z-\varepsilon$, copied twice, pointwise. The exceptional probability is zero; for example take $A=a=1$ and $\varepsilon_0=\delta/2$.

Consequently
$$
F_2(\varepsilon)=\overline\Phi(u+\varepsilon),\qquad F_2(0)=1/4,\qquad F_2'(0+)=-\phi(u).
$$
The asserted integral is exactly the same number since $g(0)=\min(0,-1)=-1$.

## Failure

NOT fails: the deterministic mean split has exact all-or-none reduction for sufficiently small perturbations and the asserted derivative $-\phi(u)$.
