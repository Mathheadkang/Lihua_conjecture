---
type: candidate
title: Independent null dust with a finite alternative has exact baseline FDR
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

For every $0<q\leq S(1)$ and finite $a>0$, take $N=d=2$, $\theta=(0,a)$, $\Sigma=I_2$, and the standard coordinate vectors as $v_1,v_2$. Put $b_1=u(q/2)$, $b_2=u(q)$, and $c=u(q)-a$. The full actual FDP is
$$
f(x,y)=\tfrac12\mathbf1\{y\geq c,\ x\geq b_2\}+\mathbf1\{y<c,\ x\geq b_1\}.
$$

## Checks

### H1

$N=2$ is finite and positive.

### H2

$\theta=(0,a)$ is real and $I_0=\{1\}$, $\pi_0=1/2$.

### H3

$\Sigma=I_2$ is positive definite with unit diagonal.

### H4

$0<q\leq S(1)$ throughout the family.

### H5

Independent standard normal $X,Y$ give $T=(X,a+Y)$ with the specified unit-vector representation.

### H6

If the alternative p-value is at most $q$ (equivalently $y\geq c$), the null is rejected precisely when its p-value is at most $q$, in which case both hypotheses are rejected and FDP is $1/2$. If the alternative p-value exceeds $q$, the null is rejected alone precisely when its p-value is at most $q/2$. This proves the displayed full actual FDP.

For $\rho=e^{-t}$, $s=\sqrt{1-\rho^2}$, write $H_b(z)=S((b-\rho z)/s)$. Independence gives the exact expression
$$
T_tf(x,y)=\tfrac12H_c(y)H_{b_2}(x)+(1-H_c(y))H_{b_1}(x).
$$
In particular $\partial_yT_tf=H_c'(y)(\tfrac12H_{b_2}(x)-H_{b_1}(x))$ keeps its signed components combined before the gradient norm. Gaussian convolution and the triangle inequality give
$$
\mathbb E\|\nabla T_tf\|_2\leq\rho\{\tfrac12\phi(b_2)+\phi(b_1)+\tfrac32\phi(c)\},
$$
so $J(f)$ is finite. Also $\partial_xT_tf>0$ everywhere for $t>0$, hence $J(f)>0$.

Conditional on the alternative p-value $p$, the null path has $A_1(t)=t/q$ when $p\leq q$ and $A_1(t)=\min\{2t/q,1\}$ when $p>q$. Thus its exact net signed jump charge and positive jump charge both vanish. The positive FDP is not an accumulation of conditional path jump charges from the independent null dust.

### H7

Writing $p_a=S(c)=\mathbb P(Y\geq c)$ and using independence,
$$
F=\tfrac12p_aq+(1-p_a)q/2=q/2>0.
$$

### NOT

$F=q\pi_0$ exactly, so $F(F-q\pi_0)_+/(qJ(f))=0$ for every finite $a>0$ and every legal $q$. Letting the alternative become arbitrarily strong or weak does not create bridge excess in this dust check.

## Failure

NOT fails: the full mixed-label independent model has exact baseline FDR and bridge ratio zero.
