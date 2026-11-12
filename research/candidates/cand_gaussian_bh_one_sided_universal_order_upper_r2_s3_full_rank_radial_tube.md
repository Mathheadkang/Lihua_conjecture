---
type: candidate
title: Full-rank circular nulls with shrinking residuals and rare alternatives
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
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
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T20:05:08.223Z'
extension_version: 0.0.4
---

## Object

For every integer j>=3 set q_j=barPhi(j), n_j=ceil(exp(j^2)), N_j=2n_j, sigma_j=j^(-3), and a_j=sqrt(1-sigma_j^2). Let G_1,G_2,epsilon_1,...,epsilon_n,H_1,...,H_n be mutually independent standard Gaussian variables. For 1<=i<=n=n_j put alpha_i=2pi i/n and define
$$
T_i=-1/j+a_j(cos(alpha_i)G_1+sin(alpha_i)G_2)+sigma_j epsilon_i,
\qquad T_{n+i}=j/2+H_i.
$$
Compute one-sided p_i=barPhi(T_i) and run ordinary BH at q_j on all N_j coordinates, using its largest qualifying rank, multiplicities and non-strict comparisons. Keep the full actual denominator R vee 1.

The null covariance has strictly positive residual variance and hence full rank n_j, despite its two-dimensional leading factor. Thus the earlier exact null-span-two obstruction does not apply literally. Both dimension and residual degeneration depend on q. The null means -1/j lie in the shallow strip for j>=3 because 1<2log(j). The alternatives are individually rare at the largest BH threshold: P(T_{n+i}>=j)=barPhi(j/2), which tends to zero.

## Checks

### H1

The levels q_j=barPhi(j) belong to (0,1), tend to zero, and satisfy U_j=barPhi^{-1}(q_j)=j>=3.

### H2

Each N_j=2ceil(exp(j^2)) is a finite positive integer. The mean vector has n_j entries -1/j and n_j entries j/2, hence belongs to R^{N_j}.

### H3

The displayed independent-factor construction is exactly jointly Gaussian. Every null variance is a_j^2+sigma_j^2=1; every alternative variance is 1. Therefore its covariance is symmetric positive semidefinite with unit diagonal. In fact both covariance blocks are positive definite, and their cross-covariance is zero.

### H4

The one-sided true-null set is exactly I_0={1,...,n_j}, since -1/j<0 and j/2>0. P-values use the stipulated standard normal survival function with these unchanged labels.

### H5

The full N_j-coordinate ordinary BH procedure is used exactly as specified. No alternative, null, residual, label, or rank is removed or replaced.

### NOT

This sequence does not have an unbounded FDR/[q sqrt(log(1/q))] ratio. Define E_j={max_{1<=i<=n_j} epsilon_i<=2j} and W=sqrt(G_1^2+G_2^2). Any false rejection has p_i<=q_j R/N_j<=q_j and hence T_i>=j. On E_j this implies
$$
a_j W>=j+1/j-2/j^2>=j,
$$
so W>=j. Consequently, for the full original BH rule,
$$
FDR<=P(V>0)<=P(W>=j)+P(E_j^c)
<=exp(-j^2/2)+n_j barPhi(2j).
$$
Since n_j<=2exp(j^2) and barPhi(2j)<=exp(-2j^2)/(2j sqrt(2pi)),
$$
n_j barPhi(2j)<=exp(-j^2)/(j sqrt(2pi))<=exp(-j^2/2).
$$
Thus FDR<=2exp(-j^2/2). The Mills lower bound q_j>=phi(j)j/(j^2+1) gives
$$
FDR/q_j<=2sqrt(2pi)(j+1/j).
$$
Also q_j<=exp(-j^2/2), so sqrt(log(1/q_j))>=j/sqrt(2). For j>=3 the normalized ratio is at most 4sqrt(pi)(1+1/j^2)<=40sqrt(pi)/9<8. All estimates concern the original largest crossing and actual FDP, including the entire rare-alternative block.

## Failure

NOT fails: a quantified two-factor radial-tube event bounds the actual FDR by 8q_j sqrt(log(1/q_j)), despite growing full null rank, shrinking residuals, shallow negative null means, and rare alternatives.
