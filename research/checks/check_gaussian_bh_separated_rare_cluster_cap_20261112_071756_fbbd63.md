---
type: falsification_check
title: 'Falsification check: gaussian_bh_separated_rare_cluster_cap'
target_asset: gaussian_bh_separated_rare_cluster_cap
outcome: no_counterexample_found
statement_digest: 41a2d96d4641af88c2627a7dc0e53cf74e3004654a2cb9353183aff244b71a7d
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T07:17:56.660Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_separated_rare_cluster_cap_r1_s1_global_null_simplex_singletons failed — NOT fails: the simplex global null is dominated (on the half-space $\bar X\ge0$, independent of $T$) by an independent model with variance $m/(m-1)$, whose Simes size is $O(q)$; extreme exchangeable negative correlation inflates Simes by at most a constant.
- Round 1, boundary_degenerate: cand_gaussian_bh_separated_rare_cluster_cap_r1_s1_identical_clumps_weak_fog_as_clusters failed — NOT fails: the clump-bracket charge carried a spurious $\log(R_*/\max(R_0,k))$ term, but the actual BH null share of a clump of identical, mutually independent null blocks is exactly $qk/m$, so the whole null FDR is $q/4\le A_2q(1+u)$.
- Obstruction: The left side of the cap is at most the full null FDR $\mathbb E[V/(R\vee1)]$, so every counterexample to the cap is a model with FDR $>A_2q(1+u)$, i.e. a counterexample to [the one-sided universal order bound](../assets/gaussian_bh_one_sided_universal_order_upper.md) (whose $Cq\sqrt{\log(1/q)}$ is $O(q(1+u))$). Any family with FDR $O(q)$ fails NOT, whatever its clusters.
- Obstruction: Conversely the separation hypothesis is vacuous at the degenerate end: centres need not be loadings. Embedding the loadings in $\mathbb R^{d+m}$ (same law of $T$) and putting $v_i=\cos\phi\,w_i+\sin\phi\,f_i$ with fresh orthonormal $f_i$ and $2-2\cos\phi=(\kappa_2/u)^2$ gives $\|w_i-v_i\|=\kappa_2/u$ and $\|v_i-v_j\|^2=2-2\cos^2\phi\,w_i^{\mathsf T}w_j>(\kappa_2/u)^2$, even for identical loadings (when $\kappa_2/u<\sqrt2$). So every null can be a singleton cluster, and for $m>q^{-C_2}$ the cap is equivalent to FDR $\le A_2q(1+u)$ over all unit-loading (hence all unit-diagonal PSD) Gaussian models. In particular it contains the global-null Gaussian Simes problem under arbitrary correlation, as for the rare-direction cap.
- Obstruction: Identical-direction clumps that are mutually independent (the refuted clump-bracket construction, with any weak-alternative fog): the BH null share of a clump of $k$ tied nulls is exactly $qk/m$ (the clump is rejected iff its common uniform p-value is $\le qR_*/m$, with $R_*$ the BH count with the clump at $0$, independent of it, and then $R=R_*$). The whole null FDR is $q\cdot(\#\text{nulls})/m\le q$, so the $\log X$ excess of that counterexample lives only in the bracket charge, not in BH. More generally, all nonnegative correlations give PRDS and FDR $\le qm_0/m$ (Benjamini-Yekutieli), so a violation needs negative correlations.
- Obstruction: Global null with the most negative exchangeable correlation (regular simplex, $\Sigma_{ij}=-1/(m-1)$): coupling $T_i=c(X_i-\bar X)$ with $\bar X$ independent of $T$ dominates the Simes event on $\{\bar X\ge0\}$ by an independent model of variance $m/(m-1)$, giving size $\le2e^5q$ once $m\ge\max(10,\log(1/q))$. Exchangeable negative dependence inflates Simes by at most a constant.

## Limitations

- No model with FDR above $Cq(1+u)$ is known; by the first two obstructions, any refutation of this cap for $m>q^{-C_2}$ is a refutation of the project's main one-sided target, which this round did not attempt beyond the two families above.
- Not covered: non-exchangeable negative dependence (sparse crossings among spread, weakly signed directions, where [the dense-crossing tilt bound](../ideas/idea_a2ee64f07126.md) stops), global nulls mixed with alternatives under negative null correlations (the Simes coupling does not apply since $V/R$ is not monotone), small $m\le q^{-C_2}$, and $q$ near $q_2$ with $\kappa_2/u\ge\sqrt2$, where the off-loading singleton centres are unavailable.

Object search: 2 candidate(s) in 1 round(s).
