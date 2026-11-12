---
type: candidate
title: Mixed original labels with four alternating net jumps
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
round: 4
slot: 3
direction: drop_hypothesis
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:58:25.271Z'
extension_version: 0.0.4
---

## Object

Let $q=1/4$, $N=3$, $c=0.035$, $a=u(c)+u(q)$, and $X\sim N(0,1)$. Take
$$
T=(X,a-X,X-1),\qquad \theta=(0,a,-1),\qquad
\Sigma=vv^{\mathsf T},\quad v=(1,-1,1)^{\mathsf T}.
$$
Thus the original labels are $I_0=\{1,3\}$, while label 2 is an alternative. No label is removed or changed. For either original null's residual conditioning, every residual is identically zero.

This examines a different failure mechanism from the board's single-jump singular calibrations: the same selected-null path has four genuine alternating upward and downward jumps, with an original alternative entering, leaving, and reentering the selected ranks. It tests whether the signed identity misses cancellations when both signs occur repeatedly in one path.

Define
$$
d=S(u(2q/3)+1),\quad e=S(u(q)+1),\quad
f=S(a-u(2q/3)),\quad s_c=S(u(c)-1).
$$
Standard-normal evaluation gives
$$
d\approx0.024567315043308856<c=0.035<e\approx0.047017193576127506
<f\approx0.06438390899279196<q/3,
$$
and $2q/3<s_c\approx0.2084214448884651<q$. Also $a\approx2.486400423148679>0$.

## Checks

### H1

$N=3$ is finite and positive.

### H2

All entries of $\theta=(0,a,-1)$ are finite real numbers.

### H3

$\Sigma=vv^{\mathsf T}$ is symmetric positive semidefinite with diagonal $(1,1,1)$. Its singularity is allowed.

### H4

$q=1/4\in(0,1/2)$.

### H5

$T-\theta=vX$ is exactly jointly Gaussian with covariance $\Sigma$, and each coordinate has unit variance. For $i=1,3$, $Z_i=X$ and $Z_j=\Sigma_{ij}X$, so $\xi_j=0$ and residual independence holds.

### H6

The original one-sided p-values are $(S(X),S(a-X),S(X-1))$. The original true-null set is exactly $\{1,3\}$. Apply the largest qualifying non-strict BH rank to all three coordinates, without altering labels or dropping coordinate 2.

### NOT

The attempted violation fails. For label 1 put $t=S(X)$. On successive open intervals separated by
$$
0<d<c<e<f<2q/3<q,
$$
the actual BH rejection counts are respectively
$$
2,\quad1,\quad3,\quad1,\quad2,\quad1.
$$
For example, rank 3 occurs exactly when $c<t<e$: coordinate 2 first satisfies the rank-3 threshold at $c$, and coordinate 3 ceases to satisfy it at $e$. Rank 2 occurs initially until coordinate 3 exits its threshold at $d$, and returns when coordinate 2 enters its rank-2 threshold at $f$. On $(2q/3,q)$ the only rejected label is 2, so label 1 is not rejected there. Consequently
$$
A_1(t)=
\begin{cases}
3t/(2q),&0<t<d,\\
3t/q,&d<t<c,\\
t/q,&c<t<e,\\
3t/q,&e<t<f,\\
3t/(2q),&f<t<2q/3,\\
1,&2q/3<t<q.
\end{cases}
$$
The clipping point $2q/3$ is continuous. The four signed net jumps, in order, are
$$
-\frac{3d}{2q},\qquad\frac{2c}{q},\qquad
-\frac{2e}{q},\qquad\frac{3f}{2q}.
$$
They sum to $D_1\approx0.14276201508787867$. Because $g_1=1$, direct rejection integration gives
$$
F_1=\frac d2+(c-d)+\frac{e-c}{3}+(f-e)+\frac{2q/3-f}{2}
=\frac q3(1+D_1)
\approx0.09523016792398989.
$$
Thus the two upward jumps contribute indispensable negative terms, but their cancellation with both downward jumps is exactly correct.

The other original null, label 3, is also checked. Put $s=S(X-1)$. Its conditional path has
$$
A_3(s)=
\begin{cases}
3s/(2q),&0<s<2q/3,\\
1,&2q/3<s<s_c,\\
s/q,&s_c<s<q.
\end{cases}
$$
Here $g_3(s)=\exp\{-u(s)-1/2\}$, and its sole net jump is $1-s_c/q$ at $s_c$. The relation $t=S(u(s)+1)$ has derivative $dt/ds=g_3(s)$. Hence direct integration yields
$$
F_3=\frac12\int_0^{2q/3}g_3(s)\,ds
+\frac13\int_{s_c}^{q}g_3(s)\,ds
=\frac d2+\frac{e-c}{3}
\approx0.01628938871369693.
$$
Integrating $g_3 A_3'$ on these displayed intervals by parts gives precisely
$$
F_3=\frac q3\left[g_3(q)-\int_{(0,q)}A_3\,dg_3
+g_3(s_c)(1-s_c/q)\right].
$$
All conditional objects here are deterministic measurable functions with finitely many threshold and clipping events. The displayed paths have limits $0$ and $1$, and their derivatives are exactly the selected-label rejection indicator divided by $qr_i$. Isolated threshold values do not affect any integral. Their signed sums are finite deterministic numbers, so absolute integrability holds. For label 3, $0\leq A_3\leq1$, $g_3(0+)=0$, and $0<g_3(q)<1$, which directly puts its baseline in $[0,1]$; label 1's baseline is one. The positive-part upper bound follows on discarding the displayed negative signed terms. The full original FDR is $F_1+F_3\approx0.11151955663768681$.

## Failure

NOT is the first failing check: all four alternating signed jumps exactly reproduce the selected-null contribution, and the other original null has the stated weighted identity as well.
