---
type: candidate
title: Mixed-sign triangular clone groups with cancelling conditional jumps
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
round: 3
slot: 2
direction: small_cases
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:34:41.931Z'
extension_version: 0.0.4
---

## Object

Let three nonempty groups have arbitrary integer sizes $m_1,m_2,m_3$, with $N=m_1+m_2+m_3$. Let $X,W$ be independent standard normals. Every coordinate in group 1 has score $X$, every coordinate in group 2 has score $X/2+\sqrt3W/2$, and every coordinate in group 3 has score $M-X/2+\sqrt3W/2$, where $M>0$. Let $0<q\leq S(1)$ be arbitrary. Thus the true nulls are groups 1 and 2. All group sizes, $M$, and $q$ may vary along a proposed refuting sequence.

The smallest instance has $m_1=m_2=m_3=1$. To exhibit the new mixed-sign cancellation mechanism, take $q=0.1$, $t_0=0.04$, and
$$
M=u(q)+\tfrac12u(t_0)-\tfrac12=1.656894601170685\ldots.
$$
For a selected null in group 1, write $y=\sqrt3W/2$. At $y=1/2$, its conditional scores are
$$
u(t),\qquad \tfrac12u(t)+\tfrac12,\qquad M-\tfrac12u(t)+\tfrac12.
$$
The last score enters the rank-three threshold at $t_0$, while the middle score exits it at
$$
t_1=S(2\{u(q)-1/2\})=0.05901416964856132\ldots.
$$
Immediately around $t_0$, the actual largest ranks are $0,3$, giving $A(t_0^-)=1$ and $A(t_0^+)=0.4$. Immediately around $t_1$, the ranks are $3,0$, giving $A(t_1^-)=t_1/q$ and $A(t_1^+)=1$. Both jumps persist for an open interval of residuals around $y=1/2$: the other threshold inequalities are strict. Hence this family permits both positive charge and its upward-jump cancellation; it is outside the all-nonpositive-correlation and antipodal-pair mechanisms on the board.

## Checks

### H1

Pass. Every choice of positive integers $m_1,m_2,m_3$ gives a finite $N\geq3$.

### H2

Pass. The mean vector is real, with means $0,0,M$ in the three groups. The original true-null labels are retained: groups 1 and 2, and no coordinates from group 3.

### H3

Pass. The three centered group scores are the inner products of $(X,W)$ with the unit vectors $(1,0)$, $(1/2,\sqrt3/2)$, and $(-1/2,\sqrt3/2)$. Their covariance matrix, extended by exact within-group copies, is a positive semidefinite unit-diagonal Gram matrix. Its distinct off-diagonal group correlations are $1/2,-1/2,1/2$; rank two is allowed.

### H4

Pass. The full family uses the stipulated range $0<q\leq S(1)$. The numerical calibration has $q=0.1<S(1)$.

### H5

Pass. Compute ordinary BH on every original coordinate, with the largest non-strict qualifying rank. Given any selected null's residual, the three clone scores are affine in $u(t)$. Tied coordinates and simultaneous events are merged into actual net jumps, as required. All true-null means equal zero, so the original weight is exactly $g_i(t)=1$.

For the displayed smallest case, $u(2q/3)=1.5010859460440247\ldots$ and $u(q)=1.2815515655446006\ldots$. At $t_0$, the middle score is strictly between these thresholds and the third score equals $u(q)$. Thus neither rank one nor rank two qualifies just before $t_0$, whereas rank three qualifies just after. At $t_1$, the third score remains strictly below $u(2q/3)$, so the rank-three exit leaves rank zero. These are actual jumps, rather than counts of auxiliary events.

### NOT

Fail. This new sign pattern still has a uniform finite bound over the whole parameterized clone family. Each BH rejection set is a union of entire groups. Consequently every positive rejection count belongs to
$$
K=\{\textstyle\sum_{j\in D}m_j:\varnothing\ne D\subseteq\{1,2,3\}\},\qquad |K|\leq7.
$$
For a selected null in group 1, only the group-3 score increases as $t$ increases; the group-1 and group-2 scores decrease. A downward jump of $A_i$ requires an increase of the actual BH rank. Such an increase requires the increasing group-3 score to cross one of the thresholds $u(qk/N)$, $k\in K$: away from these crossings, every threshold count is nonincreasing. The group-3 score is strictly increasing and crosses each such threshold at most once. There are therefore at most seven actual positive-charge jumps. Since $0\leq A_i\leq1$ and $g_i=1$, $B_i\leq7$ for every residual.

For a selected null in group 2, all three score paths are nonincreasing as $t$ increases, because all its correlations are nonnegative. Every BH threshold count and hence the largest rank is nonincreasing; $A_i$ is nondecreasing, so $B_i=0$.

It follows uniformly in all allowed parameters that
$$
\frac{N^{-1}\sum_{i\in I_0}\mathbb E B_i}{\sqrt{\log(1/q)}}
\leq\frac{7m_1/N}{\sqrt{\log(1/S(1))}}
\leq\frac7{\sqrt{\log(1/S(1))}}<\infty.
$$
Arbitrarily large clone multiplicities preserve the mixed-sign cancellation mechanism but cannot yield the required divergence. This argument uses the fixed number of score groups and does not control growing numbers of heterogeneous groups.

## Failure

NOT is the first failing check: the triangular mixed-sign clone family has at most seven positive-charge jumps for each group-1 null and zero for each group-2 null, so its normalized average budget is uniformly bounded.
