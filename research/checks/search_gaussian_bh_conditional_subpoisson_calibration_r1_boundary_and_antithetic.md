---
type: search_round
title: Boundary and antithetic obstructions for conditional sub-Poisson calibration
target_asset: gaussian_bh_conditional_subpoisson_calibration
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_conditional_subpoisson_calibration_r1_s3_singular_antithetic_pair
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
performed_by: unknown
created_at: '2026-11-11T22:23:50.122Z'
extension_version: 0.0.4
---

## Obstructions

- The capped regimes cannot refute the statement: if $K=\infty$ or $4eqK\ge1$, the claimed conditional bound is $1$, whereas $\operatorname{FDP}\le1$ pathwise. An empty original null set also gives $\operatorname{FDP}=0$.
- Finite conditional calibration excludes null mass at zero. Differentiating the count moment-generating-function inequality at $\lambda=0$ gives $\mathbb E[C(s)\mid\mathcal H]\le NKs$. Sending deterministic $s\downarrow0$ on the stipulated common full-measure set gives $\sum_{i\in I_0}\mathbb P(P_i=0\mid\mathcal H)=0$ wherever $K<\infty$. Thus zero-null-p-value boundary constructions fail the count hypothesis.
- Conditionally deterministic null counts cannot refute the bound, including Gaussian null vectors whose conditional variances all vanish. The same first-moment inequality becomes $C(s)\le NKs$; at each possible positive actual BH rank $r$, $V=C(qr/N)\le qKr$. Consequently $\operatorname{FDP}\le qK$ pathwise. For $N=1$, conditional expectation at the single threshold $q$ gives the same stronger conditional FDR bound without determinism.
- The aggregate first-moment implication already rules out every sample size satisfying $H_N=\sum_{r=1}^N1/r\le4e$. Indeed, putting $a_r=qr/N$, the largest-rank BH rule gives
  $$
  \operatorname{FDP}
  \le \frac{C(q)}N+
  \sum_{r=1}^{N-1}C(a_r)\left(\frac1r-\frac1{r+1}\right).
  $$
  This follows by bounding each rejected null's contribution $1/R$ by the reciprocal of the smallest grid rank at which its p-value qualifies. Conditional expectation and $\mathbb E[C(a_r)\mid\mathcal H]\le qKr$ then yield $\mathbb E[\operatorname{FDP}\mid\mathcal H]\le qKH_N$. This is an obstruction for those sizes, not a bound uniform in $N$.
- The recorded singular antithetic Gaussian pair passes all hypotheses but fails the counterexample conclusion: its actual FDR is $q$, below the claimed capped bound $\min\{1,4eq\}$. Thus perfect negative dependence in that two-coordinate family is not itself an obstruction to the lemma. This conclusion concerns the recorded family and does not claim that every singular Gaussian configuration has FDR $q$.

## Limitations

- Round 1 produced one failed candidate and no surviving counterexample. These obstructions do not establish the dimension-uniform $4e$ constant when $H_N>4e$.
- No concrete large-$N$ construction was checked that couples null exceedance counts across BH thresholds while retaining every deterministic-threshold conditional sub-Poisson bound and making the actual rejection rank adverse.
- Beyond the recorded antithetic pair and the deterministic boundary, this round did not establish the Gaussian sufficient condition for arbitrary singular PSD covariance matrices with nonpositive off-diagonal entries under the full final conditioning.
- The summary uses the current pack's candidate outcome and earlier round report; it does not independently re-verify the omitted candidate body or the target proof.
