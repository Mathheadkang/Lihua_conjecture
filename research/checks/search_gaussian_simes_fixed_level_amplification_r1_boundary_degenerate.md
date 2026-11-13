---
type: search_round
title: >-
  Refute search round 1 (boundary and degenerate cases) for the fixed-level
  Gaussian Simes amplification
target_asset: gaussian_simes_fixed_level_amplification
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_fixed_level_amplification_r1_s1_boundary_delta_endpoint_t
  - cand_gaussian_simes_fixed_level_amplification_r1_s1_large_delta_fog
statement_digest: b6a407fa54e9d1cd926525fbc5f6a3e04eae9e8c1c54cb093f1fed66465a084f
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:06:58.701Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Every choice with $\delta>1-\alpha_0$ fails the hypothesis $B(\alpha_0)\le1-\delta$: the single-test model $N=1$, $\Sigma=(1)$ has uniform $p_1$, so $B(\alpha)\ge\alpha$ for every $\alpha\in(0,1)$. Admissible parameters therefore satisfy $\delta\le1-\alpha_0$, so $\log(1/\delta)\ge\log(1/(1-\alpha_0))\ge\alpha_0$ and the constant $2\log(1/\delta)/\alpha_0$ is at least $2$.
- So no degenerate witness with $\mathbb P(E_t)\le2t$ can violate the conclusion. This covers $N=1$, the all-ones (singular) $\Sigma$, where all $p_i$ coincide and $\mathbb P(E_t)=t$, and the antithetic pair $\rho=-1$ with $t<1/2$, where $\mathbb P(E_t)=t$.
- No witness $\Sigma\in\mathcal C_N$ at all (singular included) can violate the conclusion while the hypothesis holds. Put $m=\lfloor\alpha_0/t\rfloor\ge\alpha_0/(2t)$ for $t\le\alpha_0/2$. The block-diagonal matrix of $m$ independent copies of $\Sigma$ lies in $\mathcal C_{mN}$. A Simes rejection at level $t$ in any one block gives a pooled rejection at level $mt\le\alpha_0$, because $p_{(k)}\le p^j_{(k)}\le tk/N\le\alpha_0k/(mN)$. Hence $1-\delta\ge1-(1-q)^m$, and so $q\le1-\delta^{1/m}\le\log(1/\delta)/m\le2\log(1/\delta)t/\alpha_0$. This holds even at the boundary $\delta=1-\alpha_0$, $t=\alpha_0/2$.

## Limitations

- The hypothesis $B(\alpha_0)\le1-\delta$ was never verified for any concrete $(\alpha_0,\delta)$, because no upper bound on the all-null Gaussian Simes rejection probability over all correlations is available. Candidates that do not violate it outright have H3 marked unknown.
- The block-diagonal argument above suggests the statement is true. A counterexample would have to break that argument (for example, through a convention about order statistics or non-strict comparisons). This round did not check the target's own proof.
- Directions other than boundary and degenerate cases (structured negative correlations, large-$N$ families) were not explored this round.
