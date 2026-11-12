---
type: candidate
title: Two-coordinate mixed labels and exact signed face cancellation
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

Take $N=K=2$, $q=1/4$, $\theta=(1,0)$, $\Sigma=I_2$, $d=2$, $v_1=e_1$, $v_2=e_2$, and $i=1$. Let $G=(Z,Y)$ with independent standard normal coordinates, $w_1=w_2=0$, $c_1=0$, $c_2=-1$. The expanded scores are $1+Z$, $1+Z-\varepsilon$, $Y$, $Y$, with null labels only on the last two. Set
$$
u_1=\overline\Phi^{-1}(q/2),\quad u_2=\overline\Phi^{-1}(q),\quad b_\ell=\overline\Phi^{-1}(q\ell/4)\ (1\le\ell\le4),\quad
\delta=\min_{1\le\ell<4}(b_\ell-b_{\ell+1})>0.
$$
This $N=2$ example examines competing positive and negative FDP jumps, which do not occur in the $N=1$ all-null tests.

## Checks

### H1

Pass: $N=K=2$ are positive integers.

### H2

Pass: $q=1/4\in(0,1/2)$.

### H3

Pass: $\theta=(1,0)$ is real and $\Sigma=I_2$ is positive definite with unit diagonal.

### H4

Pass: the two standard basis rows are unit vectors and their Gram matrix is $I_2$; $G\sim N_2(0,I_2)$ realizes the model.

### H5

Pass: use one-sided Gaussian p-values and largest-rank, non-strict ordinary BH. The original true-null set is $I_0=\{2\}$.

### H6

Pass: $i=1\in[N]$.

### H7

Pass: $E_i=\operatorname{span}(e_2)$ contains both zero marks. The constants $0,-1$ are finite. There is no sign restriction on these constants because $\theta_i=1>0$.

### H8

Pass: for $0\le\varepsilon\le1/2$, both perturbed means $1,1-\varepsilon$ stay positive. The copied null means stay zero. Every marginal has variance one and the expanded vector is jointly Gaussian with the prescribed preserved labels.

### NOT

Fail: all four conclusions hold. Exact-copy invariance holds even with deterministic ties: every odd qualifying expanded rank is followed by an even qualifying rank, since those adjacent order statistics are equal. The qualifying even ranks $2r$ correspond exactly to qualifying original ranks $r$, with the same thresholds. Hence the largest rank is doubled and the rejected set is copied.

For fixed null score $y$, the original FDP as a function of the alternative score $x$ has no jump at $u_1$ and only the following signed jump at $u_2$:
$$
\Delta_{1,1}(y)=0,\qquad
\Delta_{1,2}(y)=\tfrac12\mathbf 1\{u_2\le y<u_1\}-\tfrac12\mathbf 1\{y\ge u_1\}.
$$
Indeed, for $u_2\le y<u_1$, crossing $x=u_2$ creates two rejections and FDP $1/2$; for $y\ge u_1$, that crossing changes the null-only rejection with FDP $1$ to two rejections with FDP $1/2$. For $y<u_2$ the FDP remains zero. Thus the signed face measures have bounded densities relative to the one-dimensional Gaussian measure, and satisfy the stated finite-moment bound. Here $g(y)=-1$.

For $0<\varepsilon<\delta$, partial rejection of the alternative clones is impossible. Otherwise the rejection count would be $R=1$ or $3$, since the identical null copies cannot be split. The higher alternative score would be at least $b_R$, while the lower would be below $b_{R+1}$; otherwise rank $R+1$ would qualify. Their difference $\varepsilon$ would consequently exceed $b_R-b_{R+1}\ge\delta$, a contradiction. When groups are all or none, qualifying completed groups are exactly the qualifying ranks of reduced BH on $(1+Z-\varepsilon,Y)$. Thus the reduction is pointwise with zero exceptional probability for $\varepsilon\le\varepsilon_0=\min(1/2,\delta/2)$; any positive $A,a$ work.

For any alternative p-value $x$ independent of the uniform null p-value $U$, conditional expected FDP is $q/2$: if $x\le q$, both are rejected precisely on $U\le q$, contributing $(1/2)q$; if $x>q$, only the null can be rejected, precisely on $U\le q/2$, contributing $q/2$. Any rejection of the alternative alone has FDP zero. Therefore both the original model and the reduced model have FDR $q/2$, and $F_2(\varepsilon)=q/2$ throughout this small interval. The actual derivative is zero.

The claimed formula agrees, including the necessary cancellation:
$$
\int g\,d\mu_{1,2}
=-\frac{\phi(u_2-1)}2\bigl[\mathbb P\{u_2\le Y<u_1\}-\mathbb P\{Y\ge u_1\}\bigr]
=-\frac{\phi(u_2-1)}2[(q-q/2)-q/2]=0.
$$
The rank-one term is zero because its face jump is zero.

## Failure

NOT fails: the mixed-label model has exact local all-or-none reduction and equal positive and negative face contributions, giving the asserted derivative zero.
