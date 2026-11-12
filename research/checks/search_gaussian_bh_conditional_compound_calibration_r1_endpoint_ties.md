---
type: search_round
title: Conditional compound calibration round 1 - endpoint atoms and actual BH ties
target_asset: gaussian_bh_conditional_compound_calibration
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_conditional_compound_calibration_r1_s1_empty_null_zero
  - cand_gaussian_bh_conditional_compound_calibration_r1_s1_no_rejection
  - cand_gaussian_bh_conditional_compound_calibration_r1_s1_null_zero
  - cand_gaussian_bh_conditional_compound_calibration_r1_s1_top_rank_tie
  - cand_gaussian_bh_conditional_compound_calibration_r1_s2_tied_atoms
  - >-
    cand_gaussian_bh_conditional_compound_calibration_r1_s3_conditional_zero_atom
  - cand_gaussian_bh_conditional_compound_calibration_r1_s3_cutoff_atom
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:51:13.112Z'
extension_version: 0.0.4
---

## Obstructions

- Empty-null laws and laws with no actual BH rejections cannot violate the bound: respectively $V=0$ or $R=0$, so $V/(R\vee1)=0$. This rules out these families without assumptions about individual conditional superuniformity.
- Every conditional state with a positive true-null atom at zero has $M_q=\infty$, since the summed null CDF stays bounded away from zero as $t\downarrow0$. The prescribed bound is then $1$, which FDP cannot exceed. More generally, any state with $2qK_q\ge1$ is protected by the same cap. The conditionally deterministic common-zero construction therefore does not refute the statement: given $Z=0$ its coordinates are independent Dirac laws, its actual largest BH rank is $2$, and FDP equals the bound $1$; given $Z=1$ there are no rejections. Marginal dependence by itself does not violate conditional independence.
- Deterministic common-p-value ties at $x\in(0,q]$ cannot produce a violation by forcing the largest BH rank: rank $N$ qualifies under the non-strict comparison, hence $R=N$ and FDP equals $\gamma=|I_0|/N$. The endpoint-inclusive envelope satisfies $M_q\ge\gamma/x$, so $\min\{1,2qK_q\}\ge\gamma$. The tested top-rank tie has $N=3$, $q=x=1/10$, $\gamma=1/3$, and bound $2/3$. Stopping at the first failed lower rank would describe a different rejection rule.
- A cutoff-atom strategy that relies on omitting $t=q$ does not apply to this target: the envelope explicitly counts all null mass at that endpoint. In the tested $N=2$ law with a null atom of probability $1/2$ at $q=1/10$ and a deterministic nonnull at $q$, equality at rank $2$ gives conditional FDR $1/4$, while $M_q=K_q=5/2$ gives bound $1/2$. Replacing the envelope by a supremum over $t<q$ would give the false bound $1/5$, but changes the statement. Interior atoms likewise remain visible to rational levels approaching from above by right continuity.

## Limitations

- All seven recorded candidates in round 1 failed at NOT; none survived as a counterexample. This is a bounded search result, not a proof of the conditional lemma or of the universal constant $2$.
- The independent four-coordinate tied-atom law was checked by its exact eight-outcome enumeration using original null labels, largest qualifying ranks, and non-strict comparisons. It gives conditional expected FDP $653/1536<3/4=\min\{1,2qK_q\}$, with $M_q=K_q=15/4$. Its tied outcome with one small null absent still qualifies at rank $3$ although rank $2$ fails. This establishes failure of that specific candidate; it does not exclude arbitrary finite product laws with ties or certify a general small-dimension bound.
- The round covers empty-null/no-rejection cases, several degenerate conditional laws, an exact finite product law, and endpoint atoms. It does not exhaust higher dimensions, general continuous or mixed conditional laws, heterogeneous conditional CDFs with finite nonsaturated envelopes, or general nondegenerate dependence of the kernels on $Z$. The common-zero example tests only a two-state, conditionally deterministic kernel.
- Dropping mutual conditional independence cannot yield a counterexample satisfying the stated hypotheses. The recorded direction name drop_hypothesis does not itself mean either of its two listed candidates fails an assumption: both recorded candidates pass their hypothesis checks and fail NOT. No assertion about calibration without conditional independence follows from this round.
- The almost-sure bound for arbitrary regular conditional distributions, its integration to the unconditional conclusion, optimality of constants, and any Gaussian order estimate remain unproved by this search. Neither unrestricted main theorem nor removal of a noise floor follows from these tests.
