---
type: candidate
title: >-
  A zero-null clone block against opposite positive alternatives has logarithmic
  charge
status: failed
target_asset: gaussian_bh_positive_p_path_jump_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:26:24.010Z'
extension_version: 0.0.4
---

## Object

Let integers $a\geq1$, $b\geq1$, $N=a+b$, and arbitrary real $m_1,\ldots,m_b>0$ vary without restriction. For one standard normal $G$, take $a$ original null coordinates $T_i=G$ and $b$ alternative coordinates $T_{a+j}=m_j-G$. Let $0<q\leq\overline\Phi(1)$ and $\alpha=a/N$. Repeated alternative means give arbitrary opposite-sign positive-mean clone groups; distinct means are allowed too.

## Checks

### H1

$N=a+b$ is finite and positive, with no dimension restriction on this parameterized family.

### H2

The first $a$ means equal zero and the other $b$ means are strictly positive, so $I_0=\{1,\ldots,a\}$ exactly. All labels are retained.

### H3

The actual jointly Gaussian noise has sign vector $s=(\mathbf1_a,-\mathbf1_b)$ and covariance $ss^{\mathsf T}$, which has unit diagonal and is positive semidefinite. The rank-one singularity is permitted.

### H4

The level lies in the required interval. The conditional path for any original null has zero residual, all null p-values equal $t$, and alternative p-values $v_j(t)=\overline\Phi(m_j-u(t))$. Actual BH retains all $N$ coordinates and uses its largest non-strict qualifying rank.

### NOT

Each $v_j(t)$ is nonincreasing in $t$. For analysis only, replace the $a$ null p-values by zero and denote this auxiliary BH rank by
$$
H(t)=a+\max\bigl(\{0\}\cup\{k\in\{1,\ldots,b\}:v_{(k)}(t)\leq q(a+k)/N\}\bigr).
$$
This does not replace the actual model: it supplies a deterministic comparison rank with $a\leq H(t)\leq N$. Since each alternative p-value is nonincreasing, $H$ is nondecreasing and has finitely many jumps, merging simultaneous threshold crossings.

The actual BH rank $R_i(t)$ is at most $H(t)$ by coordinatewise monotonicity. If $t\leq qH(t)/N$, all the $H(t)$ qualifying coordinates of the auxiliary model also qualify in the actual model, so $R_i(t)=H(t)$. If $t>qH(t)/N$, the selected null cannot be rejected and $A_i(t)=1$. Consequently the actual quantity is exactly
$$
A_i(t)=\min\{Nt/(qH(t)),1\}.
$$
Between jumps of $H$, this is continuous and nondecreasing. At a jump $h\to h'>h$, with $c=Nt/q$, its downward jump is
$$
\min\{c/h,1\}-\min\{c/h',1\}
\leq 1-h/h'\leq\log(h'/h).
$$
The first inequality follows by the three cases $c\leq h$, $h<c<h'$, and $c\geq h'$. Actual net jumps with zero change in $A_i$ contribute nothing; simultaneous crossings are counted once. The logarithms telescope along the nondecreasing auxiliary rank. Since the original selected-null mean is zero, its exact weight is $g_i=1$, and
$$
B_i\leq\log(N/a)=\log(1/\alpha),\qquad
\frac1N\sum_{i\in I_0}\mathbb E B_i
\leq\alpha\log(1/\alpha)\leq1/e.
$$
Finally $q\leq\overline\Phi(1)<1/2$ implies $\sqrt{\log(1/q)}\geq\sqrt{\log2}$. Thus the normalized budget is at most $1/(e\sqrt{\log2})$ uniformly over every parameter above, including arbitrarily small clone mass and arbitrarily separated positive means. It cannot be unbounded.

## Failure

NOT fails: the actual positive charge is bounded by $\log(1/\alpha)$ per null and by $1/e$ after null-mass averaging.
