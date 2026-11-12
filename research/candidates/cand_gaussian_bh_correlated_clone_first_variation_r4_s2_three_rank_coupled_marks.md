---
type: candidate
title: Three-rank mixed-label cascades with two coupled clone marks
status: failed
target_asset: gaussian_bh_correlated_clone_first_variation
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
  H10: pass
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:23:08.560Z'
extension_version: 0.0.4
---

## Object

Take N=3, K=2, q=1/4, theta=(0,1,0), Sigma=I_3, d=3, v_j=e_j, i=1, w_1=e_2, w_2=e_3, and c_1=c_2=0. Let G=(Z,Y_2,Y_3) have independent standard normal coordinates. Thus the unchanged scores are A=1+Y_2 and B=Y_3, while the two changed scores are
$$
X_b^\varepsilon=\frac{Z+\varepsilon Y_{b+1}}{s_\varepsilon},\qquad s_\varepsilon=\sqrt{1+\varepsilon^2},\qquad b=1,2.
$$
The original true nulls are {1,3}. Write u_r=Phi-bar-inverse(r/12), r=1,2,3, and g(Y)=min(Y_2,Y_3). This differs from the board's N=2, K=1 rotation check by retaining three possible original ranks, a two-clone minimum, and dependence of that minimum on both unchanged scores. In particular, the rank-three face has both positive and negative jumps. The earlier two-rank calculation does not establish the calculations below.

## Checks

### H1

Pass. N=3 and K=2 are positive integers.

### H2

Pass. q=1/4 is strictly between zero and one half.

### H3

Pass. The mean vector is finite. Sigma=I_3 is positive definite and has unit diagonal.

### H4

Pass. G is standard Gaussian in R^3 and v_j=e_j are unit rows with v_j dot v_k=Sigma_jk. Thus T=(Z,1+Y_2,Y_3) is the specified representation.

### H5

Pass. Use p_j=Phi-bar(T_j) and the actual one-sided true null set I_0={1,3}.

### H6

Pass. Both original and expanded rejection sets use ordinary BH with the largest qualifying rank and non-strict inequalities.

### H7

Pass. The chosen index i=1 belongs to {1,2,3}.

### H8

Pass. E_1=span(e_2,e_3), and both w_1=e_2 and w_2=e_3 belong to E_1. Their lengths equal one; both drift marks are finite.

### H9

Pass. Since theta_1=0, the required drift restriction is c_b<=0; both drifts equal zero. The two perturbed means remain zero. The nonzero unchanged mean remains positive, so all actual labels are preserved.

### H10

Pass. The expanded scores are (X_1^epsilon,X_2^epsilon,A,A,B,B), with the displayed normalization. They are jointly Gaussian with variance-one marginals, and their actual true-null set is I_0 times {1,2}. No positive definiteness is required of this expanded covariance.

### NOT

Fail. All four asserted conclusions hold in this object, as follows.

**Exact copying, including deterministic ties.** At epsilon=0 each sorted original score occurs twice. If an odd expanded rank 2r-1 qualifies, the same tied score qualifies at rank 2r because its BH threshold is weaker. Therefore the largest expanded rank is even, equal to twice the largest qualifying original rank. At that rank the original and expanded p-value cutoffs are identical. Non-strict rejection thresholds include every tied coordinate on both sides, proving equality of the sets and FDPs pointwise.

**Finite face measures.** Every FDP lies in [0,1], so |Delta_r|<=1. Consequently
$$
\int (1+\|y\|)\,|\mu_{1,r}|(dy)
\le \phi(u_r)\mathbb E(1+\sqrt{Y_2^2+Y_3^2})<\infty.
$$
Also |g(y)|<=||y||, proving the claimed total-variation integrability.

**Exponential all-or-none bound.** Put h_l=Phi-bar-inverse(l/24), l=1,...,6, and delta=min_{1<=l<6}(h_l-h_{l+1})>0. Unchanged pairs are always rejected together. If the changed pair is only partly rejected, the actual expanded rank R is odd, in {1,3,5}. Its upper clone U satisfies U>=h_R. Its lower clone L must satisfy L<h_{R+1}: otherwise rank R+1 would qualify, contradicting maximality. Hence U-L>delta. But
$$
U-L=\frac{\varepsilon|Y_2-Y_3|}{s_\varepsilon}.
$$
Because Y_2-Y_3 is N(0,2), the partial-pair probability is at most
$$
2\exp\{-\delta^2/(4\varepsilon^2)\}.
$$
When all pairs are rejected all or none, the actual expanded rank is 2r and h_{2r}=u_r. Group qualification is exactly qualification by the minimum changed score and unchanged scores at original rank r. Any larger qualifying reduced rank would give a larger qualifying expanded even rank. Thus the rejection-set discrepancy is contained in the partial-pair event. Taking A=2, a=delta^2/4, epsilon_0=1 proves the stated reduction bound and its FDP consequence.

**Exact signed derivative with all three ranks.** Outside the zero-probability set where A or B equals an original threshold, the coordinate-face jumps are
$$
\Delta_1=\mathbf 1\{\max(A,B)<u_2,\ \min(A,B)<u_3\},
$$
$$
\Delta_2=\tfrac12\mathbf 1\{A\ge u_2,B<u_3\}
+\mathbf 1\{u_2\le B<u_1,A<u_3\},
$$
$$
\Delta_3=\mathbf 1\{A\ge u_3,B\ge u_3\}
\left[\tfrac23-\tfrac12\mathbf 1\{A\ge u_2,B\ge u_2\}
-\mathbf 1\{B\ge u_1,A<u_2\}\right].
$$
For Delta_1, neither rank two nor rank three can qualify, and crossing creates one null rejection. For Delta_2, rank three is excluded by the other score below u_3. If A is the higher unchanged score, crossing produces FDP 1/2 from FDP zero; if B is higher, its pre-crossing FDP is one exactly when B>=u_1. For Delta_3, crossing produces FDP 2/3. The preceding FDP equals 1/2 when both unchanged scores exceed u_2; otherwise it equals one precisely when B>=u_1 and A<u_2, and equals zero in the remaining cases. This accounts for every largest-rank cascade. In particular Delta_3=-1/3 on the positive-probability region B>=u_1 and u_3<=A<u_2.

Condition on (Y_2,Y_3), so A,B and the jumps are fixed. The reduced changed score is exactly
$$
H_1^\varepsilon=\frac{Z+\varepsilon g(Y)}{s_\varepsilon}.
$$
The fixed-coordinate FDP is a step function with these three jumps; its baseline at minus infinity cancels on subtraction. Independence of Z therefore gives the exact identity
$$
\mathbb E f(H^\varepsilon)-F
=\sum_{r=1}^3\mathbb E\left[\Delta_r(Y)
\{\overline\Phi(s_\varepsilon u_r-\varepsilon g(Y))
-\overline\Phi(u_r)\}\right].
$$
For 0<=epsilon<=1 the absolute derivative of the survival-function term is bounded by (|u_r|+|g(Y)|)/sqrt(2 pi), an integrable random variable. Differentiation under the expectation is justified by this bound and gives
$$
\left.\frac{d}{d\varepsilon}\mathbb E f(H^\varepsilon)\right|_{0+}
=\sum_{r=1}^3\phi(u_r)\mathbb E[g(Y)\Delta_r(Y)],
$$
which is exactly the asserted signed face formula. The exponential reduction error divided by epsilon tends to zero, so the same derivative holds for the actual six-score BH FDR.

As an auxiliary arithmetic check, a standard-library Python calculation with random seed 4702 compared these three jump formulas with direct largest-rank BH at u_r plus or minus 10^-7 for 20,000 independent pairs (A,B). All 60,000 comparisons agreed. The exact arguments above, rather than this finite numerical check, establish the failed NOT verdict.

## Failure

NOT fails: this three-rank mixed-label model satisfies exact copying, finite signed face moments, the explicit exponential all-or-none bound, and the asserted derivative with both signs of rank-three cascades retained.
