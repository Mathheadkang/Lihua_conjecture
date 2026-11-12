---
type: search_round
title: Few correlated alternatives and final-conditioning sign reversal
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
performed_by: unknown
created_at: '2026-11-11T22:56:02.083Z'
extension_version: 0.0.4
---

## Obstructions

- For an original null block with nonpositive off-diagonal covariance, the unconditional Gaussian null-count mgf holds with rate $Ns$, regardless of its dependence on the alternatives. With $a=|I_0^c|$, grouping original outcomes by actual false and alternative rejection counts gives the draft bound $\operatorname{FDR}\le\min\{1,2e(a+2)q\}$ in [Bounded correlated alternative counts preserve O(q) FDR under nonpositive null covariance](../ideas/idea_fe556cf8f196.md). An independent derivation is preserved in [Few unsaturated alternatives cannot amplify nonpositive-covariance Gaussian nulls beyond O(q times alternative count)](../ideas/idea_b98309d2c00e.md). Both observations retain arbitrary correlations and unsaturated alternatives; neither assumes that revealing alternatives preserves the null covariance signs. Both saved records remain unchanged.
- The independent geometric argument yields the sharper consequence $\operatorname{FDR}\le\min\{1,2e(a+1)q\}$. For $1\le v\le|I_0|$, the original event $\{V=v\}$ implies $C(q(v+a)/N)\ge v$, since $R\le V+a$. The threshold is in $(0,q]$ because $v+a\le N$. Put $b=eq(a+1)$. When $b<1/2$, Chernoff gives $\mathbb P(V=v)\le b^v$, hence $\operatorname{FDR}\le\mathbb P(V>0)\le b/(1-b)\le2b$. When $b\ge1/2$, the trivial cap is at most $2b$. Thus bounded alternative counts cannot refute the main order assertion even with arbitrary unsaturated correlated alternative gates. Within this nonpositive-null-covariance subclass, a diverging normalized ratio requires $(a+1)/\sqrt{\log(1/q)}$ to be unbounded.
- Final conditioning is a real limitation of the conditional tool, not a main counterexample. The precise saved diagnostic [A correlated alternative flips independent null residuals positive and defeats marginal-only sub-Poisson calibration](../ideas/idea_1256293060f9.md) uses independent $X,Y\sim N(0,1)$ and $(T_1,T_2,T_3)=(X,Y,1+(X-Y)/\sqrt2)$. The original null covariance is zero, but conditioning on the complete alternative leaves null residual covariance $\frac12\left(\begin{smallmatrix}1&1\\1&1\end{smallmatrix}\right)$ with positive off-diagonal entry. At $q=\overline\Phi(20)$ the prescribed conditional marginal calibration factor is $K=1$ near $T_3=1$, yet the count mgf fails at $e^\lambda=2/(3q)$ on a positive-probability interval of conditioning values. This rules out replacing the final conditional count assumption by marginal calibration alone. It does not refute the approved helper, whose sign requirement is imposed after final conditioning, or the main theorem: the same three-test model has $\operatorname{FDR}\le11q/9$ by the marginal harmonic bound.

## Limitations

- Main-target round 3 after helper approval produced no candidate files and no surviving counterexample. The two independent few-alternative observations and the sign-flip diagnostic are preserved as draft ideas; no duplicate idea was created.
- The few-alternative estimates grow with $a$ and do not control arbitrary $q$-dependent alternative counts. The general positive-null-covariance geometry remains unproved, including mixed unsaturated alternatives correlated with that null geometry.
- A failed auxiliary count inequality is not an unbounded-normalized-FDR construction. No such admissible family was found, and no dimension-uniform proof of the unrestricted main assertion is supplied here.
- The summary uses the current pack and an expressly allowed native show of idea_1256293060f9 to state its exact diagnostic. It does not inspect the target proof or mutate any target, prior round, or saved observation. The new subclass deductions still need independent native verification before being treated as approved results.
