---
type: candidate
title: Three-group alternative cloning with two exact uniform-null blocks
status: failed
target_asset: gaussian_bh_growing_clone_compensated_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T23:05:52.404Z'
extension_version: 0.0.4
---

## Object

Take $N=d=3$, $q=1/4$, $\theta=(1,0,0)$, $\Sigma=I_3$, $v_j=e_j$, and chosen index $i=1$. Thus $T_1=1+G_1$, $T_2=G_2$, $T_3=G_3$, with independent standard Gaussian coordinates. Use exactly the compensated private clones from the target. The chosen group is alternative; the other two groups are exact true-null blocks of size $K$, with independent uniform one-sided p-values $P_2,P_3$.

This tests the smallest three-group model with two exact uniform-null blocks and a cloned alternative. In contrast to the board's chosen-negative-null pair, fractional chosen-copy mass is excluded from the numerator here, and rank cascades can dilute the FDP. The argument below handles the full largest crossing, rather than separate rank optima.

## Checks

### H1

$N=3$ is finite and positive.

### H2

$\theta=(1,0,0)\in\mathbb R^3$ is fixed, independently of $K$ and $\varepsilon$.

### H3

$\Sigma=I_3$ is positive definite and has unit diagonal.

### H4

$q=1/4\in(0,1/2)$.

### H5

$i=1\in[3]$ and $\theta_1=1\ne0$.

### H6

$G\sim N_3(0,I_3)$ and $v_j=e_j$ give the required unit-row representation and covariance. One may take $U_1(y_1,y_2)=(0,y_1,y_2)$; hence $Z=G_1$ and $Y=(G_2,G_3)$ are independent standard Gaussians.

### H7

Use $S(T_j)$, the original labels $I_0=\{2,3\}$, and ordinary largest-rank BH with non-strict thresholds. The two null p-values are independent uniforms, independent of the entire chosen group. Ties within each exact block are retained.

### H8

For every $K$ use exactly $K$ copies of every group; keep groups $2,3$ exact and set
$$
T_{1b}=1+s(t_s+t_s^{-1})+\sqrt{1-s^2}\,G_1+s\xi_b,
\qquad \phi(t_s)=s,
$$
with independent standard Gaussian $\xi_b$ independent of $G$. For all $0<s<\phi(0)$ the compensation is positive and the chosen mean remains positive. The expanded actual null set is $\{2,3\}\times[K]$.

### H9

Use the target's common-largest-crossing functionals and signed original-coordinate face measures. Limits below have the required order, $K\to\infty$ first at fixed positive $\varepsilon$.

### NOT

Both assertions hold, so the required violation fails. In fact every FDR in the assertion equals $2q/3=1/6$, and every signed face mass in its right-hand side is zero.

First establish the finite-array value without any population-limit assumption. For $j\in\{2,3\}$, let $R_j$ be the ordinary BH rejection count after replacing all $K$ p-values in block $j$ by zero and leaving the other p-values fixed. Then $R_j\ge K$ and $R_j$ is independent of $P_j$. The largest-rank rule gives the exact identity
$$
\{\text{block }j\text{ is rejected}\}
=\{P_j\le qR_j/(3K)\},
\qquad R=R_j\quad\text{on this event}.
$$
Indeed, if the original block is rejected, changing its entries to zero cannot create a larger qualifying rank: at any larger rank the original block's entries already satisfy that larger threshold. Conversely, if $P_j\le qR_j/(3K)$, the original array also qualifies at rank $R_j$, and monotonicity under replacement by zero gives equality of the largest ranks. This includes every possible cascade and all ties. Therefore
$$
\mathbb E\frac{K\mathbf1\{j\text{ rejected}\}}{R\vee1}
=\mathbb E\left[\frac K{R_j}\frac{qR_j}{3K}\right]
=\frac q3.
$$
The two blocks are the entire actual null set. Thus $F_{K,\varepsilon}=2q/3$ for every $K$ and admissible $\varepsilon$. Taking $K=1$ and the unperturbed chosen statistic also yields $F=2q/3$.

The population representation can be checked directly, rather than inferred from finite-array convergence. The function $H(x)$ is nondecreasing and right-continuous on $(0,3]$. If its feasible set has positive supremum $\rho$, monotonicity implies $H(\rho)\ge\rho$. If this were strict and $\rho<3$, then nearby larger $x$ would also be feasible. At $x=3$ one has $H(3)<3$, since the finite Gaussian chosen-group mean and $s>0$ give $b(3)<1$. Consequently $H(\rho)=\rho$ whenever $\rho>0$.

For each $j\in\{2,3\}$ let $\rho_j$ be the population largest crossing after setting $P_j=0$; thus this block contributes one at every positive $x$. Then $\rho_j\ge1$ and $\rho_j$ is independent of the uniform $P_j$. The same largest-crossing argument gives
$$
\{j\text{ counted at }\rho\}
=\{P_j\le q\rho_j/3\},
\qquad \rho=\rho_j\quad\text{on this event}.
$$
For completeness, $H_j\ge H$ implies $\rho_j\ge\rho$. If the original crossing counts $j$, that block is counted at every $x\ge\rho$, so $H_j=H$ there and a larger forced crossing is impossible. In the reverse direction, $P_j\le q\rho_j/3$ implies $H(\rho_j)=H_j(\rho_j)\ge\rho_j$, giving equality of the suprema. Attainment and the fixed-point identity hold for the forced crossing by the preceding monotonicity argument as well. The chosen group is alternative, so
$$
D=\sum_{j=2}^3\frac{\mathbf1\{j\text{ counted at }\rho\}}{\rho}
\quad(\rho>0),
\qquad
\mathbb E D
=\sum_{j=2}^3\mathbb E\left[\frac1{\rho_j}\frac{q\rho_j}{3}\right]
=\frac{2q}3.
$$
This proves assertion 1, including its equality of expectations and fixed-point requirement, without an interchange of limits.

Finally fix any deterministic chosen-group p-value $p\in(0,1)$ in the original three-test model. The same block identity with $K=1$ implies
$$
\mathbb E_{P_2,P_3}f(S^{-1}(p),G_2,G_3)=2q/3
$$
for every $p$. For every original rank $r$, take the difference of this identity at $T_1=u_r+\eta$ and $T_1=u_r-\eta$, and then let $\eta\downarrow0$. Bounded convergence applies because $0\le f\le1$. Thus
$$
\int\Delta_{1,r}(y)\,\gamma_2(dy)=0,
\qquad
\mu_{1,r}(\mathbb R^2)=\phi(u_r-1)\cdot0=0.
$$
The compensated variation is exactly zero, matching the stated sum of weighted signed masses. The cancellation retains the signed jumps of all three original ranks; it does not discard their positive or negative parts.

## Failure

NOT fails: exact independent uniform-null block calibration fixes both finite and population FDR at $1/6$, and every original signed face mass is zero.
