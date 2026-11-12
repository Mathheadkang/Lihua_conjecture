---
type: search_round
title: 'Round 4: positive-mean boundary calibration and mixed-loading response'
target_asset: gaussian_bh_actual_radial_loading_signed_variation
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 7fdc4735d0d5e381ad9fbb0ee8f7ab5df233763c161d5f77194d54300e4e7cac
performed_by: unknown
created_at: '2026-11-09T18:32:58.237Z'
extension_version: 0.0.4
---

## Obstructions

- **False-tagged zero-mean boundary.** Replacing a false-tagged zero mean by a positive mean $t$ changes its conditional Gaussian tail by at most $t/(s\sqrt{2\pi})$, since the conditional standard deviation is at least $s$. Integrating over any replaced mass of at most one preserves this bound; the second mean moment changes by at most $t^2$. Choosing $t=t(\epsilon)>0$ with $t=o(\epsilon)$ makes both errors $o(\epsilon)$. Thus the false-zero boundary alone does not supply a violating object. This is a tail-and-moment boundary calibration; it does not establish the required full FDR or cutoff FDR endpoint error.
- **Mixed tags with distinct loadings.** For the equal-weight scalar two-atom law on $(\theta,v,\ell)=(0,1,1)$ and $(1,0,0)$ with $\sigma=s=1/2$, only the null atom responds to the prescribed transport. Let $L_0(z)$ denote that atom's inward kernel response and let $h_0,h$ be the true and total conditional densities. Then $\dot H(z)=\dot V(z)=L_0(z)/2$, and at every fixed interior rank $r$ the response is
  $$
  \dot f(r)=\left(1-\frac{h_0}{h}(Q(r))\right)\frac{L_0(Q(r))}{2r}.
  $$
  The rank-induced true-tail correction is retained in this identity. Distinct loadings and mixed tags therefore do not themselves contradict the fixed-rank response: the displayed calculation establishes that response for this object, rather than leaving it unestablished. No candidate was written, and no complete actual-rank identity or general mixed-law result follows from this calibration.
- **Finite moment, infinite support, and cutoff regularity.** The direction testing lawful finite-second-moment laws with infinite support and the permitted general nondecreasing $C^1$ cutoff produced no concrete violating object. Neither these features alone nor an unresolved derivative interchange establishes a failed conclusion. This is a limitation of the attempted mechanism, not an exclusion theorem for all such laws.

## Limitations

- All three slots wrote no candidates in round 4. There is no survivor, no failed-candidate check ledger, and no independent counterexample verification in this round. Absence of a candidate supplies no general theorem.
- The positive-mean replacement controls tails and the second mean moment only. Canonical atomization after fixing each endpoint, recovery of full and cutoff FDR with $o(\epsilon)$ error, and preservation of every endpoint requirement remain to be proved. No finite-model derivative limit was exchanged with $\epsilon$.
- The two-atom calculation verifies the displayed fixed-rank kernel response for its specified law. It does not establish arbitrary mixed-law differentiation, conditional domination, or the complete actual-rank derivative and its integrability.
- Joint measurability and representative invariance for arbitrary directing laws, all required differentiation under the directing law, compact-uniform quantile and barrier differentiation, all-active-minima envelopes, absence of minimizing escapes, convergence of survival difference quotients in $L^1(dr)$, and actual-rank convergence remain proof obligations. The infinite-support and $C^1$-cutoff search did not close them.
- The actual-rank brackets, the payoff difference-quotient bound in both conditional perturbation regimes, signed-weight integration and outer expectation, genuine extremal comparison, and quantitative finite endpoint recovery remain unproved by this search. No identification with a selected dual radial contact derivative, covariance monotonicity, selector Sobolev or bounded-variation regularity, Gaussian integration-by-parts formula, or estimate uniform as regularizers vanish is established.
