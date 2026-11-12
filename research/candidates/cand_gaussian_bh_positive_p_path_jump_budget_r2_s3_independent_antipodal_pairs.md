---
type: candidate
title: >-
  Independent singular antipodal null-alternative pairs have at most two
  positive jumps per null
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
slot: 3
direction: boundary_degenerate
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:30:07.309Z'
extension_version: 0.0.4
---

## Object

For any integer $m\geq1$, take $N=2m$, independent standard normal variables $X_1,\ldots,X_m$, and arbitrary finite means $b_\ell\leq0<a_\ell$. Set
$$
T_{2\ell-1}=b_\ell+X_\ell,\qquad T_{2\ell}=a_\ell-X_\ell.
$$
The covariance is block diagonal with $m$ blocks $\left(\begin{smallmatrix}1&-1\\-1&1\end{smallmatrix}\right)$. Let $0<q\leq S(1)$, allowing all these parameters to vary with $q$. Apply full ordinary BH and the original weighted, actual-net-jump definition of $B_i$.

This tests a higher-rank singular boundary: separate antithetic pairs have independent factors, so conditioning on one null leaves arbitrary random background scores from all other pairs. It is not the single-factor clone family from the board.

## Checks

### H1

Pass. $N=2m$ is a finite positive integer for every family member.

### H2

Pass. All means are finite real numbers and the true-null set is exactly $I_0=\{1,3,\ldots,2m-1\}$, retaining arbitrary negative null means.

### H3

Pass. Each covariance block is positive semidefinite with eigenvalues $0,2$ and unit diagonal. The full covariance is positive semidefinite, unit diagonal, and has rank $m$.

### H4

Pass. $q$ is in the target's interval, including its upper boundary.

### H5

Pass. For selected null $i=2\ell-1$, condition on its residual vector. All scores outside this pair are then constant in $t$, and the two moving scores are exactly
$$
T_i^{\,i}(t)=u(t),\qquad T_{2\ell}^{\,i}(t)=a_\ell+b_\ell-u(t).
$$
Thus the selected p-value increases strictly as $t$, while its partner p-value decreases strictly. No coordinate or label is omitted from BH. The original weight is
$$
g_i(t)=\exp\{b_\ell u(t)-b_\ell^2/2\}\leq1,
$$
because $b_\ell\leq0$ and $u(t)\geq1$ on $(0,q)$.

### NOT

Fail. Fix any residual realization, and let $n(k)$ count the frozen background p-values at or below $qk/N$. Define the three deterministic augmented ranks
$$
K_s=\max\bigl(\{0\}\cup\{k\in[N]:n(k)+s\geq k\}\bigr),\qquad s=0,1,2.
$$
If the actual BH rank $R>0$ rejects exactly $s$ members of the moving pair, then $R=K_s$. Indeed, $n(R)+s=R$ gives $K_s\geq R$; all $s$ rejected moving coordinates qualify also at $qK_s/N$, making $K_s$ a qualifying BH rank and hence $R\geq K_s$. Rank zero causes no additional possible positive rank.

Every upward jump of $R_i(t)$ must occur when the strictly decreasing partner p-value crosses one of $qK_1/N$ and $qK_2/N$. To see this, let the rank just after an upward jump be $r>0$. Its frozen background count is constant; the selected p-value becomes worse as $t$ increases. Therefore the rank-$r$ inequality can change from false to true only through the partner p-value crossing $qr/N$. At that jump the partner is rejected, so $r$ is $K_1$ or $K_2$. There are at most two such crossing times, with coincident times merged. Constant background threshold ties do not alter this argument.

Each actual positive drop of $A_i$ requires an upward rank jump: for fixed $t$, $\min\{tN/(qR),1\}$ decreases in $R>0$, and rank zero has $A_i=1$. Each drop has size at most one. Consequently, pointwise for every residual realization,
$$
B_i\leq2,\qquad
\frac1N\sum_{i\in I_0}\mathbb E B_i\leq1.
$$
This gives the parameter-uniform bound
$$
\frac{N^{-1}\sum_{i\in I_0}\mathbb E B_i}{\sqrt{\log(1/q)}}
\leq\frac1{\sqrt{\log(1/S(1))}}<\infty.
$$
Hence even growing rank, arbitrary pair means, and negative true-null means in this independent-pair boundary family cannot produce an unbounded refuting sequence.

## Failure

NOT fails: each conditioned path has at most two actual positive jumps, giving a uniform normalized budget bound for the entire independent-pair family.
