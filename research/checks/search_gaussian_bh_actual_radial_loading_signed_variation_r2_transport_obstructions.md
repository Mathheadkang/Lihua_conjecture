---
type: search_round
title: Round 2 radial-loading search obstructions and remaining scope
target_asset: gaussian_bh_actual_radial_loading_signed_variation
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_actual_radial_loading_signed_variation_r2_s2_antipodal_two_well
statement_digest: 7fdc4735d0d5e381ad9fbb0ee8f7ab5df233763c161d5f77194d54300e4e7cac
performed_by: unknown
created_at: '2026-11-09T18:25:15.000Z'
extension_version: 0.0.4
---

## Obstructions

- Fixed positive private smoothing blocks the tested singular conditional-score mechanism, including saturated loadings: the conditional standard deviation stays at least $s>0$. The conditional tail and suffix-barrier regularity examined in this round also obstructed the proposed escape-to-rank-one mechanism on compact rank intervals. These are restrictions on the mechanisms tested, rather than a completed proof of every regularity and compactness assertion in the target.
- Infinite Hilbert dimension alone does not make the proposed integrated Gaussian envelope nonintegrable. Tonelli's theorem and the unit-ball loading constraint give
  $$
  \mathbb E_X\int |X(v)|\,d\pi(x)
  =\sqrt{2/\pi}\int\|v\|\,d\pi(x)
  \le\sqrt{2/\pi}.
  $$
  Thus this envelope cannot be refuted merely by replacing an integrated Gaussian moment with a divergent samplewise supremum over the Hilbert ball. This calculation does not justify all derivative interchanges or the actual-rank domination bound.
- At fixed $q>0$ and $a>0$, the interval $qr\in[qa/2,q]$ is compactly contained in $(0,1)$, so $L_{q,a}$ is finite; the permitted range $q\le q_{\max}=S(1)$ supplies no fixed-regularizer divergence mechanism here. Likewise, false-tagged zero means are lawful in the directing law: treating them as forbidden cannot refute the statement. Their replacement by strictly positive means belongs to the later canonical finite endpoint recovery, which still needs quantitative control.
- Competing visible local wells alone do not force a failure of the signed response formula. The tested all-true, two-atom antipodal law, `cand_gaussian_bh_actual_radial_loading_signed_variation_r2_s2_antipodal_two_well`, passes H1--H4 but fails NOT: its exact full cutoff derivative agrees with the asserted all-active-minima signed formula and admits an integrable bound of the form $A_0+A_1|X|$. The observed local wells were not established to be simultaneous global active suffix minima. This excludes the tested object, without excluding arbitrary competing-minimum families.

## Limitations

- The round produced one failed candidate and no survivor. The other two workers found no plausible candidate in their assigned directions; that outcome does not exhaust those directions and supplies no general proof.
- The explicit two-atom calculation has only true tags. General mixtures of true and false tags, cancellation between the signed true-tail and rank terms, and arbitrary lawful Borel directing laws remain outside its verified scope.
- The full measurable, selection-free envelope over all active suffix minima, possibly infinitely many competing minima, conditional compact uniformity, and survival difference-quotient convergence in $L^1(dr)$ still require complete arguments. The local-well diagnostic does not establish the global active-set geometry.
- Neither the integrated Gaussian moment calculation nor the tested conditional regularity mechanisms establish the claimed conditional actual-rank brackets and the bound uniform in the directing law and Gaussian realization. The small- and large-$d_X$ regimes, weighted limit interchange, and the outer expectation remain proof obligations.
- Joint representative-invariant calculus for the transported family and stated countable endpoint families, arbitrary infinite-dimensional differentiation under the directing law, genuine deterministic extremal comparison, and canonical finite endpoint recovery with $o(\epsilon)$ error have not been settled by this search. In particular, no finite-derivative limit exchange or identification with one chosen dual radial contact derivative is justified here.
- All checks concern fixed positive regularizers and a fixed permitted level. They establish neither covariance monotonicity for arbitrary models nor a $q$-scaled estimate uniform as regularizers vanish.
