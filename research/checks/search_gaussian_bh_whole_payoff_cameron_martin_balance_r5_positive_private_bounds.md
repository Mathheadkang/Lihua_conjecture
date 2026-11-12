---
type: search_round
title: >-
  Whole-payoff Cameron–Martin round 5: positive private tails and fixed-s
  domination
target_asset: gaussian_bh_whole_payoff_cameron_martin_balance
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 1290e0b2b3058fd8c486827854a892092912869a544c3ce9e36d015c6eacbd8f
performed_by: unknown
created_at: '2026-11-09T22:28:38.834Z'
extension_version: 0.0.4
---

## Obstructions

- **Mixed labels cannot give exact zero selected true mass at a finite positive cutoff.** For positive private smoothing, every finite-center Gaussian tail belongs to $(0,1)$. Thus, if the true-tag mass is $p_0\in(0,1)$, finite centers hold almost everywhere, and the actual rank satisfies $0<R<1$, then $0<\nu<R$ and $\nu<p_0$. Separating mixed-label centers can make a contribution small but cannot make it exactly zero. This rules out that proposed degeneracy, without proving the complete response.

- **A stationary first-order rank need not imply a stationary composition payoff.** In the checked two-atom family in $\mathbb R^2$, take $w_\pm=(\cos\alpha,\pm\sin\alpha)$, true atom $(\theta,\ell)=(-m,1)$ with weight $p$, and false atom $(m,0)$ with weight $1-p$. On $X_2=m/(\tau\sin\alpha)$ the centers coincide at $A=\tau\cos\alpha X_1$, and $c=s$. For $v=e_2$, write $\kappa=\tau\sin\alpha$ and $k(z)=s^{-1}\phi((z-A)/s)$. Direct differentiation gives $f=p$, $\dot Q=(2p-1)\kappa$, $\dot f(r)=2\kappa p(1-p)k(Q(r))/r$, and $\dot M=-(2p-1)\kappa/\sigma$. The complete response is
  $$
  2\kappa p(1-p)\mathbb E_Z\!\left[\frac{\chi_a(R)k(Q(R))}{R}\right]
  +\frac{p(2p-1)\kappa}{\sigma}\int_a^1\chi_a'(r)\phi(M(r))\,dr,
  $$
  with the bulk integrand zero for $R\le a$. At $p=1/2$, the rank term vanishes while the bulk term is positive. At $p<1/2$, the two contributions have opposite signs. Omitting the bulk is therefore not a test of the stated identity. The exact collision lies on a Gaussian-null hyperplane and cannot alone refute an almost-everywhere assertion.

- **Fixed positive private smoothing blocks a separate-term nonintegrability argument based only on narrow kernels.** Put $K=\tau\|v\|$. The conditional formulas give $|\dot Q|\le K$, $|\dot M|\le K/\sigma$, and $|\dot f(r)|\le2K/(r s\sqrt{2\pi})$. Also $|(\chi_af)'(r)|\le\chi_a'(r)+\chi_a(r)/r$. Hence the absolute bulk term is bounded by $2K/(a s\sqrt{2\pi})$ and the absolute rank term by $K[1+\log(1/a)]/(\sigma\sqrt{2\pi})$. These bounds supply a possible domination step once the pointwise formulas are established. The approach is recorded natively as `idea_fae8ccac0b13`.

- **Orthogonal discontinuities in a weight do not alone defeat one-dimensional Gaussian integration by parts.** For $v\ne0$, condition on the orthogonal field and use $Y=X(v)/\|v\|$. An absolutely continuous line-Lipschitz bounded payoff times a bounded coherent $C^1$ weight with bounded directional derivative is absolutely continuous on the line. Its derivative is Gaussian integrable and its Gaussian boundary terms vanish. This conditional argument presupposes the coherent line versions and payoff derivative identification; it does not prove those obligations.

## Limitations

- All three workers reported no candidate; no candidate file was written and no counterexample was established. The general conclusion-failure check remains unknown. The collision calculation diagnoses the necessity of both signed terms; it does not certify the whole theorem.
- The fixed-$s$ bounds do not establish general conditional differentiation, coherent versions, common localization of all active minima, endpoint domination, survival difference-quotient convergence, or the exchanges identifying the signed expression with the ordinary derivative for arbitrary directing laws. Those proof obligations remain open.
- No bound uniform as $s\downarrow0$, arbitrary conditional exchange theorem, uniform-$q$ payment, or result surviving removal of $a$ or $\sigma$ is supplied. These searches do not resolve the unrestricted Gaussian-BH main targets.
