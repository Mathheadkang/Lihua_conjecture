---
type: candidate
title: Singleton block with unit loading and threshold equality
status: failed
target_asset: gaussian_bh_block_deficit_curve_reduction
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
statement_digest: f1dda2f50a23bcb44d5591faa42a4ed7c15018980386fbefca5819ed441dbef8
performed_by: unknown
created_at: '2026-11-06T21:22:09.796Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $q=1/2$, $G=1$, $B_1=\{i\}=\{1\}$, $\theta_1=0$, and $a_1=1$. Let $Z_1,\varepsilon_1$ be independent standard normal random variables and put $T_1=Z_1+0\varepsilon_1$. Thus $\Sigma=(1)$. Set $P_1=p(|Z_1|)$, $t_1=q$, and $U=p^{-1}(q)$. The mates and background sets are empty. Include the boundary realizations $Z_1=\pm U$, where $P_1=t_1$ exactly; no exceptional realization is removed.

## Checks

### H1

The dimension is a positive integer, $q\in(0,1)$, $\theta_1=0$, and $\Sigma=(1)$ is positive semidefinite with unit diagonal. The specified independent noises give an admissible one-factor block representation, including its conditionally deterministic unit-loading endpoint.

### H2

The p-value is exactly $P_1=p(|T_1|)$. There is one threshold $t_1=1/2$, so strict increase over the rank domain is vacuous. Counts use $P\le t_1$, including at $Z_1=\pm U$.

### H3

The empty background gives $\beta(1)=0$. It is integer-valued, nondecreasing, bounded by $N-|B_1|=0$, and independent of $(Z_1,\varepsilon_1)$.

### H4

The empty mates set gives $M_z(1)=0$ for every $z$. This is an integer-valued nondecreasing count. Consequently $D(1)=1-1-0=0$ and $D^*(1)=0$ by the stated suffix-minimum definition.

### NOT

The conclusion does not fail. For (i), the sole rank satisfies $1+\beta(1)+M_z(1)=1$, $M_z(1)=D(1)=0$, and $D(1)\le0$. Hence both displayed maxima defining $R_i$ equal $1$, and $R_i^\flat=1$. For (ii), the sole curve value is $D^*(1)=D(1)=0\le1-1$; monotonicity and unit-increment requirements are vacuous, and $D^*(k)\le0$ holds exactly on the domain $k\le R_i^\flat=1$. The alternative maximum using $D^*$ is again $1$. For (iii), this curve is deterministic, and both central ranks equal $1$ for every $z$. Therefore the difference of the two $\rho_1(u_1,z)$ terms is identically zero, even at $z=\pm U$, and $\Delta_i^{\rm c}=\Delta^{\rm c}(D^*)=0$.

## Failure

NOT fails: the singleton unit-loading boundary satisfies every asserted identity, with both ranks equal to $1$ and central difference zero.
