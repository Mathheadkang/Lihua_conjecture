---
type: candidate
title: Positively correlated unequal nulls with a genuine upward path jump
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:33:21.062Z'
extension_version: 0.0.4
---

## Object

Let $N=2$, $q=1/4$, $b=q/4=1/16$, $a=u(b)-u(q)>0$, and
$$
\theta=(0,-a),\qquad \Sigma=\begin{pmatrix}1&1\\1&1\end{pmatrix},\qquad T=(Z,Z-a),\quad Z\sim N(0,1).
$$
Both labels are true nulls. This attacks a different mechanism from the board's anticorrelated downward jumps and removable spikes: positive perfect correlation and unequal null means produce a genuine upward jump, so the signed correction is negative.

## Checks

### H1

$N=2$ is finite and positive.

### H2

Both means are finite real numbers, and $I_0=\{1,2\}$ because $a>0$.

### H3

$\Sigma$ is symmetric with unit diagonal, and $x^{\mathsf T}\Sigma x=(x_1+x_2)^2\geq0$; its singularity is allowed.

### H4

$q=1/4\in(0,1/2)$.

### H5

$T-\theta=(Z,Z)$ is exactly jointly Gaussian with covariance $\Sigma$. For either conditioned coordinate, all residuals $\xi_j=Z_j-\rho_{ij}Z_i$ are identically zero, so residual independence holds without a conditioning ambiguity.

### H6

Use the original two one-sided p-values $S(Z),S(Z-a)$ and ordinary largest-rank non-strict BH, retaining both labels. No alternative null set, deletion, or threshold convention is used.

### NOT

The conclusion holds. For label 1 the full conditional path is $(u(t),u(t)-a)$. Since $b<q/2$, its rejection counts are
$$
R_1(t)=\begin{cases}2,&0<t\leq b,\\1,&b<t\leq q/2,\\0,&q/2<t<q.\end{cases}
$$
Indeed, both coordinates meet the rank-two threshold precisely when $t\leq S(u(q)+a)=b$; after that, the first coordinate meets the rank-one threshold precisely when $t\leq q/2$. Hence
$$
A_1(t)=\begin{cases}t/q,&0<t\leq b,\\2t/q,&b<t\leq q/2,\\1,&q/2<t<q.\end{cases}
$$
There is one genuine upward jump, $A_1(b^-)=b/q$ and $A_1(b^+)=2b/q$. Thus $J_1=\{b\}$ and its signed jump sum is $-b/q=-1/4$. Because $g_1=1$, the asserted right-hand side is
$$
\frac q2\left(1-\frac bq\right)=\frac{q-b}{2}.
$$
Directly, $P_1=S(Z)$ is uniform. Label 1 contributes $1/2$ when $P_1\leq b$, contributes $1$ when $b<P_1\leq q/2$, and zero otherwise. Its direct contribution is therefore $b/2+(q/2-b)=(q-b)/2$, exactly the same value.

For label 2, the full conditional path is $(u(t)+a,u(t))$, so $R_2(t)=2$ on all of $(0,q)$ and $A_2(t)=t/q$ with no net jumps. Here $g_2(t)=\exp\{-a u(t)-a^2/2\}$, and the baseline is
$$
g_2(q)-\int_{(0,q)}\frac tq\,dg_2(t)=\frac1q\int_0^q g_2(t)\,dt=\frac{S(u(q)+a)}q=\frac bq=\frac14.
$$
The integral equality follows by $t=S(x)$ and $g_2(t)\phi(x)=\phi(x+a)$. Thus the asserted contribution is $b/2$. Directly, label 2 is rejected exactly when $Z\geq u(q)+a=u(b)$, then with two rejections, again giving $b/2$.

For label 1, an event set is $\{S(u(q/2)+a),b,q/2\}$; the first event changes no rejection count. For label 2, include $q/2$ and each $S(u(qk/2)-a)$ that lies in $(0,q)$, for $k=1,2$. These are deterministic finite measurable sets containing all required events. The displayed paths verify both endpoints and the derivative formula on every component. For label 2, a threshold crossing at a conditionally stronger coordinate changes no rank. Point values at the non-strict thresholds have no effect on the integrals.

The two baselines are $1$ and $1/4$, and the absolute signed jump sums are deterministic and finite. There are no downward jumps, so $B_1=B_2=0$. Summing the exact contributions gives $F=q/2\leq q\pi_0=q$. Thus the full identity and its stated upper bound both hold.

## Failure

NOT is the first failing check: the genuine upward jump supplies exactly the negative signed correction needed for the direct label-1 rejection contribution, while label 2 has the exact weighted baseline.
