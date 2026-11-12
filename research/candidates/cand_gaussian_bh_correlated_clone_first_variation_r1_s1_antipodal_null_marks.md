---
type: candidate
title: Minimal boundary null with antipodal transverse clone marks
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

Take $N=1$, $K=2$, $q=1/4$, $\theta_1=0$, $\Sigma=(1)$, $d=2$, $v_1=(1,0)$, $i=1$, $w_1=(0,1)$, $w_2=(0,-1)$, and $c_1=c_2=0$. Write $G=(Z,U)$ with independent standard normal coordinates. Then $E_i=\{0\}\times\mathbb R$, $Y=(0,U)$, and the two expanded scores are
$$
\frac{Z+\varepsilon U}{D_\varepsilon},\qquad
\frac{Z-\varepsilon U}{D_\varepsilon},\qquad
D_\varepsilon=\sqrt{1+\varepsilon^2}.
$$
Write $u=\overline\Phi^{-1}(q)$, $s=\overline\Phi^{-1}(q/2)$ and $\delta=s-u>0$.

## Checks

### H1

$N=1$ is a positive integer.

### H2

$K=2$ is a positive integer.

### H3

$q=1/4\in(0,1/2)$.

### H4

$\theta=(0)\in\mathbb R^1$ is finite, with $I_0=\{1\}$.

### H5

$\Sigma=(1)$ is positive definite and has unit diagonal.

### H6

$G\sim N_2(0,I_2)$ and $v_1=(1,0)$ provide a finite-dimensional unit-row representation of $T_1=Z$, with $v_1\cdot v_1=1=\Sigma_{11}$.

### H7

$i=1\in[1]$.

### H8

Both marks $w_1=(0,1)$ and $w_2=(0,-1)$ lie in $E_i$ and are fixed finite vectors.

### H9

$c_1=c_2=0$ are real and satisfy the required $c_b\le0$ at $\theta_i=0$.

### H10

The sign restriction for nonzero original means is vacuous. Both expanded means remain zero, so the actual null set is exactly $I_0\times[2]$. Every expanded variance is $(1+\varepsilon^2)/D_\varepsilon^2=1$, and the expanded model is jointly Gaussian. All BH statements use the largest qualifying rank and non-strict inequalities.

### NOT

Fail: all four conclusions hold for this object.

At $\varepsilon=0$ both scores equal $Z$. Rank two qualifies exactly when $Z\ge u$, and rank one can never be the largest qualifying rank because $s>u$. Thus exact-copy invariance holds pointwise, including threshold equality.

The original FDP is $f(t)=\mathbf1\{t\ge u\}$, so $\Delta_{1,1}(y)=1$ for every $y$. Consequently $\mu_{1,1}=\phi(u)\gamma_{E_i}$ and
$$
\int(1+\|y\|)\,|\mu_{1,1}|(dy)
=\phi(u)\bigl(1+\sqrt{2/\pi}\bigr)<\infty.
$$
This is the asserted bound with equality.

The reduced score is $H_1^\varepsilon=(Z-\varepsilon|U|)/D_\varepsilon$. Expanded BH rejects both clones precisely when this minimum is at least $u$, which is exactly the reduced rejection event. A disagreement can therefore occur only through a largest rank of one. Such partial rejection requires maximum score at least $s$ and minimum score strictly below $u$. It forces
$$
\frac{2\varepsilon|U|}{D_\varepsilon}>s-u=\delta,
\qquad |U|>\frac{\delta}{2\varepsilon}.
$$
Thus for every $\varepsilon>0$ the disagreement probability is at most
$$
\mathbb P\{|U|>\delta/(2\varepsilon)\}
\le 2\exp\{-\delta^2/(8\varepsilon^2)\}.
$$
Assertion 3 holds with $A=2$, $a=\delta^2/8$, and $\varepsilon_0=1$; it also supplies the stated FDR comparison.

Conditioning on $U$ gives
$$
\mathbb E f(H^\varepsilon)
=\mathbb E\,\overline\Phi\bigl(D_\varepsilon u+\varepsilon|U|\bigr).
$$
The derivative of the argument is $u\varepsilon/D_\varepsilon+|U|$, bounded by $u+|U|$ on $[0,1]$. Since the normal density is bounded and $\mathbb E|U|=\sqrt{2/\pi}$, dominated differentiation yields
$$
\left.\frac{d}{d\varepsilon}\mathbb E f(H^\varepsilon)\right|_{0+}
=-\phi(u)\sqrt{2/\pi}.
$$
The exponential error divided by $\varepsilon$ tends to zero, so this is also $F_K'(0+)$. Finally $g(Y)=\min(U,-U)=-|U|$, and the asserted signed-face integral is exactly $-\phi(u)\sqrt{2/\pi}$.

## Failure

NOT fails: the nonsmooth minimum from antipodal transverse marks has the asserted derivative, and partial clone rejection has the required exponential bound.
