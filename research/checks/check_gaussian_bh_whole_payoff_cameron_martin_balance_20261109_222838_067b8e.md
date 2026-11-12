---
type: falsification_check
title: 'Falsification check: gaussian_bh_whole_payoff_cameron_martin_balance'
target_asset: gaussian_bh_whole_payoff_cameron_martin_balance
outcome: no_counterexample_found
statement_digest: 1290e0b2b3058fd8c486827854a892092912869a544c3ce9e36d015c6eacbd8f
performed_by: unknown
created_at: '2026-11-09T22:28:38.943Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: Fixed-tag bounded background shifts do not supply a marked-set violation merely by changing the true-null numerator. On the common particle/private-mark space, the coordinatewise score bounds by the backgrounds at common-factor values shifted by plus or minus the prescribed displacement preserve global BH selection order. Inclusion then bounds both selected mass and true-null mass. The fixed-boundary and zero-mean mixed-tag cases examined in slot 1 retained this sandwich; no violating object was written.
- Obstruction: Opposite unit loadings, with strictly positive fixed private and common smoothing parameters, did not defeat this mechanism in slot 3: the same common-factor displacement bounds every coordinate, even when the loadings have opposite signs. Mixed tags retained the marked-set sandwich in that family. This observation concerns each fixed deterministic direction and makes no assertion of one exceptional set valid simultaneously for all directions.
- Obstruction: An unbounded countably orthogonal Gaussian background does not itself create an unbounded translation along a fixed deterministic direction. The particlewise displacement satisfies |tau (t-u) <w,v>| <= tau |t-u| ||v|| for every unit-ball loading. Thus the proposed unbounded-background family does not defeat the common-factor score comparison merely because the background field lacks a bounded samplewise supremum. No such supremum was used, and no plausible marked-set violation was identified.
- Obstruction: Unbounded lawful means and infinite support do not enlarge that fixed-direction displacement. Strictly positive private variance, c(w) >= s > 0, also prevents a literal unsmoothed atom from arising in these proposals. These mechanisms blocked the proposed routes based solely on unbounded means or support; the searches did not turn this observation into a proof of conditional differentiation or of its exchanges for an arbitrary directing law.
- Obstruction: Tied suffix minima and the rank-one endpoint supplied no plausible violating object in this round. Ties alone do not contradict a pointwise right envelope formula retaining every active minimizer; they can obstruct stronger uniform convergence of derivative quotients, which the statement does not assert. The bounded-shift mechanism blocked the proposed endpoint-escape route, but common compact localization and endpoint domination remain proof obligations.
- Obstruction: A zero direction, or a direction orthogonal to the loadings almost everywhere under the directing law, leaves the translated scores and conditional payoff stationary. These families therefore cannot produce a nonzero directional-response counterexample by translation alone.
- Obstruction: Pure-label directing laws do not challenge the fixed-tag composition response: when the tag is constant, the positive-rank FDP is that constant, so its translation derivative is zero. This does not generally make the complete payoff derivative zero. In the all-true case the rank contribution can remain through the derivative of the cutoff; only the all-false case has identically zero payoff. The pure-label checks supplied no violating object.
- Obstruction: A specified C1 cutoff that is constant on the two sides of its transition has zero derivative at both transition edges. Consequently an edge test cannot obtain a nonzero first-order cutoff contribution by assigning an incompatible derivative at either edge. Strictly positive private variance also makes the integrated score distribution strictly increasing under a common-factor shift: a positive actual rank cannot remain constant over a nontrivial common-factor interval. A proposed positive-rank plateau therefore does not provide an admissible degeneracy in this setting.
- Obstruction: The tested unequal-private-variance, mixed-tag two-atom model exhibited a finite rank birth near rank 0.4306. This diagnostic did not establish a failure of the complete signed response. Its reported numerical residual decreased from approximately 5.9e-5 to 1.4e-6 under refinement, so the finite birth and a coarse residual alone do not establish a nonzero limiting discrepancy.
- Obstruction: The boundary checks at the largest permitted level, in private-tail regimes, and at rank one supplied no endpoint-violation object. They identified no new boundary mechanism beyond the existing bounded-shift and positive-private-variance considerations; compatibility of these checks is not a general endpoint theorem.
- Obstruction: The tested three-atom, mixed-label, two-dimensional model did not produce a violation by retaining the complete signed response. In one tested direction, the full response was approximately 0.15625738917 and the difference quotient approximately 0.15625738875; the discrepancy decreased under refinement to about 4e-10. In the other tested direction, the bulk contribution was approximately -0.04560248 and the rank contribution approximately +0.07966097. These opposite signs show why a check omitting either contribution would not test the stated complete response. These computations are diagnostics for the tested model, not an obstruction proved for every mixed-label law.
- Obstruction: **Mixed labels cannot give exact zero selected true mass at a finite positive cutoff.** For positive private smoothing, every finite-center Gaussian tail belongs to $(0,1)$. Thus, if the true-tag mass is $p_0\in(0,1)$, finite centers hold almost everywhere, and the actual rank satisfies $0<R<1$, then $0<\nu<R$ and $\nu<p_0$. Separating mixed-label centers can make a contribution small but cannot make it exactly zero. This rules out that proposed degeneracy, without proving the complete response.
- Obstruction: **A stationary first-order rank need not imply a stationary composition payoff.** In the checked two-atom family in $\mathbb R^2$, take $w_\pm=(\cos\alpha,\pm\sin\alpha)$, true atom $(\theta,\ell)=(-m,1)$ with weight $p$, and false atom $(m,0)$ with weight $1-p$. On $X_2=m/(\tau\sin\alpha)$ the centers coincide at $A=\tau\cos\alpha X_1$, and $c=s$. For $v=e_2$, write $\kappa=\tau\sin\alpha$ and $k(z)=s^{-1}\phi((z-A)/s)$. Direct differentiation gives $f=p$, $\dot Q=(2p-1)\kappa$, $\dot f(r)=2\kappa p(1-p)k(Q(r))/r$, and $\dot M=-(2p-1)\kappa/\sigma$. The complete response is
- Obstruction: $$
- Obstruction: 2\kappa p(1-p)\mathbb E_Z\!\left[\frac{\chi_a(R)k(Q(R))}{R}\right]
- Obstruction: +\frac{p(2p-1)\kappa}{\sigma}\int_a^1\chi_a'(r)\phi(M(r))\,dr,
- Obstruction: $$
- Obstruction: with the bulk integrand zero for $R\le a$. At $p=1/2$, the rank term vanishes while the bulk term is positive. At $p<1/2$, the two contributions have opposite signs. Omitting the bulk is therefore not a test of the stated identity. The exact collision lies on a Gaussian-null hyperplane and cannot alone refute an almost-everywhere assertion.
- Obstruction: **Fixed positive private smoothing blocks a separate-term nonintegrability argument based only on narrow kernels.** Put $K=\tau\|v\|$. The conditional formulas give $|\dot Q|\le K$, $|\dot M|\le K/\sigma$, and $|\dot f(r)|\le2K/(r s\sqrt{2\pi})$. Also $|(\chi_af)'(r)|\le\chi_a'(r)+\chi_a(r)/r$. Hence the absolute bulk term is bounded by $2K/(a s\sqrt{2\pi})$ and the absolute rank term by $K[1+\log(1/a)]/(\sigma\sqrt{2\pi})$. These bounds supply a possible domination step once the pointwise formulas are established. The approach is recorded natively as `idea_fae8ccac0b13`.
- Obstruction: **Orthogonal discontinuities in a weight do not alone defeat one-dimensional Gaussian integration by parts.** For $v\ne0$, condition on the orthogonal field and use $Y=X(v)/\|v\|$. An absolutely continuous line-Lipschitz bounded payoff times a bounded coherent $C^1$ weight with bounded directional derivative is absolutely continuous on the line. Its derivative is Gaussian integrable and its Gaussian boundary terms vanish. This conditional argument presupposes the coherent line versions and payoff derivative identification; it does not prove those obligations.

## Limitations

- All three workers reported no candidate; no candidate file was written and no counterexample was established. The general conclusion-failure check remains unknown. The collision calculation diagnoses the necessity of both signed terms; it does not certify the whole theorem.
- The fixed-$s$ bounds do not establish general conditional differentiation, coherent versions, common localization of all active minima, endpoint domination, survival difference-quotient convergence, or the exchanges identifying the signed expression with the ordinary derivative for arbitrary directing laws. Those proof obligations remain open.
- No bound uniform as $s\downarrow0$, arbitrary conditional exchange theorem, uniform-$q$ payment, or result surviving removal of $a$ or $\sigma$ is supplied. These searches do not resolve the unrestricted Gaussian-BH main targets.

Object search: 0 candidate(s) in 5 round(s).
