---
type: candidate
title: One-coordinate two-clone opposite tangent rotations
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

Take $N=1$, $K=2$, $q=1/4$, $\theta_1=0$, $\Sigma=[1]$, $d=2$, $v_1=e_1$, $i=1$, $w_1=e_2$, $w_2=-e_2$, and $c_1=c_2=0$. Write $G=(Z,Y)$ with independent standard normal coordinates. The clone scores are $(Z\pm\varepsilon Y)/s$, where $s=\sqrt{1+\varepsilon^2}$. Set $u=\overline\Phi^{-1}(1/4)$, $v=\overline\Phi^{-1}(1/8)$, and $\delta=v-u>0$.

This stochastic splitting calculation was completed before the parent reported independent coverage of this same small-case family by another slot; it is retained to preserve the worked-out test, not claimed as additional family coverage.

## Checks

### H1

Pass: $N=1$ and $K=2$ are positive integers.

### H2

Pass: $q=1/4\in(0,1/2)$.

### H3

Pass: the mean is real and $\Sigma=[1]$ is positive definite with unit diagonal.

### H4

Pass: $G\sim N_2(0,I_2)$ and $v_1=e_1$ is a unit row realizing $\Sigma$.

### H5

Pass: use one-sided Gaussian p-values, original label $I_0=\{1\}$, and ordinary BH with largest qualifying rank and non-strict inequalities.

### H6

Pass: $i=1\in[N]$.

### H7

Pass: $E_i=\operatorname{span}(e_2)$ contains $w_1,w_2$, and $c_1=c_2=0\le0$.

### H8

Pass: both clone means remain zero, their variances are $(1+\varepsilon^2)/(1+\varepsilon^2)=1$, and they are jointly Gaussian. Both actual labels remain null. The nonzero-mean sign condition is vacuous.

### NOT

Fail: all four conclusions hold. At zero both clones are rejected exactly when $Z\ge u$, including equality, giving exact-copy invariance. The original face jump is $1$, so $\mu_{1,1}=\phi(u)\gamma_{E_i}$. Its total variation moment is exactly $\phi(u)(1+\sqrt{2/\pi})$ and $g(Y)=-|Y|$ is integrable.

Write $M=(Z-\varepsilon|Y|)/s$ and $L=(Z+\varepsilon|Y|)/s$. BH rejects both exactly when $M\ge u$. Partial rejection requires $L\ge v$ and $M<u$, hence
$$
\frac{2\varepsilon|Y|}{s}>v-u=\delta.
$$
It follows that the exceptional probability is at most
$$
\mathbb P\{|Y|>\delta/(2\varepsilon)\}\le2\exp\{-\delta^2/(8\varepsilon^2)\}.
$$
Outside this event both or neither clone is rejected according to $M\ge u$, which is exactly reduced BH copied twice. The FDR error has the same bound. Thus one can take $A=2$, $a=\delta^2/8$, and $\varepsilon_0=1$.

Moreover
$$
F_2(\varepsilon)=\mathbb E\overline\Phi(us+\varepsilon|Y|)+O(e^{-\delta^2/(8\varepsilon^2)}).
$$
The difference quotient for the expectation is dominated by a constant times $1+|Y|$ for $0<\varepsilon\le1$, using $s-1\le\varepsilon^2/2$ and boundedness of $\phi$. Dominated convergence therefore gives
$$
F_2'(0+)=-\phi(u)\mathbb E|Y|=-\phi(u)\sqrt{2/\pi}=\int g\,d\mu_{1,1},
$$
exactly as asserted.

## Failure

NOT fails: opposite tangent rotations yield the asserted Gaussian-tail exception and right derivative.
