---
type: candidate
title: Mixed zero-mean tags with a new unit-loading true particle
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 5
slot: 1
direction: boundary_degenerate
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:22:18.949Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space to be the real line, let its unit vector be e=1, and put
$$
\sigma=s=\tfrac12,\quad \tau_s=1/\sqrt2,\quad c=\sqrt3/2,
\quad a=\tfrac18,\quad q=S(1),\quad \rho=1,\quad\lambda=0.
$$
Choose the cutoff that is zero on [0,a], one on [2a,1], and equal to 3u^2-2u^3 on [a,2a], where u=(r-a)/a. Define the deterministic laws
$$
\pi=\tfrac12\delta_{(0,0,1)}+\tfrac12\delta_{(0,0,0)},
\qquad \nu=\delta_{(0,e,1)},\qquad
\pi_\epsilon=(1-\epsilon)\pi+\epsilon\nu.
$$
The false-tagged zero in the base law uses the target's explicitly allowed closed convention. Write X=X(e). Conditional on X, the base and inserted total kernels are
$$
H(t)=S(t/c),\qquad K_X(t)=S\bigl(2(t-X/\sqrt2)\bigr).
$$
The proposed failure mechanism is that adding true mass at the zero-mean boundary, while changing its conditional loading and private variance, might omit a first-order rank contribution after averaging the background.

This is not a kernel-preserving tag swap: K_X differs from H for almost every X. It is not an all-true transfer: the fixed-rank true fraction varies. Nor is this a globally leftward or rightward conditional contamination, since the random center X/sqrt(2) changes sign and the variances differ. These differences remove the reductions responsible for the board's previously tested families.

## Checks

### H1

The Gaussian scales are positive and sigma^2+s^2=1/2<1. The real line is a nonzero separable Hilbert space, and both loadings lie in its closed unit ball.

### H2

The cutoff is nondecreasing and C1, with the prescribed values; 0<a<1/4 and 0<q=q_max. The named approved prerequisites are used with their stated actual-largest-rank convention, rather than selecting a crossing branch independently.

### H3

Both laws are deterministic Borel probabilities chosen before X,Z. Every mean is zero, so both tag implications hold in the closed convention. Both second mean moments are exactly zero.

### H4

For 0<epsilon<1/16, epsilon rho<a/2 and epsilon rho<1. The level is unchanged, epsilon|lambda|=0, and q_epsilon=q_max. Thus this is an admissible fixed mass perturbation, including its boundary level.

### NOT

The proposed missing first-order contribution does not occur. In fact,
$$
H_{\epsilon,X}=(1-\epsilon)H+\epsilon K_X,
\qquad
V_{\epsilon,X}=\tfrac12 H_{\epsilon,X}+\tfrac12\epsilon K_X.
$$
Consequently, at every interior rank,
$$
f_{\epsilon,X}(r)=\tfrac12+
\frac{\epsilon K_X(Q_{\epsilon,X}(r))}{2r},
\qquad
\dot f_X(r)=\frac{K_X(Q(r))}{2r}.
$$
Here Q(r)=cS^{-1}(r), h(Q(r))=phi(S^{-1}(r))/c, and h_0/h=1/2. Substitution into the target's fixed-rank formula gives exactly this nonzero bulk derivative. At rank one, f_epsilon(1)=(1+epsilon)/2, also giving the asserted endpoint derivative 1/2.

The base barrier B(r)=[S^{-1}(qr)-cS^{-1}(r)]/sigma is deterministic and has a unique global minimum t_* in (0,1). To check uniqueness, set u=S^{-1}(qr), v=S^{-1}(r). The ratio phi(u)/phi(v) is strictly increasing: its logarithmic derivative is [u m(u)-v m(v)]/r, positive when v>=0 because x m(x) is strictly increasing on [0,infinity), and positive when v<0 because u>0. The ratio tends to q at zero and infinity at one. Thus B' changes sign exactly once, at c phi(u)/phi(v)=q. The unique suffix minimizer is t_r=max(r,t_*).

For each finite X, ordinary local uniform implicit differentiation gives
$$
\dot Q_X(t)=\frac{K_X(Q(t))-t}{h(Q(t))},
\qquad
\dot M_X(r)=-\frac{K_X(Q(t_r))-t_r}{\sigma h(Q(t_r))}.
$$
There is no escaping minimizer at rank one: for epsilon<=epsilon_0<1 and r>epsilon_0,
$$
Q_{\epsilon,X}(r)\le
Q\left(\frac{r-\epsilon_0}{1-\epsilon_0}\right),
$$
which tends to minus infinity as r increases to one. Hence the elementary envelope argument applies to the actual suffix minimum in this example, without discarding any competing perturbed minimizer.

The conditional rank derivative is generally nonzero. Nevertheless E_X K_X(t)=H(t), since X/sqrt(2)+zeta/2 has variance c^2. Therefore E_X dot M_X(r)=0 for every interior r. This is cancellation after averaging X, not vanishing of the conditional derivative.

The required differentiation for this particular family has a direct domination check. The base survival P(r)=S(M(r)) is Lipschitz on [a/2,1]: it is constant below t_*, smooth above it, and phi(B(r))B'(r) tends to zero at one because c^2/sigma^2=3>1. The elementary inequalities H-epsilon<=H_epsilon<=H+epsilon transfer qualifiers by rank shifts of epsilon and Gaussian shifts of epsilon L_{q,a}/sigma. Thus the corresponding survival difference quotients are uniformly bounded on [a,1] by Lip(P)+L_{q,a}/(sigma sqrt(2pi)), independently of X. This also handles ranks within epsilon of one by extending P as zero beyond one. The payoff-change quotient from the displayed exact identity for f_epsilon is bounded by 1/(2a). Dominated convergence therefore justifies the rank integral and X expectation here.

In particular, since f=1/2 and g'=chi_a'/2, the actual derivative and the target expression both give
$$
\dot{\mathcal F}^{a}
=\mathbb E\left[\chi_a(R)\frac{K_X(Q(R))}{2R}\right]
-\frac12\int_a^1\chi_a'(r)\phi(M(r))\mathbb E_X\dot M_X(r)\,dr
=\tfrac12\mathbb E_Z\chi_a(R).
$$
The bulk integrand is zero at R<=a. Rank one has probability zero. The first equality is obtained by separating the payoff change and survival change as above, not by assuming the target's general interchange assertion. No assertion that this population maximizes either objective is made, so the conditional maximizer inequalities do not supply a violation for this object.

## Failure

NOT fails: this mixed-tag zero-mean loading change has a nonzero bulk response and a conditional rank response, but its background-averaged rank response cancels exactly and the full derivative equals the asserted formula.
