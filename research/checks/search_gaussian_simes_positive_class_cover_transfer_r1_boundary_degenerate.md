---
type: search_round
title: >-
  Refute search round 1 for the positive-class cover transfer: boundary and
  degenerate cases
target_asset: gaussian_simes_positive_class_cover_transfer
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - cand_gaussian_simes_positive_class_cover_transfer_r1_s1_antipodal_pair
  - cand_gaussian_simes_positive_class_cover_transfer_r1_s1_comonotone_ties
  - cand_gaussian_simes_positive_class_cover_transfer_r1_s1_singleton_equality
statement_digest: 6f5e1db93cf32b89012029bd947a756bef6f729d9d2aea6b980ed9894daae7fb
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:26:12.201Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Every candidate fails NOT for a structural reason: if a positive class $S$ is hit, then $k=|\mathcal A\cap S|\ge1$ elements of $S$ have $p\le qr/N\le (q/c)\,k/|S|$ (using $c|S|r/N\le k$), so the Simes statistic of $p_S$ is at most $q/c<1$. The Simes inequality for nonnegatively correlated Gaussian vectors (lib_chi2024_positive_gaussian_simes, singular allowed, ties harmless since it is an order-statistic event) gives $P(S\text{ hit})\le q/c$, and Markov on $h=\sum_S\pi(S)\mathbf 1\{S\text{ hit}\}$ gives the bound. No degenerate choice of $\Sigma$ (singular, antipodal, comonotone), $\pi$, or tie pattern escapes this.
- Mixed-sign degenerate $\Sigma$ (antipodal pairs) can push $\mathbb P(E_q)$ well above $q$, but a singleton class is hit with probability at most $P(p_i\le q)=q$, since BH thresholds never exceed $q$; the positive-class restriction removes the bad pair $\{1,2\}$.
- The boundary $c=c_*=1$ is sharp: $N=1$, or $\Sigma=J$ with any $\pi$, attains equality $q$. For $cc_*\le q$ the bound is vacuous, so no counterexample can live there.

## Limitations

- Only the boundary_degenerate direction was covered (single worker). Large-$N$ random or block-structured $\Sigma$ with many overlapping positive classes, and $\pi$ concentrated on mid-size classes with $c$ small, were not searched; the Simes-plus-Markov obstruction above suggests they fail too, but it relies on the library theorem applying to every positive class including those with singular sub-covariance.
