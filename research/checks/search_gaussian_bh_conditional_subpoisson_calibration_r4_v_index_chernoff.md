---
type: search_round
title: >-
  Full false-rejection-index Chernoff obstruction to conditional calibration
  counterexamples
target_asset: gaussian_bh_conditional_subpoisson_calibration
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:32:26.405Z'
extension_version: 0.0.4
---

## Obstructions

- Random thresholds and calibration factors do not evade the stipulated common full-measure set. A sum of conditional p-value CDFs is right-continuous in $s$, so for every interior $s<q$ its ratio to $Ns$ is the limit along rationals decreasing to $s$. The endpoint $q$ is included separately; a conditional atom exactly at $q$ is therefore retained. For the actual-rank argument only the finite BH grid $qr/N$ is needed. An $\mathcal H$-measurable rank selects among these finitely many inequalities on the same full-measure set. After fixing the conditional law, finite random $K$ and nonnegative $\mathcal H$-measurable Chernoff exponents are ordinary numerical parameters of that law; the common-set hypothesis prevents selection of parameter-specific exceptional sets.
- If the actual positive BH rank has conditional support contained in an $\mathcal H$-measurable set $S\subseteq\{1,\ldots,N\}$ of cardinality at most $L$, the first-moment implication alone gives $\mathbb E[\operatorname{FDP}\mid\mathcal H]\le\min\{1,LqK\}$. Indeed, on $\{R=r\}$ the null count is $V=C(qr/N)$, and summing $\mathbb E[C(qr/N)\mathbf1_{\{R=r\}}\mid\mathcal H]/r$ over $r\in S$ is at most $\sum_{r\in S}qK$. Thus at most ten conditionally supported positive ranks cannot refute the $4e$ bound, regardless of the number of random nulls.
- The complete alternative vector in $\mathcal H$ fixes a total-rank representative for every possible actual false-rejection count. For $v=0,\ldots,|I_0|$, define $r_v$ as the BH rejection count of an auxiliary vector retaining the actual alternative p-values and replacing the original null coordinates by $v$ zeros and the remaining ones. Its rank depends only on $v$ and $\mathcal H$, not on the positions of those zeros. On the original event $\{V=v\}$, the original actual rank satisfies $R=r_v$. At the original threshold the auxiliary vector has the same count; at any larger BH threshold its null count $v$ is no greater than the original null count, while the alternatives are identical. Therefore replacement creates no larger qualifying rank and preserves the actual one. For $v\ge1$, $r_v\ge v$. This is an auxiliary identity for the original BH procedure, not a change of labels or a rerun used for reporting FDP.
- The false-rejection-index identity yields the full dimension-uniform Chernoff obstruction. Fix a conditional law with finite $K$, put $a=qK$ and $d_v=v/r_v$ for $v\ge1$. The events with $d_v\le2ea$ contribute at most $2ea$ to conditional expected FDP because their probabilities sum to at most one. For every remaining $v$, put $\mu_v=ar_v$ and apply the count-mgf bound at $s=qr_v/N$ with $\lambda_v=\log(v/\mu_v)=\log(d_v/a)>0$. Since $\{V=v\}\subseteq\{C(qr_v/N)\ge v\}$, Chernoff gives $\mathbb P(V=v\mid\mathcal H)\le\exp\{-v\log(v/\mu_v)+v-\mu_v\}\le(ea/d_v)^v$. Consequently its weighted contribution is at most $d_v(ea/d_v)^v=ea(ea/d_v)^{v-1}\le ea\,2^{1-v}$. Summing over all high-ratio indices is at most $2ea$. Combining the two parts gives $4ea$, and the pathwise bound FDP at most one supplies the cap; $K=\infty$ is already capped. This reconstructs the remaining count-mgf-to-actual-rank mechanism without conditional null independence. The same mechanism is already saved in idea_e34ba60a4ca5; no duplicate idea was created.

## Limitations

- Round 4 produced no new candidate files and no surviving counterexample. The earlier three candidate records remain intact.
- The dimension-uniform mechanism is reconstructed above as a search obstruction. This search-round record is not a native proof execution, independent proof-verification verdict, or researcher approval of the target; those steps remain separate.
- The round did not inspect the target's omitted proof or any omitted candidate body. Its argument uses the supplied statement and the earlier search reports, with the full rank identity and Chernoff algebra made explicit here.
- The Gaussian sufficient-condition argument remains the interpolation mechanism from the earlier round. Neither that argument nor the present obstruction supplies a small finite $K$ for arbitrary Gaussian conditional means and variances, or establishes an unrestricted Gaussian order bound.
