---
type: candidate
title: Two independent tests have a nonpositive selected-null Mills trace
status: failed
target_asset: gaussian_bh_entropy_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:12:17.023Z'
extension_version: 0.0.4
---

## Object

Take $N=d=2$, $v_1=e_1$, $v_2=e_2$ and independent standard Gaussian coordinates $G_1,G_2$. Let $X=\theta+G_1$ with $\theta\le0$, and $Y=\mu+G_2$ with $\mu>0$. Thus only index 1 is a true null. Test at levels $q_n=\overline\Phi(3)2^{-n}$, $n\ge1$; the calculation holds for every $q\in(0,1/2)$. Both means can vary with $q$ while retaining these signs.

## Checks

### H1

$N=d=2$ are finite positive integers.

### H2

The directions are unit orthogonal vectors and the covariance is the identity. The mean vector is $(\theta,\mu)$, with original true-null set exactly $\{1\}$.

### H3

$q_n>0$ decreases to zero below $\overline\Phi(3)$ and eventually satisfies any proposed positive $q_0$.

### H4

Write $u_1=\overline\Phi^{-1}(q/2)>u_2=U=\overline\Phi^{-1}(q)$ and $c_j=1/h(u_j)$. Direct enumeration of the largest BH rank gives the two events on which a true-null discovery occurs:

- $A_1=\{X\ge u_1,Y<u_2\}$, with $R=1$ and $f=1$;
- $A_2=\{X\ge u_2,Y\ge u_2\}$, with $R=2$ and $f=1/2$.

Elsewhere $f=0$. In particular $f=\mathbf1_{A_1}+\tfrac12\mathbf1_{A_2}$ and $B=e_1(c_1\mathbf1_{A_1}+\tfrac12c_2\mathbf1_{A_2})$. These are the actual BH cells, not a freely selected rank.

### H5

Independence gives

$$
F=\overline\Phi(u_1-\theta)\Phi(u_2-\mu)
 +\tfrac12\overline\Phi(u_2-\theta)\overline\Phi(u_2-\mu)>0.
$$

Every term is finite and the first is strictly positive for finite means.

### NOT

Fix $t<1$, let $s=\sqrt{1-t}$ and let $z=(z_1,z_2)$ be the heat starting point. The two cell probabilities under the remaining independent Gaussian increments are

$$
A_1(t,z)=\overline\Phi((u_1-\theta-z_1)/s)\Phi((u_2-\mu-z_2)/s),
$$

$$
A_2(t,z)=\overline\Phi((u_2-\theta-z_1)/s)\overline\Phi((u_2-\mu-z_2)/s).
$$

Both are positive. Define

$$
\pi_2(t,z)=\frac{A_2(t,z)/2}{A_1(t,z)+A_2(t,z)/2}.
$$

Then the exact vector heat posterior is

$$
a(t,z)=e_1\{c_1+(c_2-c_1)\pi_2(t,z)\}.
$$

The Mills ratio is strictly increasing on the real line: $h'(w)=h(w)(h(w)-w)>0$, using $h(w)>w$ when $w>0$ and $h(w)>0\ge w$ when $w\le0$. Thus $c_2>c_1$ and

$$
\partial_{z_1}\log(A_2/A_1)
=\frac{h((u_2-\theta-z_1)/s)-h((u_1-\theta-z_1)/s)}s<0.
$$

It follows that $\partial_{z_1}\pi_2=\pi_2(1-\pi_2)\partial_{z_1}\log(A_2/A_1)<0$. The second component of $a$ is zero, so its full spatial Jacobian has

$$
\operatorname{tr}K(t,z)=(c_2-c_1)\partial_{z_1}\pi_2(t,z)<0
$$

at every $t<1,z$. The sign does not rely on an average or an omitted interface. It remains valid for arbitrarily large $\mu$ or negative $\theta$ depending on $q$.

For completeness the other asserted conclusions cannot fail here. Since $0\le f\le1$, $D\le\log(1/F)<\infty$. Also $\|a\|\le c_2=1/H$, giving $0\le x\le1$. Absolute trace integrability follows directly from bounded heat posteriors: under the path tilt, $a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]$ is a bounded martingale. The quotient heat equation and Ito's formula on each $[0,\tau]$, $\tau<1$, give $da_t=K_t\,d\widetilde W_t$ under the tilted Brownian innovation. Therefore

$$
\mathbb E_{\mathbb Q}\int_0^\tau\|K_t\|_{\rm HS}^2dt
=\mathbb E_{\mathbb Q}\|a_\tau\|^2-\|a_0\|^2\le H^{-2}.
$$

Monotone convergence and Cauchy--Schwarz yield $\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt\le\sqrt2/H<\infty$. Hence $M\le0$ and $M_+=0$, so the proposed budget holds for every $C>0$ throughout this family.

## Failure

NOT fails: the full heat Jacobian trace is pointwise nonpositive for the entire independent two-test, one-composite-null family, including a diverging positive alternative mean.
