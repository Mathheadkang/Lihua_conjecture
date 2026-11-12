---
type: candidate
title: Fixed strongly anticorrelated two-null model with a clipped high-rank saddle
status: failed
target_asset: gaussian_bh_growing_clone_compensated_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T22:56:18.570Z'
extension_version: 0.0.4
---

## Object

Take N=2, theta=(-1/5,0), q=1/4, chosen group i=1, and

$$
\Sigma=\begin{pmatrix}1&-19/20\\-19/20&1\end{pmatrix}.
$$

Put c=-19/20, v_1=(1,0), v_2=(c,sqrt(1-c^2)), and G=(Z,Y) standard Gaussian in R^2. Thus T_1=-1/5+Z and T_2=cZ+sqrt(1-c^2)Y. Both groups are true nulls. Use the exact private-clone construction in the target, with all private normals independent of (Z,Y), K tending to infinity first, and then epsilon tending to zero. The covariance is fixed; it is not sent to its singular endpoint.

The new feature relative to the singleton board is an exact second block that can enter at a moving fractional-rank boundary. This clips the upper saddle and also permits a separate, very small fractional-entry branch. Both are retained below.

## Checks

### H1

Pass: N=2 is finite, both means are real, the covariance has diagonal one and eigenvalues 1/20 and 39/20, hence is positive definite.

### H2

Pass: q=1/4 belongs to (0,1/2).

### H3

Pass: i=1 belongs to [2] and theta_1=-1/5 is nonzero. The unchanged second mean may equal zero.

### H4

Pass: the displayed two unit rows have Gram matrix Sigma, and G is a finite-dimensional standard Gaussian vector.

### H5

Pass: use S(T_j), with the actual original null set I_0={1,2}. After the sign restriction in H8, all expanded labels are null. Therefore every FDP equals the indicator of at least one rejection, even when the chosen group is only fractionally rejected.

### H6

Pass: all procedures use the largest qualifying rank and non-strict thresholds. Below, every positive crossing is allowed; no predetermined rank is selected.

### H7

Pass: give each group exactly K copies. Group 2 remains exact and group 1 has scores -1/5+d_epsilon+sqrt(1-s^2)Z+s xi_b, with the prescribed s, t_s, d_epsilon and independent standard private xi_b. This is exactly jointly Gaussian and every marginal variance is one.

### H8

Pass: d_epsilon tends to zero, so choose epsilon sufficiently small that d_epsilon<1/5. The chosen mean remains negative and the expanded null set is exactly I_0 times [K].

### NOT

Fail: both asserted conclusions hold for this object. Here are the crossing and asymptotic calculations, including the extra multirank mechanisms.

Write u(x)=S^{-1}(qx/2), u_r=u(r), m=-1/5+d_epsilon+sqrt(1-s^2)Z, and

$$
a(x)=\frac{q}{2\phi(u(x))}=\frac1{x h(u(x))}.
$$

For fixed positive epsilon, the private empirical survival function converges uniformly almost surely to b(x)=S((u(x)-m)/s). On every interval away from zero, a strict population crossing is consequently approximated by finite-copy crossings. Conditional on T_2, m has a nondegenerate Gaussian law. Exceptional tangencies or equalities at the exact-block entry require m to equal a critical value of the analytic functions below, or an endpoint value. Their critical points form a countable discrete set, so these exceptional m values have conditional probability zero.

There is no extra sublinear finite-copy crossing at zero. For every fixed m and s<1, Gaussian tail asymptotics give b(x)/x -> 0 as x -> 0. For x=l/K below a sufficiently small eta, a crossing without the exact block requires at least l chosen successes. If b(x)/x<=delta/e there, a binomial bound gives probability at most delta^l. Summing over l>=1 and then sending eta to zero rules out crossings whose l/K tends to zero. The exact block has a strictly positive conditional entry location and does not affect this argument. This proves convergence of the conditional positive-crossing indicator in probability, and boundedness gives F_{infinity,epsilon}=E D_epsilon.

The largest positive crossing satisfies H(rho)=rho: H is right-continuous with only an upward exact-block jump, is smooth elsewhere, and H(2)<2. If H(rho)>rho, right continuity would extend the crossing set to the right. In the present all-null model J=H, hence D_epsilon is exactly the positive-crossing indicator used above.

For the small-noise calculation define

$$
L_r(x)=u(x)-sS^{-1}(x-r+1).
$$

Let x_1 minimize L_1 on (0,1), and let x_2 minimize L_2 on [3/2,2). Put C_r=L_r(x_r). For small s these are the unique upper minima and x_r tends to r. Indeed on the upper half of the interval, writing t=-S^{-1}(x-r+1)>=0,

$$
L_r'(x)=-a(x)+s/\phi(t),\qquad
\frac{d}{dx}\log\frac{s}{a(x)\phi(t)}
=\frac{t}{\phi(t)}+u(x)a(x)>0.
$$

For r=1 the derivative is negative on the lower half when s is small: a(x)phi(S^{-1}(x)) has a positive infimum there, including its positive limit as x tends to zero. Thus C_1 is the full solo-block threshold. The r=2 lower half is dealt with separately below, rather than incorrectly minimizing L_2 over its entire interval.

At either upper minimum, set t_r=-S^{-1}(x_r-r+1) and delta_r=r-x_r=S(t_r). Then

$$
\phi(t_r)=s/a(x_r)=s x_r h(u(x_r)),\qquad
\delta_r=O(s/t_s),
$$

and Mills expansion and Taylor expansion give

$$
t_r=t_s-\frac{\log\{r h(u_r)\}}{t_s}+o(t_s^{-1}),
$$

$$
C_r=u_r+s(t_s+t_s^{-1})
-\frac{s}{t_s}\log\{r h(u_r)\}+o(s/t_s).
$$

This is the same scalar contact calculation as on the board, now applied to each of the two actual ranks. The following verifies that the exact-block entry does not add a coefficient.

Put c_2=2S(T_2)/q. If T_2>=u_1, the exact block alone ensures a crossing. If T_2<u_2, it never enters and the crossing condition is m>=C_1. If u_2<T_2<u_1, the upper branch is available only for x>=c_2. It has threshold C_2 when c_2<=x_2 and threshold L_2(c_2) when c_2>x_2. Since the joint density of (m,T_2) is bounded uniformly for small s, the probability lost by replacing that clipped threshold with C_2 is bounded by a constant times

$$
\int_{x_2}^2\{L_2(c)-C_2\}\,dc
\le s\int_{x_2}^2[-S^{-1}(c-1)]\,dc
=s\phi(t_2)=O(s^2).
$$

Here dT_2/dc=-a(c) is bounded on [x_2,2], and u(c)-u(x_2)<=0 gives the displayed inequality. Thus the strip has width O(s/t_s), but its integrated crossing correction is O(s^2), not O(s/t_s).

There can also be a crossing on 1<x<3/2 that is absent from the upper-branch description. Such an extra event must have m<C_2. For small s, u(x)-m is then bounded below by a positive constant, since u(3/2)>u_2 and C_2 tends to u_2. The crossing inequality requires

$$
x-1\le b(x)\le S(\kappa/s)
$$

for some fixed kappa>0. Since c_2<=x, this forces T_2 into a strip of exponentially small width immediately below u_1. Its probability is exponentially small. This retains the small fractional-entry branch rather than discarding it by rank selection.

Consequently, with an error O(s^2)+O(exp(-kappa'/s^2)), the expanded limiting FDR equals

$$
P(T_2\ge u_1)
+P(T_2<u_2,m\ge C_1)
+P(u_2\le T_2<u_1,m\ge C_2).
$$

The original FDR is exactly this expression with m=T_1 and C_r=u_r. The change sqrt(1-s^2)Z-Z is O(s^2) at the level of these smooth bivariate Gaussian probabilities. Subtracting d_epsilon from C_r therefore gives

$$
\lim_{s\downarrow0}\frac{F_{\infty,\varepsilon}-F}{s/t_s}
=\log\{h(u_1)\}\phi(u_1+1/5)
 P(T_2<u_2\mid T_1=u_1)
$$

$$
\qquad+\log\{2h(u_2)\}\phi(u_2+1/5)
 P(u_2<T_2<u_1\mid T_1=u_2).
$$

For the original all-null BH, the rank-1 face jump is exactly 1{T_2<u_2}; the rank-2 face jump is exactly 1{u_2<T_2<u_1}. All other face jumps vanish. Hence the two weights on the last display are precisely the target's signed face masses mu_{1,1}(R) and mu_{1,2}(R). Their numerical values, computed with standard-library Gaussian tails only, are approximately 0.160307688403 and 1.94676410407e-7, respectively; the resulting coefficient is approximately 0.0799698579581. These numbers are a diagnostic; the analytic expansion establishes failure of NOT.

## Failure

NOT fails: the fixed strongly anticorrelated two-null model has the claimed finite-copy limit and compensated coefficient; clipping the upper saddle contributes O(s^2), while its separate low fractional-entry branch contributes only exponentially small mass.
