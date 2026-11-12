---
type: search_round
title: 'Round 5: population zero-rank exclusion and remaining empirical tail gap'
target_asset: gaussian_bh_growing_clone_compensated_variation
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T23:16:37.454Z'
extension_version: 0.0.4
---

## Obstructions

- At fixed positive private noise and fixed common Gaussian vector $G$, the chosen conditional Gaussian has finite mean $m$ and variance $s^2<1$. Writing its small-rank mass as $b(r)=S((u(r)-m)/s)$ with $u(r)=S^{-1}(c r)$ for the positive rank-normalization constant $c$, Gaussian tail asymptotics give $\log\{b(r)/r\}=-(s^{-2}-1)u(r)^2/2+O(u(r)+\log u(r))$. Thus $b(r)/r\to0$ as $r\downarrow0$. Each exact block has a fixed positive conditional p-value and contributes no mass at sufficiently small rank. Hence positive population crossings cannot accumulate at zero for that fixed $G$ and noise. This excludes the proposed population zero-rank accumulation mechanism; it does not establish convergence of empirical endpoints or provide a new tested family.
- The proof-step obstruction is the distinction between that population gap and empirical microscopic crossings. A finite-copy tail estimate and a valid global comparison of actual largest crossings must still be supplied. The possible approach of isolating the population gap before controlling the empirical lower tail is recorded as [Separate fixed-noise population zero-rank exclusion from empirical clone tails](../ideas/idea_14070b1eb71a.md).

## Limitations

- All three round-5 slots produced no new candidate file; there is no survivor or newly checked failure of NOT. Prior board examples retain their earlier coverage and are not counted again as new families.
- Slot 2 considered the fixed three-test background $N=3$, $\theta=(-1,0,0)$, with the chosen negative-null coordinate independent of the other two exact null coordinates, whose correlation is $1/2$. This reached only a numerical multirank diagnostic. Neither a violation nor a matched-limit proof was established; numerical diagnostics supply no additional verified coverage.
- The fixed-$G$ statement $b(r)/r\to0$ is a population tail fact at each fixed positive noise. It supplies no finite-copy estimate for empirical ranks tending to zero, no convergence of empirical largest crossings, and no justification for exchanging limits.
- General finite-copy tail control and global largest-crossing comparison remain unproved, including endpoint behavior, tangencies, births, switches, and multirank cascades. General signed rank-face summation, overlapping boundary layers, fractional chosen-null numerators, and remainders at scale $s/t_s$ also remain proof obligations.
- The original model parameters stay fixed. This round establishes neither the general common-crossing representation nor the compensated expansion, a uniform-in-model or uniform-in-copy-count estimate, a singular-model extension, or an unrestricted FDR bound. The target remains draft and unresolved.
