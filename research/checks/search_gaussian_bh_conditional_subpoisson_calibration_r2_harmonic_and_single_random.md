---
type: search_round
title: >-
  Harmonic-mixture and single-random-null obstructions to conditional
  calibration counterexamples
target_asset: gaussian_bh_conditional_subpoisson_calibration
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_conditional_subpoisson_calibration_r2_s1_harmonic_disjoint_clusters
  - cand_gaussian_bh_conditional_subpoisson_calibration_r2_s2_harmonic_blocks
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:26:54.626Z'
extension_version: 0.0.4
---

## Obstructions

- The two round-2 candidates are independent instances of one failed family, the disjoint harmonic rank mixture with proposed $K=1$. They are retained separately as cand_gaussian_bh_conditional_subpoisson_calibration_r2_s1_harmonic_disjoint_clusters (first failing check H5) and cand_gaussian_bh_conditional_subpoisson_calibration_r2_s2_harmonic_blocks (first failing check H4). For mixture weights $\mathbb P(J=j)=q/j$, and a block of $j$ null p-values at $qj/N$, the count at $s=2q/N$ is $1$ on $J=1$, $2$ on $J=2$, and $0$ otherwise. Thus $\mathbb E[2^{C(s)}]=1+(5/2)q$, whereas the proposed sub-Poisson bound is $\exp(2q)$. For $0<q<1/10$, $\exp(2q)<1/(1-2q)<1+(5/2)q$, so this family fails the count-mgf hypothesis throughout the nontrivial $K=1$ regime $q<1/(4e)$. The first candidate's exact instance gives $11/10>\exp(2/25)$. Its exact first-moment calibration therefore does not rescue the required exponential bound. This obstruction concerns the proposed $K=1$; it does not assert that no larger calibration factor can make the hypothesis hold.
- Under a final conditioning that makes every p-value except at most one original null coordinate deterministic, the first-moment consequence alone yields conditional FDR at most $2qK$. To see this when there is one random null $i$, let $D(s)$ count the deterministic original nulls and let $r_*$ be the BH rejection count after setting $P_i=0$. Then $D(s)\le\mathbb E[C(s)\mid\mathcal H]\le NKs$, so the deterministic-null part of FDP is at most $qK$ at every realized rank. The ordinary BH leave-one-out identity states that whenever $i$ is rejected, the actual rank is the fixed $r_*\ge1$, with rejection event $P_i\le qr_*/N$. Its conditional expected FDP contribution is at most $\mathbb E[C(qr_*/N)\mid\mathcal H]/r_*\le qK$. The finite possible values of the $\mathcal H$-measurable rank permit evaluation using the common full-measure set. This excludes attempts to exploit conditioning while leaving only one random null coordinate; it makes no claim for two or more.
- Earlier boundary obstructions remain in force: capped regimes have the trivial bound $1$; an empty original null set gives FDP zero; finite $K$ excludes conditional null mass at zero; deterministic conditional null counts give FDP at most $qK$; and $N=1$ gives conditional FDR at most $qK$. The aggregate first-moment bound $qKH_N$ also rules out all sample sizes with $H_N\le4e$, but grows with $N$.
- The earlier singular antithetic Gaussian pair remains a failed conclusion check: its FDR is exactly $q$, below the claimed capped bound. This excludes that recorded family rather than arbitrary singular Gaussian laws.

## Limitations

- Round 2 added two failed candidates from the same conceptual family and no surviving counterexample. Both stopped at a failed exponential-count hypothesis; their later conclusion-failure checks remain unknown.
- No candidate was found with large $N$, at least two conditionally random original null coordinates, an adverse actual BH rank, and all deterministic-threshold conditional sub-Poisson inequalities simultaneously valid. The available harmonic bound does not settle the dimension-uniform $4e$ constant.
- This round did not establish the Gaussian sufficient condition for a general singular PSD covariance matrix with nonpositive off-diagonal entries under the full final conditioning, nor did it find a counterexample to that sufficient condition.
- The summary uses the supplied candidate failure lines and earlier reports, supplemented by the displayed algebraic family obstruction and single-random-null argument. It does not independently re-verify the omitted candidate bodies or inspect the target proof. No duplicate idea node was created for these mechanisms.
