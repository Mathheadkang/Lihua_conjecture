---
type: candidate
title: Unbalanced independent mixed pair with the false group cloned
status: failed
target_asset: gaussian_bh_rare_clone_mills_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:05:18.154Z'
extension_version: 0.0.4
---

## Object

Take \(N=2\), \(q=S(1)\), \(\theta=(4,-4)\), \(\Sigma=I_2\), \(d=2\),
\(v_1=e_1,v_2=e_2\), and choose \(i=1\). Thus the perturbed group is false and the exact-copy background group is a conservative true null. Use precisely the prescribed offset law and midpoint quantiles. All model data remain fixed during both limits.

Write \(U=1\), \(a=u_1=S^{-1}(q/2)\), \(u_2=1\),
\(u(x)=S^{-1}(qx/2)\), and
\[
L=2\{h(1)-1\},\quad
z(v)=\frac2q\{\phi(v)/v-S(v)\},\quad
b(v)=1-1/v\qquad(v\ge1).
\]
In particular \(z(1)=L\), \(z(\infty)=0\), and
\(z'(v)=-(2/q)\phi(v)/v^2\).
For all checks involving small positive epsilon, use
\(0<\varepsilon<\min\{1/(2L),1\}\).

## Checks

### H1

\(N=2\) is a positive finite integer.

### H2

\(q=S(1)\simeq0.15865525393145707\) is strictly between zero and one half. Its associated \(U=1>0\).

### H3

The fixed means \((4,-4)\) are admissible arbitrary real means. The actual original labels are \(\ell_1=0,\ell_2=1\).

### H4

\(\Sigma=I_2\) is symmetric, positive definite, and has unit diagonal.

### H5

For independent standard Gaussian \(G_1,G_2\), the representation is
\(T_1=4+G_1,T_2=-4+G_2\), with the finite unit directions \(e_1,e_2\), giving exactly the required covariance.

### H6

The chosen coordinate \(i=1\) belongs to \([2]\).

### H7

The displayed epsilon range gives \(\varepsilon L<1\) and
\(\varepsilon/U<1<4=\theta_1\). Every other parameter remains fixed. Every finite clone array uses the prescribed common directions and midpoint offsets.

### NOT

Fail: all four conclusions hold for this object. The mixed fractional-rank effect does not yield a counterexample.

First, integration by parts gives
\[
\int_1^\infty\phi(v)v^{-2}\,dv=\phi(1)-S(1)>0.
\]
Consequently \(0<L<\infty\), the continuous minority mass is
\(\varepsilon L\), and the zero atom has mass \(1-\varepsilon L\).
The map \(v\mapsto\varepsilon b(v)\) takes \([1,\infty)\) into
\([0,\varepsilon)\), with no atom at either image endpoint. Thus the law has all the claimed support properties and its left quantile equals zero at probability \(1-\varepsilon L\). Its quantile, extended by \(Q(0)=0,Q(1)=\varepsilon\), is continuous on \([0,1]\): it is flat through the zero atom and then continuously increasing. Every finite offset lies in \([0,\varepsilon)\).
The altered alternative mean \(4-d_b>3\) stays positive, and the background mean stays \(-4\). The finite arrays are jointly Gaussian with unit marginal variances. Exact copying preserves original BH ranks after multiplication by \(K\), including ties.

Here is an exact calculation of the finite-copy FDP and its inner limit. Temporarily force the entire null group to be available, and let its largest augmented rank, in group units, be
\[
r_{K,\varepsilon}(t)
=\max\left(\{1\}\cup
\left\{1+\frac lK:1\le l\le K,\quad
t\ge u(1+l/K)+d_l\right\}\right).
\]
The midpoint offsets are ordered increasingly. For rank \(K+l\), the displayed inequality says exactly that at least \(l\) alternative copies qualify when all \(K\) null copies count. If the actual null statistic satisfies
\(T_2\ge u(r_{K,\varepsilon}(T_1))\), this largest augmented rank is an actual qualifying BH rank. It also dominates every possible alternative-only rank. If that inequality fails, no smaller augmented rank can reject the null, because its threshold is higher; no larger augmented rank qualifies by the definition of \(r_{K,\varepsilon}\). Hence the exact actual FDP is
\[
f_{K,\varepsilon}(T)
=\frac{\mathbf1_{\{T_2\ge u(r_{K,\varepsilon}(T_1))\}}}
{r_{K,\varepsilon}(T_1)}.
\]
This retains a partial alternative group and uses its actual denominator.

Define its population counterpart
\[
r_\varepsilon(t)
=\sup\{x\in[1,2]:1+C_\varepsilon(x;t)\ge x\}.
\]
For \(1<x<2\), the crossing condition is equivalent to
\(t\ge u(x)+Q_\varepsilon(x-1)\). At \(x=2\) it means
\(t\ge1+\varepsilon\), consistent with the continuous extension \(Q(1)=\varepsilon\).
The midpoint grid thresholds converge uniformly to this continuous threshold curve. Their largest crossing converges at every continuity point of the monotone function \(t\mapsto r_\varepsilon(t)\): uniform threshold approximation brackets the finite crossing by the population crossings at \(t-\delta\) and \(t+\delta\), with grid errors tending to zero. A monotone function has at most countably many discontinuities. Therefore
\(r_{K,\varepsilon}(T_1)\to r_\varepsilon(T_1)\) almost surely.
Independence and bounded convergence give the exact inner limit
\[
\lim_{K\to\infty}F_{K,\varepsilon}
=\mathbb E\, g(r_\varepsilon(T_1)),\qquad
g(x)=\frac{S(u(x)+4)}x.
\]
Indeed the conditional probability of the null threshold event is
\(S(u(r)+4)\). The possible equality event has probability zero since \(T_2\) is continuously distributed and independent of \(T_1\).

This is also precisely the globally largest crossing in the statement whenever a null is rejected. If \(T_2\ge u(r_\varepsilon(T_1))\), its actual rank is \(r_\varepsilon(T_1)\); if the inequality fails, no crossing can reject the null and the actual FDP is zero. Thus the preceding expectation equals the statement's \(\mathbb E f_{\mathrm{pop},\varepsilon}(T)\), without replacing a common crossing by separate optima. For completeness, \(H_\varepsilon(x;T)\) is increasing and right-continuous. Any positive supremum of its qualifying set is itself qualifying. Strict slack \(H(\rho)>\rho\) at \(\rho<2\) would extend the qualifying set to the right by monotonicity; at \(\rho=2\), \(H\le2\). Hence \(H(\rho)=\rho\), including the endpoint.

To calculate the derivative, set
\[
m_\varepsilon
=\min_{v\ge1}
\{u(2-\varepsilon z(v))+\varepsilon b(v)\}.
\]
This is the exact birth threshold for an augmented crossing above one.
The zero-offset atom covers all fractions through \(2-\varepsilon L\); the continuous tail parameterizes fractions \(2-\varepsilon z(v)\) above that value. Fractions below \(2-\varepsilon L\) require at least \(u(2-\varepsilon L)\), already the \(v=1\) member of the minimum. Thus
\(r_\varepsilon(t)=1\) below \(m_\varepsilon\), and
\(2-\varepsilon L\le r_\varepsilon(t)\le2\) above it.
Also \(r_\varepsilon(t)=2\) for \(t\ge1+\varepsilon\), and \(m_\varepsilon\ge1\).

Taylor expansion is uniform in \(v\), because \(0\le z(v)\le L\):
\[
u(2-\varepsilon z(v))
=1+\varepsilon A z(v)+O(\varepsilon^2),
\qquad A=\frac{q}{2\phi(1)}=\frac{m(1)}2.
\]
The derivative of \(Az(v)+b(v)\) is
\[
\frac{1-\phi(v)/\phi(1)}{v^2}\ge0.
\]
Its minimum is therefore \(AL=1-m(1)\), attained at \(v=1\). Consequently
\[
m_\varepsilon
=1+\varepsilon c+O(\varepsilon^2),\qquad c=1-m(1).
\]
Since \(g\) is continuously differentiable on \([1,2]\), the partial-rank correction \(g(r_\varepsilon(t))-g(2)\) is \(O(\varepsilon)\) on its entire support above \(m_\varepsilon\). That support lies inside an interval of length at most \(\varepsilon\), namely \([m_\varepsilon,1+\varepsilon]\). Its integrated contribution is thus \(O(\varepsilon^2)\), not an omitted first-order term. The only first-order contribution is the moved jump:
\[
\lim_{\varepsilon\downarrow0}
\frac{\mathbb E g(r_\varepsilon(T_1))-F}{\varepsilon}
=-c\,\phi(-3)\{g(2)-g(1)\}.
\]

Finally reconstruct the prescribed original-coordinate signed face measures. At the first face \(T_1=a\), the FDP does not change for any \(T_2\) off its threshold set, so \(\mu_{1,1}(E_1)=0\).
At the terminal face \(T_1=1\), the signed jump is \(+1/2\) when
\(1<T_2<a\), \(-1/2\) when \(T_2>a\), and zero when \(T_2<1\). Therefore
\[
\mu_{1,2}(E_1)
=\frac{\phi(-3)}2\{S(5)-2S(a+4)\}
=\phi(-3)\{g(2)-g(1)\}.
\]
The predicted signed formula is exactly the derivative just computed:
\[
-\{1-m(1)\}\,\mu_{1,2}(E_1).
\]
Numerically, \(a\simeq1.409608709293454\),
\(c\simeq0.34432045758120144\),
\(\mu_{1,2}(E_1)\simeq4.952346208916525\,10^{-10}\),
and the derivative is approximately \(-1.705194112754666\,10^{-10}\).
A separate deterministic midpoint quadrature of the exact local transition gives difference quotients approximately
\(-1.720649637\,10^{-10}\), \(-1.709821233\,10^{-10}\), and
\(-1.706735588\,10^{-10}\) at epsilon \(0.01,0.003,0.001\), respectively. These diagnostics corroborate, rather than replace, the preceding analytic calculation.

The parameter-measure inequalities also hold. If \(M_K\) is the number of nonzero midpoint offsets, rounding gives
\(M_K/K\le\varepsilon L+1/K\).
Distinct directions separate the two original groups, so the discrete total variation is \(M_K/(2K)\), bounded by
\(\varepsilon L/2+1/(2K)\). Coupling each moved alternative atom with its original location gives transport cost at most \(\varepsilon M_K/(2K)\). The population total variation is exactly \(\varepsilon L/2\), and the same coupling costs at most \(\varepsilon^2L/2\). Since \(b_\varepsilon=\varepsilon L/2\) and \(U=1\), these are the stated four bounds.

## Failure

NOT fails: in this fixed unbalanced mixed-label model, the actual common-crossing finite-copy limit exists, the fractional FDP correction is second order, and the signed inverse-Mills derivative and both parameter-measure cost bounds agree with the target.
