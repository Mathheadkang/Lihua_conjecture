---
type: falsification_check
title: 'Falsification check: gaussian_bh_global_particle_potential_certificate'
target_asset: gaussian_bh_global_particle_potential_certificate
outcome: no_counterexample_found
statement_digest: 5c18aaddd67e681c31bff48ee957bb54c0681a855d0bfd853d043ea65e593f90
performed_by: unknown
created_at: '2026-11-09T09:50:07.704Z'
extension_version: 0.0.4
---

## Cases checked

- Round 5, boundary_degenerate: cand_gaussian_bh_global_particle_potential_certificate_r5_s1_all_false_boundary failed — H4 fails: the zero-mean all-true lawful competitor strictly improves the normalized regularized objective at the same level.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: An arbitrary lawful directing law with a failed stationarity or potential inequality cannot refute this target without certification that it is a genuine deterministic canonical global maximizer over the entire lawful comparison class. Such examples leave the global-maximizer hypothesis unverified; the round did not certify a family of actual global maximizers with this failure.
- Obstruction: No mathematical obstruction ruling out a family of fully admissible counterexamples was established. The supplied round report records boundary and minimal-example checks, with explicit quantiles and actual-record geometry consistent with the statement, and the candidate list is empty.
- Obstruction: Unit-loading boundary examples do not remove private smoothing: at $\|v\|=1$, the stated formula gives $c_s(v)^2=s^2>0$. A proposed singular-kernel failure based only on vanishing residual loading variance therefore fails; this does not establish the required uniform reciprocal-density bounds.
- Obstruction: If one signed weight $w_{X,\pm}$ vanishes almost everywhere for the defining expectations, every defined generator for that sign has $(G_\pm^t,c_\pm^t)=(0,0)$. Provided the hybrid selector family is nonempty, its potential hull is the zero singleton, so this degeneracy alone cannot refute its compactness. It does not prove selector nonemptiness in general.
- Obstruction: Noncompactness of the infinite-dimensional strong Hilbert ball alone does not refute compactness of the averaged potential classes in their declared evaluation topology: the parameter domain and the set of functions on it are different spaces. The report supplies no sequence of admissible generated potentials or limits violating the claimed compactness; no general family of fully admissible noncompactness counterexamples has been ruled out.
- Obstruction: A failed certificate or stationarity inequality at an arbitrary lawful law does not give a counterexample without certifying that the law and level form a genuine deterministic canonical global maximizer over the entire lawful class. No such optimizer was certified in this round. This is a search admissibility obstruction, not a proof step toward the target.
- Obstruction: Arbitrary lawful populations, including mixed-tag two-particle populations with opposite loadings and signed rank weights, cannot refute an assertion made only at genuine deterministic canonical global maximizers unless global optimality over the entire lawful comparison class is certified. The round report supplies no such certification. This excludes an unsupported counterexample argument, not a family of fully admissible counterexamples.
- Obstruction: Unit-loading boundary constructions do not produce a singular private kernel merely by setting the residual loading variance to zero: the displayed formula gives $c_s(v)^2=s^2>0$ at $\|v\|=1$. This rules out that particular singular-kernel mechanism, without providing uniform reciprocal-density control.
- Obstruction: A sign whose defining weight vanishes almost everywhere has every defined selector potential and level coordinate equal to zero. Conditional on selector nonemptiness, the corresponding hull is the zero singleton; disappearance of that sign alone is therefore not a compactness failure.
- Obstruction: Noncompactness of the strong Hilbert parameter ball by itself is not a counterexample to compactness of the generated averaged functions in the declared evaluation topology. No sequence of admissible potentials or their limits demonstrating failure was supplied.
- Obstruction: No additional family-level obstruction follows from the third-round report's endpoint, rank-one, or small-positive-mean tag checks: it reports no sign contradiction but supplies no candidate object or calculation body. The round contains no candidates, so it establishes no exclusion of fully admissible counterexamples beyond the restricted mechanisms just described.
- Obstruction: An arbitrary lawful population, including a finite mixed-tag or zero-mean-label example, cannot refute a conclusion restricted to genuine deterministic canonical global maximizers without certification of global optimality over the entire lawful comparison class. Round 4 provides no such certified object. This blocks an unsupported counterexample argument, rather than ruling out a family of fully admissible counterexamples.
- Obstruction: Unit-loading boundary examples do not yield a singular private kernel merely by eliminating residual loading variance: the stated variance remains $c_s(v)^2=s^2>0$ when $\|v\|=1$. This excludes that particular singular-kernel mechanism, without controlling reciprocal mixture density uniformly.
- Obstruction: If a defining signed weight vanishes almost everywhere in the relevant expectations, every defined generator for that sign has zero particle potential and zero level coordinate. Conditional on nonemptiness of the hybrid selector family, the corresponding hull is the zero singleton. Vanishing of one sign alone therefore does not supply a compactness counterexample.
- Obstruction: Noncompactness of the infinite-dimensional strong Hilbert parameter ball alone does not imply noncompactness of the generated averaged potential functions in their declared evaluation topology. A failure requires an admissible potential sequence or another failure of a stated property; none is supplied in this round.
- Obstruction: A proposed all-false boundary maximizer fails H4 whenever a lawful zero-mean all-true population strictly improves the normalized regularized objective at the same level. The round's sole candidate has exactly this strict improvement, so its H4 is **fail**, not unknown. H1--H3 pass; NOT remains unknown because the checks stop at H4. This rules out the proposed maximizing object, without testing the certificate conclusion at a genuine global maximizer.
- Obstruction: More generally, stationarity or potential failure at a lawful population cannot refute a statement restricted to genuine deterministic canonical global maximizers unless global optimality over the entire lawful comparison class is certified. The reported single-particle and parameter-edge checks provide no additional qualifying object or family-level exclusion in this pack.

## Limitations

- The pack supplies one failed candidate and its first-failure line, not its calculation body. The summary records the stated strict competing-law improvement without inventing objective values or extending that comparison to every all-false law.
- No explicit genuine deterministic canonical global maximizer was certified. The matching potential, matching level coordinate, and coherent mean-flux conclusions therefore remain untested at an object satisfying every hypothesis; the failed candidate is not a counterexample to the lemma.
- General compactness remains unproved: hybrid selector nonemptiness and measurability, conditional-realization-uniform bounds, derivative bounds and equicontinuity, preservation of analytic extensions under convex limits, and continuity of the required integral pairings still require proof. Noncompactness of the strong parameter ball alone does not settle compactness of the potential classes.
- Exact all-active support formulas, nested-hull limits, Gaussian interchanges, centered product-space separation, and a matching mass-and-level pair coherent with lawful mean variations remain unproved. The total-flux identity and finite false-particle comparison also remain obligations.
- The H4 failure is a search-admissibility obstruction, not an established proof step toward the target, so it does not warrant an approach idea. The reported absence of other contradictions supplies no proof of the certificate or its draft prerequisites. Zero-true-mean flux control, removal of regularizers, and both unrestricted Gaussian BH bounds remain separate unresolved obligations.

Object search: 1 candidate(s) in 5 round(s).
