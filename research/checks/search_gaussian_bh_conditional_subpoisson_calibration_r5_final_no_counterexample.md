---
type: search_round
title: Final prescribed conditional-calibration search finds no counterexample
target_asset: gaussian_bh_conditional_subpoisson_calibration
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:34:00.242Z'
extension_version: 0.0.4
---

## Obstructions

- The complete actual-false-rejection-index Chernoff mechanism recorded in round 4 and idea_e34ba60a4ca5 continues to block the proposed boundary and large-dependence families whenever the stated count-mgf hypothesis holds. The final round found no new object outside that mechanism's coverage. Its proof is not duplicated here, and no duplicate idea node is created.
- Ties and cutoff equality do not open a boundary gap. Ordinary largest-rank BH with the specified non-strict comparisons retains the original null labels and satisfies $V=C(qR/N)$ at every positive actual rank. The auxiliary-rank identity therefore retains tied rejections. Equality at the split $d_v=2eqK$ belongs to the low-ratio part of the already recorded estimate; no limiting argument or division by a zero rank is needed. At $V=0$ the FDP contribution is zero, and the cap covers $K=\infty$.
- Conditional atoms, irrational thresholds, and random $\mathcal H$-measurable calibration factors remain covered by the common conditional-law/full-measure-set requirement and the right-continuous CDF calculation recorded earlier. In particular, the endpoint $q$ is explicitly included, and the finite BH grid permits selection of the conditional auxiliary ranks without choosing threshold-dependent exceptional sets.
- Further conditioning that destroys Gaussianity or makes an off-diagonal residual covariance positive does not refute the Gaussian sufficient-condition clause: that clause requires Gaussianity and nonpositive residual covariance after the complete alternative vector has already been included in the final $\mathcal H$. The statement asserts no preservation under additional conditioning. Failure of that sufficient criterion also does not establish failure of the general lemma; the count-mgf hypothesis would have to be checked separately under the proposed final conditioning.

## Limitations

- Round 5, the final prescribed search round, produced no candidate files and no surviving counterexample. Across the five rounds the three preserved candidate records all failed: the singular antithetic pair failed its conclusion-failure check, and the two independently recorded harmonic-mixture instances failed the count-mgf hypothesis.
- This is a completed search summary, not a native proof execution, independent proof-verification verdict, or researcher approval. The reconstructed count-to-actual-rank estimate and Gaussian interpolation mechanism still need to be presented and checked through those distinct native stages.
- The summary uses only the current pack's target statement, board, and round reports; it does not inspect the omitted target proof, candidate bodies, or saved idea bodies. The target and previous records remain unchanged.
- No result here guarantees a small finite Gaussian calibration factor $K$, preserves covariance signs under further conditioning, or establishes an unrestricted Gaussian order bound.
