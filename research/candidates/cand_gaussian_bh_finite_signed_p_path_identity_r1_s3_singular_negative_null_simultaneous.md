---
type: candidate
title: Singular negative-null path with simultaneous crossings
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:25:30.473Z'
extension_version: 0.0.4
---

## Object

Set $N=2$, $q=1/4$, $h=q/2$, $a=u(q)$, $b=u(h)$, and $c=a+b$.
Let $X$ be standard normal, $Z=(X,-X)$, $\Sigma=\bigl(\begin{smallmatrix}1&-1\\-1&1\end{smallmatrix}\bigr)$, and $\theta=(-1,c+1)$. Thus $I_0=\{1\}$ and $T=(-1+X,c+1-X)$.

## Checks

### H1

The dimension $N=2$ is finite and positive.

### H2

Both means are finite real numbers. The original tested null has strictly negative mean $\theta_1=-1$; the second mean is positive.

### H3

The covariance is symmetric and unit diagonal. For every $v\in\mathbb R^2$, $v^{\mathsf T}\Sigma v=(v_1-v_2)^2\geq0$. Its rank is one, and the displayed $Z$ has exactly this Gaussian covariance.

### H4

The testing level $q=1/4$ lies in $(0,1/2)$.

### NOT

Fails: this object satisfies the signed identity, including its negative-null weight, simultaneous event, and actual net jump.

Conditioning on coordinate 1 gives the deterministic residual $\xi=(0,0)$ and the full path
$$
T_1^{\,1}(t)=u(t),\qquad T_2^{\,1}(t)=c-u(t).
$$
For $0<t<h$, coordinate 2 has $p_2(t)>q$, so the largest BH rejection count is $R_1(t)=1$. For $h\leq t<q$, both p-values are at most $q$, so $R_1(t)=2$. At $t=h$, the equalities $p_1(h)=q/2$ and $p_2(h)=q$ hold simultaneously, and the non-strict rule gives two rejections. The other threshold equalities occur only at the excluded endpoint $q$. We may take $E_1=J_1=\{h\}$, and
$$
A_1(t)=\begin{cases}2t/q,&0<t<h,\\t/q,&h\leq t<q.\end{cases}
$$
Consequently $A_1(h^-)-A_1(h^+)=1/2$, $A_1(0+)=0$, and $A_1(q^-)=1$. Coordinate 1 is rejected throughout $(0,q)$, and the two affine slopes are $2/q$ and $1/q$, exactly the asserted derivative. These residual and path objects are measurable.

Write $g(t)=\exp\{-u(t)-1/2\}$ and $G(t)=S(u(t)+1)$. Direct differentiation gives $G'(t)=g(t)$, with $G(0+)=0$. The original coordinate 1 is rejected alone when its p-value lies in $(0,h)$, and with coordinate 2 when it lies in $[h,q]$. It cannot be rejected when its p-value exceeds $q$. Thus
$$
F_1=\frac{G(q)+G(h)}2.
$$
Integration by parts on the two affine intervals gives
$$
\int_{(0,q)} A_1(t)\,dg(t)
=g(q)+\frac12g(h)-\frac{G(q)+G(h)}q.
$$
The claimed right-hand side is therefore
$$
\frac q2\left[g(q)-\int_{(0,q)}A_1\,dg+\frac12g(h)\right]
=\frac{G(q)+G(h)}2=F_1.
$$
Because $0\leq A_1\leq1$ and $g(0+)=0$, the baseline lies in $[0,g(q)]\subset[0,1]$. The absolute jump sum is the finite deterministic value $g(h)/2$, which also equals $B_1$. The stated FDR upper bound follows directly from the baseline bound. Numerically, $F_1=0.03139049407380984$, the baseline is $0.15513254165470514$, and the weighted jump is $0.09599141093577358$; multiplying their sum by $q/N=0.125$ reproduces $F_1$.

## Failure

NOT: the singular model with a strictly negative null and simultaneous crossings obeys the identity exactly; merging the event retains its single downward jump.
