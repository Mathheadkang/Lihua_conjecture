---
type: candidate
title: Nonnegative equicorrelation boundary family has zero positive path charge
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

For any integer $N\geq1$, $r\in[0,1]$, $\theta\in\mathbb R^N$, and $0<q\leq\overline\Phi(1)$, take independent standard normals $G_0,G_1,\ldots,G_N$ and set
$$
Z_j=\sqrt r\,G_0+\sqrt{1-r}\,G_j,\qquad T_j=\theta_j+Z_j.
$$
Thus $\Sigma=(1-r)I_N+r\mathbf1\mathbf1^{\mathsf T}$. This includes independence, singular identical noise, arbitrary negative null means, and the empty-null boundary.

## Checks

### H1

$N$ is a finite positive integer.

### H2

Every mean is real, and the original true-null set is exactly $I_0=\{i:\theta_i\leq0\}$.

### H3

The displayed Gaussian construction has unit variances and covariance $\Sigma$. For every $x$, $x^{\mathsf T}\Sigma x=(1-r)\|x\|^2+r(\sum_jx_j)^2\geq0$; the endpoints $r=0,1$ are included.

### H4

The stipulated level satisfies $0<q\leq\overline\Phi(1)$. BH is the largest non-strict qualifying rank on all $N$ original coordinates.

### NOT

Fix any original null $i$ and any residual realization. All $\rho_{ij}\geq0$, including $\rho_{ii}=1$. As $t$ increases, $u(t)$ decreases, so every score $\theta_j+\rho_{ij}(u(t)-\theta_i)+\xi_j$ is nonincreasing. A zero coefficient gives a retained constant score, including a possible threshold tie. Every p-value is therefore nondecreasing, and the actual largest BH rank $R_i(t)$ is nonincreasing. Consequently $A_i(t)=\min\{Nt/(qR_i(t)),1\}$, with value one at rank zero, is nondecreasing. Its actual net downward jumps are absent, even at simultaneous crossings. Thus $B_i(\xi)=0$ exactly, with the original negative-mean weight $g_i$ retained. The normalized budget is identically zero for this entire parameterized family, so it cannot be unbounded.

## Failure

NOT fails: every selected-null conditional path has $B_i=0$, uniformly over this family.
