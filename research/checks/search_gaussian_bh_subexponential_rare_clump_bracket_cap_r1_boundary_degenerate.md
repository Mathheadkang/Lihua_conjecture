---
type: search_round
title: >-
  Refute search round 1 for the compound-Poisson rare-clump bracket cap
  (boundary and degenerate cases)
target_asset: gaussian_bh_subexponential_rare_clump_bracket_cap
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_subexponential_rare_clump_bracket_cap_r1_s1_global_null_singleton_simplex
  - >-
    cand_gaussian_bh_subexponential_rare_clump_bracket_cap_r1_s1_identical_clumps_weak_fog
statement_digest: d66c527595f7967458383519a22868df0977fdbc6933b1f63f69cb380debf465
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:53:04.402Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

# Refute search round 1, slot 1: boundary and degenerate cases

## Obstructions

- Every singleton clump system fails NOT unless the full FDR fails: with $K_l=\{i\}$ one has $R_{i,0}=R_{i,*}$, $D_i=1$, and $\Psi_i=\mathbf 1\{i\in\mathcal R\}/R$, so $\sum_S\Psi_i=|\mathcal R\cap S|/(R\vee1)$. Global-null singleton families (simplex frame, sign cube, negative equicorrelated blocks) reduce to the size of the Gaussian Simes test under neighbourhood sparsity. So the cap does contain the sparse global-null Gaussian Simes problem, like the rare-direction cap (idea_13a0fb394818). That problem is the global-null case of the main order bound, so it cannot be refuted here without refuting the main conjecture. The simplex frame gives size $q(1+o(1))$.
- For clumps of $k$ identical nulls whose direction is orthogonal to everything else, the charge is exactly $\frac{qk}{m}(1+\mathbb E\log(R_*^l/\max(R_0^l,k)))$. A counterexample therefore needs the other coordinates to be near-critical, at relative precision $1/X$ over a multiplicative window of length $X=e^{\omega(u)}$ with probability bounded below. Two routes do not achieve this. (a) A single common factor (one shared direction carrying an exact staircase) reaches precision $1/X$ only on a factor window of width about $1/(Xu)$, so $\sum_X P\cdot\log X=O(1)$. (b) Independent alternatives at the BH scale $t\approx q$ fail because the mean profile $\sum_a\overline\Phi(y-\theta_a)$ cannot match $(m/q)t$ there: the hazard monotonicity forces $\theta_a\approx0$, and then about $m/q$ coordinates would be needed.
- That mean-profile obstruction disappears in the deep tail $t^*=qM/m\ll q$. The window $[t^*/X,t^*]$ has length $\log X/y^*$ in the $y$ scale, and a fog of $\Theta(m)$ weak alternatives with $\vartheta\approx2\log(2/q)/y^*$ has intensity boosted by about $1/q$ there, with log-variation $\vartheta\log X/y^*\to0$. This gives the surviving candidate cand_gaussian_bh_subexponential_rare_clump_bracket_cap_r1_s1_identical_clumps_weak_fog. Its charge is at least $\frac q4(1+0.74\log X)$, of order $q u^2$ for $X=\lfloor1/(4q)\rfloor$, against the claimed $A_3q(1+u)$. A proof of the cap would have to exclude exactly this, and the statement places no restriction on alternatives that could.

## Limitations

- Sign-cube frames, Dobriban-type and Lei-type lower families restricted to rare clumps, and replicated one-null staircases were reasoned about only through the singleton reduction and the near-criticality criterion, not computed individually. The single-common-factor staircase was estimated heuristically, not written as a candidate.
- The survivor's interference bound uses Daniels' identity for the uniform empirical process, and its fog fluctuations use Bernstein's inequality, both quoted rather than taken from the library. The numerical check is a Poisson approximation at small $X$ ($q=0.01$, $X=20$), not the asymptotic regime. The required $m$ is astronomically large ($y_M^2\ge8X\log X\log(2/q)$).
- Positive-radius clumps (spread within $\kappa/u$) and negative null means in $(-a_q,0)$ were not needed and were not explored. The survivor uses radius $0$ and $\theta=0$.
