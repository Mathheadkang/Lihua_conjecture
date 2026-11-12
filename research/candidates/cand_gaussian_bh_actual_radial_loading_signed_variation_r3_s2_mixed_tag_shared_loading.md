---
type: candidate
title: Mixed-tag shared-loading two-atom dilution test
status: failed
target_asset: gaussian_bh_actual_radial_loading_signed_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: 7fdc4735d0d5e381ad9fbb0ee8f7ab5df233763c161d5f77194d54300e4e7cac
performed_by: unknown
created_at: '2026-11-09T18:28:55.333Z'
extension_version: 0.0.4
---

## Object

Take the scalar Hilbert space, sigma = 0.4, s = 0.5, tau squared = 0.59, q = 0.1 and a = 0.1. The directing law gives mass p = 0.4 to the true-tagged particle (0,1,1), and mass 0.6 to the false-tagged particle (mu,1,0), where mu = 1.2. On a < r < 2a use the cutoff chi(r) = y squared times (3-2y), y = (r-a)/a, extended by zero and one on the specified sides.

The proposed failure mechanism is cancellation between a nonzero signed true-tail response and the rank response. This is different from the board's all-true single-atom and antipodal tests: the present fixed-rank FDP is nonconstant, and its integrated derivative is nonzero. No extremality assertion or conditional choice of the law is made.

## Checks

### H1

The regularizers are positive, sigma squared + s squared = 0.41 < 1, 0 < a < 1/4, and q = 0.1 < S(1). The displayed cutoff is nondecreasing and C1, including its joining points.

### H2

Both loading norms are one. The true tag has mean zero and the false tag has strictly positive mean. The deterministic two-point probability law is Borel and has second mean moment 0.6 times 1.2 squared = 0.864. It is chosen before all noises.

### H3

Transport both loadings to 1-epsilon while retaining means, tags and regularizers. The private variance is

$$
c_\epsilon^2=0.25+0.59(2\epsilon-\epsilon^2),
$$

and the combined common Gaussian standard deviation is

$$
t_\epsilon=\sqrt{0.16+0.59(1-\epsilon)^2}=\sqrt{1-c_\epsilon^2}.
$$

The variance sum remains one. Baseline values are c = 0.5, t = sqrt(0.75), dot c = 1.18 and dot t = -0.59/t.

### H4

The conditional population and its actual largest non-strict rank use exactly the required independent scalar X and common Z. Integrating their shared shift combines 0.4 Z + sqrt(0.59)(1-epsilon) X into t_epsilon times a standard normal. This integration does not change the conditional Gaussian model or replace the largest-rank rule. The score-tail shape after removing this shift is

$$
H_c(z)=pS(z/c)+(1-p)S((z-\mu)/c),\qquad V_c(z)=pS(z/c).
$$

Write Q_c for its inverse, f_c(r)=V_c(Q_c(r))/r, b_c(r)=u_q(r)-Q_c(r), m_c(r)=min over r <= u < 1 of b_c(u), and A_c(r) for its full minimizing set. The exact rank survival after integrating X and Z is S(m_c(r)/t). Thus every future competing minimum is retained.

### NOT

The proposed signed-cancellation counterexample fails. Here is an exact reduction of the two terms for this particular finite law. In the following dots mean the specified epsilon derivative at zero. Put z=Q_c(r), alpha_0=z/c, alpha_1=(z-mu)/c, and

$$
h_0=p\phi(\alpha_0)/c,\quad h=h_0+(1-p)\phi(\alpha_1)/c,\quad H^{[c]}=[p\alpha_0\phi(\alpha_0)+(1-p)\alpha_1\phi(\alpha_1)]/c.
$$

Direct implicit differentiation gives

$$
\dot Q_c(r)=\dot c\,H^{[c]}/h,\qquad
\dot f_c(r)=\frac{\dot c}{r}\left[p\alpha_0\phi(\alpha_0)/c-(h_0/h)H^{[c]}\right],
\qquad f_c'(r)=\frac{h_0/h-f_c(r)}r.
$$

The envelope derivative retains all minimizing ranks:

$$
\dot m_c(r)=-\max_{u\in A_c(r)}\dot Q_c(u).
$$

With w=(chi f_c)', direct differentiation of the actual-rank payoff yields

$$
\dot{\mathcal F}^a
=\mathbb E[\chi(R)\dot f_c(R)]
+\int_a^1w(r)\phi(m_c(r)/t)
\left[-\dot m_c(r)/t-0.59m_c(r)/t^3\right]dr.
$$

For this finite mixture the differentiation is justified without a numerical assumption. On ranks bounded away from one all its quantile functions are analytic. As r tends to one, Q_c(r) tends to minus infinity and b_c tends to plus infinity, uniformly for c near 0.5; hence minimizing ranks cannot escape to one. Also |partial_c Q_c| <= (|Q_c|+mu)/c. At an active rank Q_c=u_q-m_c, and u_q stays bounded for ranks at least a. Thus the differentiated survival integrand is bounded by a constant times (1+|m_c|) phi(m_c/t), uniformly bounded. The signed bulk derivative is bounded using 0 <= h_0/h <= 1, r >= a and the bounded derivatives of the two Gaussian kernels; it extends to zero at rank one. Finally |w| <= ||chi'|| + 1/a. These estimates justify the scalar expectation and rank-integral differentiation for this object.

This is exactly the target's two-term response after the shared X is integrated. Indeed its conditional suffix barrier is (m_c-sqrt(0.59)X)/sigma and its derivative is (dot m_c+sqrt(0.59)X)/sigma. Elementary Gaussian integration gives

$$
\mathbb E_X\left[\phi\left(\frac{m_c-\sqrt{0.59}X}{\sigma}\right)
\frac{\dot m_c+\sqrt{0.59}X}{\sigma}\right]
=\phi(m_c/t)\left[\dot m_c/t+0.59m_c/t^3\right].
$$

The fixed-rank f_c and dot f_c are independent of X, so the bulk term also agrees exactly. Both signed terms survive and have opposite signs.

A standard-library scalar midpoint diagnostic, using 30,000 ranks in (a,1), 45 bisections per mixture quantile, and reverse suffix minima, gave baseline payoff 0.0327890011355, bulk response +0.0571099959932, rank response -0.0713754763561, total -0.0142654803629. Direct inward difference quotients were -0.0142683226644 at epsilon = 0.001 and -0.0142657980063 at epsilon = 0.0001. These values are finite-grid diagnostics, not an error-certified proof; the exact reduction above is the reason this mechanism fails.

This test establishes neither the entire statement for arbitrary laws nor its conditional domination and finite endpoint recovery clauses. In particular it does not settle infinitely many competing minima or general loading configurations.

## Failure

NOT is the first failing check: the mixed-tag law has a nonzero dilution term, but its direct actual-rank derivative agrees with the complete signed formula rather than contradicting it.
