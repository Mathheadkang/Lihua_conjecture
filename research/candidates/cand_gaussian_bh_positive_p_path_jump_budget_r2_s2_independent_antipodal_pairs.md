---
type: candidate
title: Independent antipodal pairs cannot accumulate a positive-jump budget
status: failed
target_asset: gaussian_bh_positive_p_path_jump_budget
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
direction: extremal
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:30:07.309Z'
extension_version: 0.0.4
---

## Object

For every integer $K\geq1$, take $N=2K$ and independent standard normal variables $X_1,\ldots,X_K$. For arbitrary positive numbers $\mu_1,\ldots,\mu_K$, set
$$
T_{2\ell-1}=X_\ell,\qquad T_{2\ell}=\mu_\ell-X_\ell,\qquad 1\leq\ell\leq K.
$$
Allow $K$ and all $\mu_\ell$ to depend arbitrarily on $0<q\leq S(1)$. The proposed extremal mechanism is to accumulate positive budgets across arbitrarily many independent antipodal null-alternative pairs, instead of repeating one rank-one null clone block. The covariance rank is $K$ and the true-null set is $I_0=\{1,3,\ldots,2K-1\}$.

## Checks

### H1

$N=2K$ is a finite positive integer for each model in the family.

### H2

The mean vector is $(0,\mu_1,0,\mu_2,\ldots,0,\mu_K)\in\mathbb R^N$; the positive parameters leave exactly the odd coordinates true nulls.

### H3

The covariance is block diagonal, with $K$ blocks
$$
\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.
$$
Each block has eigenvalues $0,2$, so the covariance is positive semidefinite with unit diagonal. The singular jointly Gaussian construction is admissible.

### H4

The level is in the required interval $0<q\leq S(1)$.

### H5

Use the full ordinary-BH path and the original labels. For a selected null $i=2\ell-1$, conditioning on its residual vector leaves every other pair's scores fixed, while the two scores in its own pair are
$$
T_i^i(t)=u(t),\qquad T_{i+1}^i(t)=\mu_\ell-u(t).
$$
Thus its p-value is $t$, and its partner's p-value $v(t)=S(\mu_\ell-u(t))$ is continuous and strictly decreasing. Its weight is $g_i(t)=1$. Simultaneous crossings are retained as actual net jumps of $A_i$.

### NOT

The normalized expected positive budget is uniformly bounded for this entire family, so NOT fails. Here is a residual-wise calculation that retains the actual largest BH rank, including cascades through the fixed background.

Fix one selected null and its residual vector. Write $a_k=qk/N$ and let $c_k$ count the $N-2$ fixed background p-values at most $a_k$. Define the two fixed ranks
$$
h=\max\{k:c_k+1\geq k\},\qquad H=\max\{k:c_k+2\geq k\}.
$$
They satisfy $1\leq h\leq H\leq N$. No actual rejection rank exceeds $H$, since at most two additional coordinates supplement the fixed background.

If the selected null is rejected and its partner is not, the actual largest rank is exactly $h$: feasibility of the actual rank gives the upper bound, and the selected null's threshold condition then makes $h$ feasible. If both are rejected, the identical argument with two coordinates gives actual rank exactly $H$.

Both are rejected precisely when $t\leq a_H$ and $v(t)\leq a_H$. Necessity follows from the upper bound $R\leq H$; sufficiency follows by feasibility of rank $H$. Since $v$ is decreasing, their joint-rejection region is a single interval, possibly empty, inside $(0,a_H]$.

Outside that interval the clipped path is
$$
A_i(t)=\min\{t/a_h,1\}.
$$
Indeed the null, if rejected alone, has rank $h$; and if $t\leq a_h$, rank $h$ is feasible using the null and the fixed background. Inside the interval, $A_i(t)=t/a_H$. Therefore there is at most one downward net jump, at the interval's left endpoint; its magnitude is at most $1$. At the right endpoint $a_H$ the path reaches $1$ continuously. Empty intervals, boundary events, and isolated ties add no downward net jumps. Consequently
$$
0\leq B_i(\xi)\leq1
$$
for every residual vector, uniformly over $K$, $q$, and the positive means. Summing over the $K$ true nulls gives
$$
\frac{N^{-1}\sum_{i\in I_0}\mathbb E B_i}{\sqrt{\log(1/q)}}
\leq\frac{1}{2\sqrt{\log(1/q)}}
\leq\frac{1}{2\sqrt{\log(1/S(1))}}<\infty.
$$
This bound concerns the independent antipodal-pair family only.

## Failure

NOT fails: each conditioned null path has at most one downward net jump, so independent replication to arbitrarily high covariance rank keeps the normalized null-averaged budget uniformly bounded.
