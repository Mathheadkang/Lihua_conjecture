---
type: search_round
title: >-
  Conditional compound calibration round 3 - cap crossing and interacting mixed
  kernels
target_asset: gaussian_bh_conditional_compound_calibration
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_conditional_compound_calibration_r3_s1_random_cap_two_nulls
  - >-
    cand_gaussian_bh_conditional_compound_calibration_r3_s2_six_null_mixed_kernel
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T16:12:28.588Z'
extension_version: 0.0.4
---

## Obstructions

- The recorded cap-crossing family cannot refute the target by combining two active nulls with a random nonnull or by crossing the cap at one. At $N=3$, $q=1/10$, each original null is $1/30$ with probability $a(z)/2$ and otherwise one, the original nonnull is independently zero or one with equal probabilities, and $a(z)=1/5+3z/5$. Conditional independence holds. If $S$ is the number of small nulls and $B$ indicates the nonnull zero, the actual largest qualifying BH rank is $R=S+B$ and $V=S$. The resulting conditional FDR $3a(z)/4-a(z)^2/6$ is below $\min\{1,2a(z)\}$ throughout $a(z)\in[1/5,4/5]$, including the transition $a=1/2$, where it is $1/3<1$. The zero atom belongs to a nonnull and does not make the null envelope infinite; here $M_q=K_q=10a(z)$ is finite everywhere. This obstruction is restricted to the displayed family.
- Mixing conditional states that each obey the target comparison cannot create an unconditional violation against the expectation of those same statewise bounds. In particular, the six-null two-state candidate has valid conditional product laws and respects its two finite nonsaturated bounds separately. Marginal dependence introduced by mixing is allowed; replacing the statewise envelope by a marginal envelope would test a different claim. This observation does not establish the missing statewise inequality for arbitrary kernels.

## Limitations

- Exactly two new candidates were recorded in round 3, both passing their listed hypotheses and failing NOT. The board now contains thirteen failed candidates over three rounds and no survivor. These failures are search evidence, not a proof of the conditional calibration lemma or its universal constant $2$.
- The $N=7$ mixed-kernel candidate has six original nulls with heterogeneous off-threshold supports and a random original nonnull. Its exact certificate enumerates $3^7=2187$ support vectors in each of two conditional states, retaining the actual largest qualifying BH rank, non-strict comparisons, and original null labels. It gives conditional FDRs $21345811/146800640<4/7$ and $3394163/44040192<36/55$; the respective finite nonsaturated envelope bounds use $qM_q=2/7$ and $18/55$ at $q=1/100$. This certificate establishes only the failure of that specified candidate. It does not exclude arbitrary interacting six-null laws or prove a general dimension-seven bound.
- The cap-crossing candidate integrates to FDR $197/600$, below expected bound $17/20$. Its full conditioning range is covered by the explicit formula above, but it has only two active nulls with a common small atom and a Bernoulli nonnull. General interacting continuous laws or arbitrary random nonnull distributions are not covered by that calculation.
- The third search slot supplied a restricted $N=2$ atom calculation and found no genuinely new candidate. That calculation is not a third candidate, a survivor, an exhaustive test of every two-coordinate law, or a general theorem. No additional proof is asserted from it here.
- Arbitrary dimensions, general heterogeneous conditional product kernels, and the full finite nonsaturated-envelope regime remain unexhausted. Earlier endpoint inclusion, nonattained supremum, zero-null-atom, conditional-independence, and original-label conventions remain necessary. A common conditioning variable may induce marginal dependence without violating conditional independence; constructions that actually abandon conditional independence are outside the target.
- No proof plan, proposed stop-loss argument, or exact-arithmetic gate was read or verified in this summary stage. The search results do not certify that proposed mechanism, Gaussian order estimates, noise-floor removal, or either unrestricted main theorem. General validity still requires a complete proof and its independent verification.
