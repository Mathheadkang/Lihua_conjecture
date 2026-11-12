---
type: falsification_check
title: 'Falsification check: gaussian_bh_two_to_one_signed_duplication'
target_asset: gaussian_bh_two_to_one_signed_duplication
outcome: no_counterexample_found
statement_digest: 987e0b4167580298c08435b5d415d205e1f3153780e8613a7e16afb82038f6a6
performed_by: unknown
created_at: '2026-11-07T03:00:01.053Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 1, known_counterexamples: no plausible candidate.
- Round 1, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 2, small_cases: no plausible candidate.
- Round 2, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 3, known_counterexamples: no plausible candidate.
- Round 3, extremal: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 4, known_counterexamples: no plausible candidate.
- Round 4, extremal: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Round 5, known_counterexamples: no plausible candidate.
- Round 5, extremal: no plausible candidate.
- Round 6, boundary_degenerate: no plausible candidate.
- Round 6, small_cases: no plausible candidate.
- Round 6, drop_hypothesis: no plausible candidate.
- Round 6, known_counterexamples: no plausible candidate.
- Round 6, extremal: no plausible candidate.
- Round 7, boundary_degenerate: no plausible candidate.
- Round 7, small_cases: no plausible candidate.
- Round 7, drop_hypothesis: no plausible candidate.
- Round 7, known_counterexamples: no plausible candidate.
- Round 7, extremal: no plausible candidate.
- Round 8, boundary_degenerate: no plausible candidate.
- Round 8, small_cases: no plausible candidate.
- Round 8, drop_hypothesis: no plausible candidate.
- Round 8, known_counterexamples: no plausible candidate.
- Round 8, extremal: no plausible candidate.
- Round 9, boundary_degenerate: no plausible candidate.
- Round 9, small_cases: no plausible candidate.
- Round 9, drop_hypothesis: no plausible candidate.
- Round 9, known_counterexamples: no plausible candidate.
- Round 9, extremal: no plausible candidate.
- Round 10, boundary_degenerate: no plausible candidate.
- Round 10, small_cases: no plausible candidate.
- Round 10, drop_hypothesis: no plausible candidate.
- Round 10, known_counterexamples: no plausible candidate.
- Round 10, extremal: no plausible candidate.
- Obstruction: Boundary, zero-statistic, and threshold-tie constructions cannot make both signed copies reject: the larger member of each complementary p-value pair is at least one half, whereas every duplicated BH threshold is at most q, strictly below one half.
- Obstruction: Small finite models and large-dimensional extremal configurations retain the same potentially qualifying ranks: the smaller signed p-values are exactly one half of the original two-sided p-values, and their first N thresholds are qk/(2N).
- Obstruction: Singular or degenerate covariance does not invalidate Gaussian admissibility of the signed vector: signed duplication is a linear image and its covariance has unit diagonal and is positive semidefinite.
- Obstruction: A false-rejection-count reversal cannot arise merely by changing nonzero means: each rejected original two-sided true null contributes a rejected signed coordinate with zero mean; additional negative signed means can only add one-sided true-null rejections.
- Obstruction: Threshold ties cannot increase a BH rejection set beyond its largest qualifying rank: an additional p-value at or below that rank's threshold would itself produce a larger qualifying rank. This rules out a discrepancy caused solely by multiplicities in the signed and original orderings.
- Obstruction: Exact rational small-case checks reported for 14,040 configurations with N from 1 to 4 found no discrepancy in the largest qualifying rank, rejection set, multiplicity, or zero-rejection convention. These checks rule out only the tested finite configurations.
- Obstruction: A proposed boundary mechanism at q=1/2 and t=0 fails the strict hypothesis q<1/2. Within the stated interval, no complementary signed p-value of at least one half can pass a BH threshold.
- Obstruction: Dependence assumptions and monotonicity in negative null means are unnecessary for comparing expectations of a valid pathwise inequality: the duplicated Gaussian law is the pushforward of the original law. Thus their absence does not itself provide a counterexample.
- Obstruction: Allowing dimension and means to vary arbitrarily with q, or a worst-case supremum to be unattained, does not obstruct a pointwise finite-model reduction: each finite original model maps to an admissible even-dimensional one-sided model already included in the unrestricted one-sided supremum.
- Obstruction: Attempts requiring zero tests, level zero, or nonfinite realized statistics fail the stated positive-dimension, positive-level, or real-valued hypotheses; floating-point tail underflow does not supply a real-valued counterexample.
- Obstruction: Changing a mean through zero cannot remove the rejected one-sided true-null copy associated with an original two-sided true null. The reported 54,240 mean-sign, observation-sign, and rejection-label configurations with dimensions one through four found no false-rejection reversal, conditional on the asserted rejection correspondence; this is a finite bookkeeping probe only.
- Obstruction: Selection-dependent true-null labels require random mean labels, whereas the model fixes its mean vector and both true-null sets before sampling. Such label constructions therefore fail the fixed-model hypotheses.
- Obstruction: Rare-event sequences and very unbalanced rejection counts cannot reverse an established pathwise FDP comparison: the rejection denominators coincide and each FDP is bounded by one, so expectation does not require an additional integrability assumption.
- Obstruction: Restricting the Gaussian law to a singular support cannot create a counterexample to an identity asserted for every real realization. No new singular-support mechanism beyond the existing board was found in this round.
- Obstruction: The exact one-test FDR calculation does not reverse the proposed comparison: with $c=\Phi^{-1}(1-q/2)$, both procedures have FDR $q$ when $\theta=0$, while for $\theta\ne0$ the original two-sided FDR is zero and the duplicated one-sided FDR is $\Phi(-c-|\theta|)\geq0$.
- Obstruction: Dropping Gaussianity or unit variance does not itself break the proposed deterministic rejection correspondence: the complementary normal-tail p-values are still defined for every finite realized vector. Gaussianity and unit diagonal instead ensure that the transformed sampling law belongs to the stipulated model class.
- Obstruction: Negative signed means do not introduce anti-conservative one-sided null calibration. For a unit-variance Gaussian coordinate of mean $\mu\leq0$ and $0<a<1$, $\mathbb P\{\overline\Phi(X)\leq a\}=\overline\Phi(\Phi^{-1}(1-a)-\mu)\leq a$.
- Obstruction: Joint sequences with dimension increasing and $q$ approaching $1/2$ retain, in every finite model with $q<1/2$, a strictly positive gap between every BH threshold and the larger member of each complementary signed p-value pair. Reaching the excluded limiting level is not an admissible finite-model exception.
- Obstruction: Arbitrary-dependence BH inflation examples built from unrelated p-value arrays do not supply the prescribed signed Gaussian construction: each signed pair must be complementary, and its smaller member must equal half the corresponding original two-sided p-value. A pathology that discards these restrictions is outside the target family.
- Obstruction: Changing the testing level between the original and duplicated procedures does not refute the statement, which compares ordinary BH at the same fixed level in both models.
- Obstruction: Boundary, small-case, hypothesis-edge, and extremal searches identified no new admissible mechanism beyond the families already excluded on the search board; changing only a parameter of those families supplies no new candidate.
- Obstruction: The boundary and small-case directions identified no admissible family beyond the existing zero, threshold-tie, endpoint, singular-support, finite-rank, and null-label checks; changing only a parameter does not escape their recorded obstructions.
- Obstruction: The hypothesis-edge and known-pathology directions identified no mechanism that retains the complementary signed-pair construction, fixed mean and true-null labels, and the same testing level while escaping the existing board.
- Obstruction: The extremal direction identified no admissible family beyond the recorded varying-dimension, rare-event, and strict-level-limit checks; the excluded limiting endpoint is not a finite model satisfying the hypotheses.
- Obstruction: The boundary direction identified no admissible family beyond the recorded zero, threshold-tie, endpoint, and singular-support obstructions.
- Obstruction: The small-case direction identified no new family beyond the existing rank, multiplicity, null-label, and one-test checks; repeating a parameter choice does not escape those obstructions.
- Obstruction: The hypothesis-edge direction identified no new mechanism retaining the strict level interval, fixed mean labels, finite real realizations, and admissible singular covariance.
- Obstruction: The known-pathology direction identified no new family satisfying the complementary signed-pair construction, fixed labels, same testing level, and one-sided null calibration simultaneously.
- Obstruction: The extremal direction identified no new family beyond the recorded varying-dimension, rare-event, and strict-level-limit checks.
- Obstruction: The boundary direction found no admissible family beyond the recorded zero, threshold-tie, endpoint, and singular-support obstructions.
- Obstruction: The small-case direction found no family beyond the existing rank, multiplicity, null-label, and one-test checks; repeating a parameter choice does not escape those obstructions.
- Obstruction: The hypothesis-edge direction found no new mechanism that preserves the strict level interval, fixed mean labels, finite real realizations, and admissible singular covariance while escaping the recorded restrictions.
- Obstruction: The known-pathology direction found no new family satisfying the complementary signed-pair construction, fixed labels, same testing level, and one-sided null calibration simultaneously.
- Obstruction: The extremal direction found no new admissible family beyond the recorded varying-dimension, rare-event, and strict-level-limit checks.
- Obstruction: The boundary direction found no new admissible family beyond the recorded zero, threshold-tie, endpoint, and singular-support restrictions.
- Obstruction: The small-case direction found no new family beyond the recorded rank, multiplicity, null-label, and one-test checks; changing only a parameter does not escape those restrictions.
- Obstruction: The hypothesis-edge direction found no new mechanism preserving the strict level interval, fixed mean labels, finite real realizations, and admissible singular covariance.
- Obstruction: The known-pathology direction found no new family satisfying the complementary signed-pair construction, fixed true-null labels, same testing level, and one-sided null calibration simultaneously.
- Obstruction: The extremal direction found no new admissible family beyond the recorded varying-dimension, rare-event, and strict-level-limit restrictions.
- Obstruction: The boundary direction found no new admissible family beyond the recorded zero, threshold-tie, endpoint, and singular-support restrictions.
- Obstruction: The small-case direction found no new family beyond the recorded finite-rank, multiplicity, null-label, and one-test checks; changing only a parameter does not escape their obstructions.
- Obstruction: The hypothesis-edge direction found no new mechanism preserving the strict level interval, fixed mean labels, finite real realizations, and admissible singular covariance.
- Obstruction: The known-pathology direction found no new family satisfying the complementary signed-pair construction, fixed true-null labels, same testing level, and one-sided null calibration simultaneously.
- Obstruction: The extremal direction found no new admissible family beyond the recorded varying-dimension, rare-event, and strict-level-limit restrictions.

## Limitations

All five directions returned NONE and wrote no candidate files. This round identified no new admissible family and adds no numerical evidence or general proof. The ten prescribed search rounds are complete, but absence of a counterexample is not a proof. The finite-rank and rejection-set identities, false-rejection domination, and unrestricted supremum comparison still require formal proof. Both main uniform finite-constant upper bounds remain unresolved. No duplicate approach idea is recorded.

Object search: 0 candidate(s) in 10 round(s).
