---
type: idea
title: Exact antisymmetric basis-exchange currents for the global Parseval FDP cover
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - one-sided
  - determinantal-cover
  - signed-basis-current
  - native-plan-first-tests
---

## Purpose and status

This develops the root's global random-basis cover idea_ee0372421118 beyond static moments. The following exact finite algebra expresses changing determinant weights as antisymmetric basis-exchange currents. It is a concrete signed resummation identity, not a final FDR estimate. The derivation is agent draft mathematics and has not been independently verified by the native loop.

## Smooth Parseval frame and a skew column generator

Let F(s) be a smooth d-by-n real matrix with F F^T=I_d. Columns include weighted physical null directions and auxiliary completion directions; auxiliary columns are never tests. Write A=F'F^T, which is skew-symmetric because (FF^T)'=0. The n-by-n matrix
$$
\Omega=F^{\mathsf T}F'-F'^{\mathsf T}F-F^{\mathsf T}AF
$$
is skew-symmetric and satisfies F'=F Omega. Indeed F F'^T=-A, so multiplication on the left by F cancels the two extra A F terms.

For an increasing d-index set B, put d_B=det(F_B), alpha_B=d_B^2. If C=B minus i plus j with i in B and j outside B, let epsilon(B,i,j) be the sign required to sort the replaced column list. Multilinearity of the determinant gives
$$
d'_B=\sum_{i\in B,\ j\notin B}
\Omega_{ji}\epsilon(B,i,j)d_C.
$$
Terms replacing one column by a different column already in B vanish, and the diagonal skew terms vanish.

Define
$$
J_{BC}=2\Omega_{ji}\epsilon(B,i,j)d_Bd_C
$$
for adjacent bases. The replacement signs agree under reversal and Omega changes sign, so J_CB=-J_BC. Exactly,
$$
\alpha'_B=\sum_C J_{BC},\qquad
\sum_B\alpha'_B H_B
=\frac12\sum_{B,C}J_{BC}(H_B-H_C). \tag{EX}
$$
These are polynomial identities in the determinant amplitudes; no inverse basis matrix is used, and a zero determinant causes no division.

## Pairing with the actual physical FDP cover

Use uniform physical null weights c=1/p and the unchanged original full BH rank R. At a fixed realized score sample let
$$
H_B=\frac p{R\vee1}
\sum_{i\in B\cap I_0}1_{\{i\in\mathcal R_q\}}.
$$
If C exchanges i with j, set I_i=1{i is a physical selected null}, and I_i=0 for auxiliary indices. Then
$$
H_B-H_C=\frac p{R\vee1}(I_i-I_j).
$$
Consequently the true determinant-weight current is supported only on swaps across the selected/unselected null boundary. Both-selected and neither-selected exchanges contribute zero. This is more specific than an absolute sum of basis motions.

When p varies, the explicit derivative of the importance weights must be retained. The root's marginal identity sum_{B containing i}alpha_B/c=1 shows that this derivative cancels the total current term pathwise for a fixed score sample. Equivalently, if K_B is the number of selected physical null columns,
$$
\frac12\sum_{B,C}J_{BC}(K_B-K_C)
=-\frac{p'}p E_B K_B.
$$
This cancellation concerns changes of the cover only. It does not cancel physical Gaussian score velocities, rank-interface jumps, or the Mills drift in idea_0b153b121437.

## A stable smooth representation and gauge check

The determinant law may be constructed canonically from the true-null Gram matrix Gamma_00, in its m-dimensional canonical square-root realization. Orthogonal changes of the actual latent embedding do not change this Gram. To avoid changes in the rank of the slack completion, one may take physical c=1/(2p), p=||Gamma_00||op, and complete the frame using the columns of (I-c Gamma_00)^{1/2}; the slack is then at least I/2. The inverse importance is 2p. The exact FDP and replication identities remain true with those weights, and the second-moment mass bound changes only by a universal factor.

On the symmetric covariance interpolation Gamma_00(s)=(1-s)I+s Gamma_00(1), its largest eigenvalue is 1-s+s p(1), so this physical weight is smooth. The canonical completion is smooth as well. Unused latent orthogonal directions can be completed by deterministic columns, selected in every basis and carrying no physical label.

This representation prevents spurious currents from an arbitrary rotation of the null span relative to alternatives. In particular if the true-null Gram stays I, the canonical determinant law is constant, even if null-alternative correlations change. Thus basis currents alone cannot solve the independent-null/strongly dependent-alternative case.

## Concrete kernel compatibility and remaining gate

The determinant-weighted marked pair estimate in idea_cb8b42129f28 controls both-selected Gaussian tail pairs and gives a u^{-2} determinant gain. Formula (EX), however, exposes selected/unselected exchanges. One must either match these mixed events to signed physical rank-interface terms before estimating, or supply a mixed-event/importance-entropy payment. Treating every current as a both-selected pair would be false.

An immediate warning is that a conditional surface bound for a mixed pair cannot generally gain a factor sqrt(1-rho): exposing the average at its threshold can leave a nonzero conditional sign-disagreement probability even as rho tends to one. The determinant/current amplitudes and the original physical rank denominator must therefore remain together.

The exact current identity is a real additional finite mechanism for such a matching attempt. A pending main plan still needs an explicit, checkable matching or coefficient allocation, rather than renaming the final averaged signed kernel as a proved budget. No project, dependency, approval, budget or loop state is changed.
