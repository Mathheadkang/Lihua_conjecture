---
type: plan
title: Prove signed duplication by exact finite BH ranks
status: succeeded
target_asset: gaussian_bh_two_to_one_signed_duplication
inspired_by:
  - idea_63cf0f96831d
proof_digest: cbdbbe39b07cec40914998bdc9d0ee8c2eee1d01065c4cb8ea9ff4a2e9f5f82b
statement_digest: 987e0b4167580298c08435b5d415d205e1f3153780e8613a7e16afb82038f6a6
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
  gaussian_worst_case_bh_fdr: 5c3438b5ed0ad228d4c497cb1bba3bc00df045464de3732cd69e217ebf9b28a1
verified_proof_digest: cbdbbe39b07cec40914998bdc9d0ee8c2eee1d01065c4cb8ea9ff4a2e9f5f82b
---

## Goal

Target: [Exact signed-duplication reduction from two-sided to one-sided Gaussian BH](../assets/gaussian_bh_two_to_one_signed_duplication.md).

Prove the frozen statement for every finite admissible Gaussian model and every $0<q<1/2$, including singular covariance, ties, zero statistics, and zero rejections. No bound on either worst-case FDR function is assumed.

## Plan

1. [x] Prove that signed duplication is an admissible Gaussian model directly from the definition of joint Gaussianity: for vectors $a,b\in\mathbb R^N$, the centered linear form of $X$ is $(a-b)^{\mathsf T}(T-\theta)$ and its variance is $(a-b)^{\mathsf T}\Sigma(a-b)$. Check symmetry, positive semidefiniteness, and every unit diagonal entry of $\widetilde\Sigma$ without using a density or inverse covariance.
2. [x] Establish the finite BH bookkeeping fact that the cardinality of the rejection set equals the largest qualifying rank for any p-value vector, with non-strict comparisons and multiplicities. If the selected rank is positive and more indices pass its threshold, their larger cardinality itself qualifies, contradicting maximality; if no positive rank qualifies, use the prescribed empty set.
3. [x] For a fixed real vector $t$, use $\overline\Phi(-t_i)=1-\overline\Phi(t_i)$ to separate each signed pair into $a_i=\overline\Phi(|t_i|)=p_i/2\leq1/2$ and $b_i=1-a_i\geq1/2$. Prove numerically ordered identities $u_{(k)}=p_{(k)}/2$ for $1\leq k\leq N$, including ties at $1/2$, and $u_{(k)}\geq1/2$ for $N<k\leq2N$. Since every duplicated BH threshold is at most $q<1/2$, exclude all ranks larger than $N$ and match each remaining qualifying rank exactly with the original BH inequality. Conclude equal selected ranks and, by step 2, $R_1=R_2$.
4. [x] Match the threshold rejection sets using their common selected rank. If it is zero both sets are empty. Otherwise the duplicated threshold is $qR_2/(2N)<1/2$, so only the smaller signed member can be rejected, exactly when $p_i\leq qR_2/N$. Identify that member by $t_i>0$ or $t_i<0$. If $t_i=0$, both signed p-values equal $1/2$ and the original p-value equals $1$, so none is rejected. This proves the exact asserted rejection-set identity, including all ties at either threshold.
5. [x] Compare false-rejection counts with the fixed mean vector. For $\theta_i=0$, both signed means vanish and the unique rejected copy of every rejected original index is a one-sided true null. These copies are distinct across original indices, proving $V_1\geq V_2$. For $\theta_i\ne0$, verify exactly one signed mean is negative and its possible rejection only adds to $V_1$; no monotonicity in means is invoked.
6. [x] Combine steps 3--5 with the common denominator $R_1\vee1=R_2\vee1$ to obtain the pointwise FDP inequality, explicitly treating zero rejections. Take expectation under the original Gaussian law, identify the signed vector's pushforward law using step 1, and obtain the stated finite-model FDR comparison. For each fixed $q$, bound each duplicated admissible finite model by the unrestricted one-sided supremum and then take the two-sided supremum. No attainment, fixed dimension, limit exchange, or main-goal upper bound is needed.

## Verification

Check that every claim in the frozen target follows from the six steps: admissibility first; exact selected ranks, actual rejection cardinalities, and the complete signed rejection-set identity next; fixed-null false-count domination and the zero-rejection convention afterward; finally finite-model expectations and the unrestricted suprema at the same level. In particular, check that threshold ties are handled by non-strict inequalities and multiplicity rather than by a probability-zero exception. A fresh verifier should independently reconstruct the rank argument and confirm the proof needs neither Gaussian nonsingularity nor any unresolved order or sharp-constant theorem. The conclusion is solely $F_2(q)\leq F_1(q)$ for $0<q<1/2$.

## Assumed definitions

Use only the approved definitions [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md). No draft definition or unproved dependency is assumed. The cited approach idea is provenance, not a premise. The supplied pack lists no library analogue, and native library searches for signed duplication and Benjamini-Hochberg ranks found no matching result to adapt.

## Outcome

The complete proof is in the target asset's canonical `## Proof`. All six checklist steps are proved using only the five approved definitions listed above. The statement is unchanged, the asset remains draft, and independent verification is still required. The conclusion is the standalone same-level inequality $F_2(q)\leq F_1(q)$ for $0<q<1/2$; neither unresolved main order bound is assumed or proved.


## Verdict

confirmed

Independently checked the canonical Statement and Proof against all five approved definitions. The signed Gaussian linear image has the stated mean, unit diagonal and positive semidefinite covariance, including singular laws. The maximal-rank argument proves that rejection cardinality equals the selected rank with multiplicities and non-strict comparisons; the signed order statistics then give the exact same-level finite-rank and rejection-set correspondence for every real observation, including ties, zero coordinates and no rejections. Each rejected original zero-mean null maps injectively to a rejected signed true null; negative one-sided null means can only increase the signed false count. The common denominator, bounded expectations and pointwise domination by the one-sided supremum justify the FDR and worst-case inequalities without attainment, a limit exchange, or any unproved upper bound. No proof gap requiring repair was found. An auxiliary exact-rational check passed 11,144 finite-rank boundary cases; the all-dimension conclusion follows from the proof, not this finite check.
