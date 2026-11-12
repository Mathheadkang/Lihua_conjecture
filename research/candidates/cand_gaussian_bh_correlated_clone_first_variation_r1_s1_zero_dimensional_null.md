---
type: candidate
title: Minimal null with zero-dimensional transverse space and unequal clone drift
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
  H9: pass
  H10: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:10:17.525Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $K=2$, $q=1/4$, $\theta_1=0$, $\Sigma=(1)$, $d=1$, $v_1=1$, $i=1$, $w_1=w_2=0$, $c_1=0$, and $c_2=-1$. Thus $G=Z\sim N(0,1)$, $E_i=\{0\}$, $Y=0$, and the expanded scores are $Z$ and $Z-\varepsilon$.

Write $u=\overline\Phi^{-1}(q)$ and $s=\overline\Phi^{-1}(q/2)$, so $\delta=s-u>0$. All small-parameter claims below hold for $0\le\varepsilon\le\delta/2$.

## Checks

### H1

$N=1$ is a positive integer.

### H2

$K=2$ is a positive integer.

### H3

$q=1/4\in(0,1/2)$.

### H4

$\theta=(0)\in\mathbb R^1$ is finite. Its one-sided true-null set is $I_0=\{1\}$.

### H5

$\Sigma=(1)$ is positive definite and has unit diagonal.

### H6

$G\sim N_1(0,I_1)$ and $v_1=1$ give a finite-dimensional unit-row representation, with $T_1=Z$ and $v_1\cdot v_1=1=\Sigma_{11}$.

### H7

$i=1\in[1]$.

### H8

Both marks $w_b=0$ belong to $E_i=\{0\}$.

### H9

Both $c_b$ are real and satisfy $c_b\le0$, as required when $\theta_i=0$.

### H10

The sign-preservation condition for a nonzero original mean is vacuous. For every $\varepsilon\ge0$ the two means are $0$ and $-\varepsilon$, so the actual null labels are exactly $I_0\times[2]$. Both expanded variances are one. Ordinary BH uses the largest qualifying rank and non-strict inequalities throughout.

### NOT

Fail: all four assertions hold for this object, including the equality cases.

For the original single test, $f(t)=\mathbf1\{t\ge u\}$. At $\varepsilon=0$ the two-clone BH largest rank is two exactly when $Z\ge u$ and otherwise is zero: a qualifying rank one would require $Z\ge s>u$ and hence already force rank two. Thus exact-copy invariance holds pointwise, including $Z=u$.

The only coordinate-face jump is $\Delta_{1,1}(0)=1$, so
$$
\mu_{1,1}=\phi(u)\delta_0.
$$
Its total variation and first-moment bound are exactly $\phi(u)$; the first moment is zero.

For $\varepsilon\le\delta/2$, rank two qualifies exactly when $Z-\varepsilon\ge u$. If it fails, then $Z<u+\varepsilon<s$, so rank one also fails. Consequently all-or-none reduction holds pointwise and the exceptional probability is zero. Its required bound follows, for example, with $A=a=1$ and $\varepsilon_0=\delta/2$.

Therefore
$$
F_K(\varepsilon)=\overline\Phi(u+\varepsilon),\qquad
F_K'(0+)=-\phi(u).
$$
Here $g(0)=\min(0,-1)=-1$, so the asserted face formula gives exactly $\int g\,d\mu_{1,1}=-\phi(u)$.

## Failure

NOT fails: the zero-dimensional Gaussian boundary case with unequal nonpositive clone drifts obeys all four conclusions exactly.
