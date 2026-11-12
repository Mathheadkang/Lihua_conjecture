---
type: search_round
title: >-
  Negative-null covariance and saturated-alternative obstructions after
  sub-Poisson calibration
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates: []
statement_digest: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
performed_by: unknown
created_at: '2026-11-11T22:51:59.356Z'
extension_version: 0.0.4
---

## Obstructions

- Suppose the original null covariance block has $\Sigma_{ij}\le0$ for distinct $i,j\in I_0$, and the entire alternative block is independent of the null vector. Conditioning on all alternative p-values leaves the Gaussian null mean vector and covariance block unchanged. Because every original null mean is nonpositive and every original marginal variance is one, $F_{i,\mathcal H}(s)\le s$ and the approved conditional sub-Poisson helper has $K=1$. Thus the original ordinary BH procedure satisfies $\operatorname{FDR}\le\min\{1,4eq\}$, uniformly in all dimensions, null counts, negative null means, singularities, and parameters within this subclass. Its normalized ratio is at most $4e/\sqrt{\log(1/q)}$, so this subclass cannot refute the main order assertion. The application is already saved as draft idea_52b05be9e378; no duplicate idea is created.
- A saturation comparison removes the independence requirement at an explicit probability cost, while retaining nonpositive covariance within the original null block. Write $a=|I_0^c|$. For $a\ge1$ define the sufficient good event $A=\{\max_{j\notin I_0}P_j\le qa/N\}$ and the exact bad-event cost $\delta=\mathbb P(A^c)$. Keep the original null p-values and labels in an auxiliary vector whose alternative p-values are all zero. Its BH rank $R_0$ is at least $a$. Coordinatewise monotonicity of the BH rank gives $R\le R_0$; on $A$, all original alternatives are already below $qa/N\le qR_0/N$, so rank $R_0$ also qualifies in the original procedure, yielding $R=R_0$. The null rejection set and FDP therefore agree on $A$. Since FDP is at most one off $A$, $\operatorname{FDR}_{\rm original}\le\operatorname{FDR}_{\rm auxiliary}+\delta\le4eq+\delta$; the separate bound FDR at most one gives $\operatorname{FDR}_{\rm original}\le\min\{1,4eq+\delta\}$. The auxiliary bound follows from the approved helper with deterministic alternative zeros and $K=1$. This comparison uses no independence between alternatives and nulls and asserts no global monotonicity of FDR under replacing alternatives by zeros.
- The saturation error is the exact union probability $\delta=\mathbb P\{\exists j\notin I_0:T_j<\overline\Phi^{-1}(qa/N)\}$, with the finite-model union bound $\delta\le\sum_{j\notin I_0}\Phi(\overline\Phi^{-1}(qa/N)-\theta_j)$. Here $\Phi$ is the standard normal CDF; the unit-variance Gaussian marginals have no atoms at the threshold, even if the joint law is singular. Thus $\delta=O(q)$ gives an $O(q)$ subclass bound; more generally $\delta=O(q\sqrt{\log(1/q)})$ prevents an unbounded normalized ratio. When $a=0$, no saturation event is needed and the all-null nonpositive-covariance case already has the $4eq$ bound. This application is already saved as draft idea_7a957628fee8; no duplicate idea is created.

## Limitations

- Main-target round 2 after helper approval produced no candidate files and no surviving counterexample. All old rounds, candidates, and checks remain preserved.
- The two saved applications are draft observations derived from an approved helper; this search summary is not a separate native proof-verification verdict or approval for either application or the unrestricted main theorem.
- Mixed unsaturated alternatives correlated with the null vector remain unaddressed. Revealing those alternatives may change the conditional null means, Gaussian covariance signs, and calibration factor. The independent-block argument cannot simply be carried over.
- Arbitrary positive off-diagonal covariances within the original null block also remain outside the two displayed subclass arguments. They may be allowed by the main statement and cannot be discarded or replaced.
- Large positive alternative means do not by themselves guarantee a uniform small saturation error when the number of alternatives grows with $q$. The exact $\delta$ or a valid upper bound must be controlled at the required scale for the entire proposed family.
- The unrestricted $q$-dependent high-complexity Gaussian supremum and its same-actual-rank allocation remain unresolved. The current pack supplies the saved idea IDs and round report but not their bodies; the rank comparison and error bound are reconstructed explicitly here without inspecting those bodies or the omitted target proof.
