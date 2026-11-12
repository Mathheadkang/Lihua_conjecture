---
type: search_round
title: 'Round 4: correlated alternative splitting retains the compensated coefficient'
target_asset: gaussian_bh_growing_clone_compensated_variation
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_growing_clone_compensated_variation_r4_s2_correlated_alternative_pair
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T23:11:26.852Z'
extension_version: 0.0.4
---

## Obstructions

- Dependence between the privately cloned alternative and the exact null does not by itself create a discrepancy. The sole new candidate has fixed $N=2$, $q=1/4$, $\theta=(1,0)$, $i=1$, and correlation $1/2$; all nine hypothesis checks pass but NOT fails. Its signed face masses are $\mu_{1,1}(\mathbb R)=0$ and $\mu_{1,2}(\mathbb R)=0.007070014537774618$, giving the nonzero compensated coefficient $\log\{2h(u_2)\}\mu_{1,2}(\mathbb R)=0.006596569578441303$. This rules out the proposed discrepancy only for this fixed dependent pair, beyond the earlier zero-coefficient independent benchmarks.
- Dropping partial alternative rejection or replacing the common crossing by separate block crossings would lose the calculation's relevant cancellation. In this pair, let $u(x)=S^{-1}(qx/2)$ and $x_s(m)$ be the largest root of $1+b_\varepsilon(x,z)\ge x$ on $[1,2]$, with $m=1+d_\varepsilon+\sqrt{1-s^2}z$. The retained population FDR is exactly $\mathbb E_Z[P\{T_2\ge u(x_s(m))\mid Z\}/x_s(m)]$, where $T_2\mid Z=z\sim\mathcal N(z/2,3/4)$. Thus the fractional FDP $1/x_s(m)$ is retained, even though the chosen block is an alternative. The integrated upper-branch fractional deficit is $O(s^2/t_s^2)$ and the lower-branch correction is exponentially small in this model; both are below $s/t_s$. The resulting saddle displacement reproduces the signed original-rank face coefficient.
- A strict positive mass surplus at a population largest crossing cannot furnish the proposed endpoint counterexample. The chosen Gaussian survival mass is continuous in rank, and the exact blocks have only upward jumps at their non-strict thresholds. At a positive largest crossing, $H(\rho)>\rho$ would extend admissibility immediately to its right; at the maximal rank total mass cannot exceed that rank. Hence this deterministic argument gives $H(\rho)=\rho$ whenever $\rho>0$. It does not prove finite-copy convergence or the compensated expansion. The separation of these obligations and the local integrated-deficit estimate are recorded as the draft approach [Separate deterministic crossing equality from empirical clone convergence](../ideas/idea_30958c18ad42.md).

## Limitations

- Round 4 produced exactly one new failed candidate and no survivor. The other two slots supplied no new admissible object or candidate file; the deterministic crossing observation is not an additional tested family. Earlier-round board entries are prior coverage, not additional round-4 candidates.
- The correlated pair's reduction checks its finite-copy limit and expansion locally. It does not establish general convergence of empirical largest crossings to the common population functional, including population endpoints, tangencies, births and switches, or empirical ranks tending to zero. The deterministic equality alone supplies none of those convergence estimates.
- General multirank saddle clipping, rank-face intersections and overlapping boundary layers still require target-scale estimates before signed face contributions can be summed. Dependent null blocks, fractional chosen-null numerators, and actual cascades are not covered here beyond the separately checked earlier local models. The chosen alternative in this round does not test a fractional chosen-null numerator.
- All original means and covariance parameters remain fixed. No uniform estimate across models, estimate uniform in copy count, exchange of the prescribed limits, general compensated expansion, singular-model extension, or unrestricted FDR bound follows. The target remains draft and unresolved.
