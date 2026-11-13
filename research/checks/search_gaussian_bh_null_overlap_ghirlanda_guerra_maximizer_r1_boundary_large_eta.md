---
type: search_round
title: 'Refute search round 1 (boundary and degenerate): the large-penalty regime'
target_asset: gaussian_bh_null_overlap_ghirlanda_guerra_maximizer
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_null_overlap_ghirlanda_guerra_maximizer_r1_s1_large_eta_antipodal_nulls
statement_digest: c004cd7dd3ebba2bde77adaf595610273c90f3f1141552d69887bd909631a7ab
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T08:17:01.419Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Any regime where $A_{\eta,\sigma}(q)=q$ cannot give a counterexample. There the fully correlated zero-mean null law ($C\equiv1$) attains $q$ and is a maximizer. Its constant null overlap satisfies the GG identities trivially.
- At $\sigma^2\ge1/2$, the antipodal two-cluster null witness gives $\mathcal F\le q$: exactly $q$ at $\sigma^2=1/2$ and below $q$ above it. The total correlation $2\sigma^2-1$ between the clusters is then nonnegative, so the witness cannot beat GG-compatible laws in that range.
- Survivor (large $\eta$, $\sigma=\sqrt{0.3}$, $q=0.1$). The GG identities force nonnegative null-null overlaps (positivity principle), and this property is closed under weak limits. As $\eta\to\infty$, GG maximizers converge to a zero-moment law. Retagging its zero-mean alternatives as nulls cannot raise the value, so the retagging gain is $0$. Then the positive-Gaussian Simes inequality bounds that law's FDR by $q$. The antipodal zero-moment witness exceeds $q$ by $4.88\times10^{-4}$, which contradicts the bound. This mechanism rules out the claim at every sufficiently large $\eta$ whenever $\sigma<1/\sqrt2$.

## Limitations

- The threshold $\eta_0$ comes from a compactness argument and is not explicit. Moderate and small $\eta$, and $\eta\downarrow0$, were not examined.
- For $\sigma\ge1/\sqrt2$ no zero-moment witness with $\mathcal F>q$ was found, so the large-$\eta$ mechanism is not established there.
- NOT relies on Talagrand's positivity principle (GG identities imply $R^0_{12}\ge0$ almost surely). The target's Notes state it, but it is not a library node and its source location was not verified this round.
- The level $q=q_{\max}$ and the regime $q\downarrow0$ were not treated separately. The same witness has a positive excess at $q=q_{\max}$ for $\sigma^2\in(0,1/2)$, numerically.
