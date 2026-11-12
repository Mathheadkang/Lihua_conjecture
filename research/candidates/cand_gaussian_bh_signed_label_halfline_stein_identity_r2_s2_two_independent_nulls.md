---
type: candidate
title: Two independent central nulls with nonzero correction
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: small_cases
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:29:57.144Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $\theta=(0,0)$, $\Sigma=I_2$, and $q=S(1)$. Put $u=S^{-1}(q)=1$, $v=S^{-1}(q/2)$, and $\delta=v-u>0$. The observations are two independent standard normals and both original labels are null. Unlike the scalar examples, the upper label has a nonzero covariance-correction term when the second rank triggers.

## Checks

### H1

$N=2$ is a finite positive integer.

### H2

The mean vector is real and the original null labels are exactly $I_0=\{1,2\}$.

### H3

$\Sigma=I_2$ has unit diagonal and positive eigenvalues $1,1$; the stipulated Gaussian law is admissible and positive definite.

### H4

$q=S(1)$ is positive and lies in the stated level interval, with $U=1$.

### H5

Use ordinary one-sided BH and retain these two original labels along every translation. For ordered scores $x>y$ write $d=x-y$. The records are $0\to1\to2$ when $d>\delta$ and $0\to2$ when $d<\delta$, with the largest-rank convention at equality. Thus the upper label has coefficients $1,-1/2$ in the first case and $1/2$ in the second; the lower label has coefficient $1/2$ in both. These are precisely the prescribed records and signed coefficients, without dropping dilution.

### NOT

The conclusion does not fail. Here is a direct two-variable check of its expectation identity, beyond the scalar cancellation already on the board. Write $t(d)=S(u+d)$ and $\epsilon(d)=1$ for $d<\delta$, $-1$ for $d>\delta$. The baseline summed over the two labels is
$$
B(x,y)=q/2+(q/2)\mathbf1\{d>\delta\}+\epsilon(d)t(d)/2.
$$
The only nonzero covariance correction is the upper label's rank-two term; it equals $-\epsilon(d)H_a(x,u+d)/2$, since $d_{12}=1$ and the other trigger-label pairs coincide. The gap $D=|Z_1-Z_2|$ has density $f(d)=\sqrt2\phi(d/\sqrt2)$ for $d>0$, and distribution function $F(d)=2\Phi(d/\sqrt2)-1$. Direct integration of the displayed $H_a$ formula gives
$$
\int_{\mathbb R}\phi(x)\phi(x-d)H_a(x,u+d)\,dx
=\phi(u+d)[\Phi(d/\sqrt2)-q].
$$
Indeed $\phi(x)H_a(x,u+d)=\phi(u+d)[\Phi(x)-\mathbf1\{x>u+d\}]$; convolution yields the first term $\Phi(d/\sqrt2)$ and the second integral is $S(u)=q$. Accounting for both possible orders, the expected correction is therefore
$$
-\int_0^\infty\epsilon(d)\phi(u+d)[\Phi(d/\sqrt2)-q],dd.
$$
Set $K(d)=t(d)[\Phi(d/\sqrt2)-q]$. Then
$$
K'(d)=-\phi(u+d)[\Phi(d/\sqrt2)-q]+t(d)f(d)/2.
$$
Consequently baseline plus correction equals
$$
q-qF(\delta)/2+2K(\delta)-K(0)=q,
$$
because $t(\delta)=q/2$, $K(0)=q(1/2-q)$, and $2K(\delta)-K(0)=qF(\delta)/2$. Independently, BH has at least one rejection exactly when both scores exceed $u$, or one exceeds $v$ and the other is below $u$; these disjoint events have total probability $q^2+2(q/2)(1-q)=q$. Both labels are null, so this is the actual FDR. This proves (SF) exactly in this model.

The other asserted properties also hold here. On $d=\delta$, the upper potential $H(x,v)-H(x,u+d)/2$ meets $H(x,u+d)/2$ because $u+d=v$; on $x=y$ the two labels have the common value $H(x,u)/2$. There are no other chamber interfaces. These matching values and the explicit half-line formulas give a locally Lipschitz field, bounded by $2C$, with the stipulated linear derivative growth. For each label, entry thresholds are at least the corresponding $u_r$ and later $b$ values decrease, so its signed baseline lies between its entry tail divided by $2$ and that tail divided by its entry rank, hence between zero and $q/2$. The scalar half-line formulas give $|H_a|\le1$ and $|H_x|\le C|x|+1$ on these cells. For above-threshold terms, $A\ge1$ and $X\ge A$ imply $|H_a|\le2S(A)$ by the elementary Mills inequalities; multiplying the coefficients and $d_{12}=1\le2$ proves each stated $4q/N$ budget. Splitting the already verified (SF) at $\tau=0$ therefore also gives the claimed inequality with its full signed $D_<$. All integrals above are absolutely integrable (the convolution formula, bounded potentials, and linear derivative growth suffice). This is a failed counterexample, not a general proof or a bound on $D_<$.

## Failure

NOT fails: this genuinely bivariate positive-definite model has a nonzero signed covariance correction, but its baseline plus correction equals the exact FDR $q$ and the remaining stated properties hold.
