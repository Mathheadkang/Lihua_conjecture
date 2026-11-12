---
type: candidate
title: Antipodal mixed labels under upward false-mean transport
status: failed
target_asset: gaussian_bh_private_noise_cutoff_signed_transport_variation
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
round: 3
slot: 1
direction: idea_acdbe615ab6c
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:53:53.692Z'
extension_version: 0.0.4
---

## Object

Set $q=1/10$, $\sigma=s=1/2$, $\tau_s=1/\sqrt2$, $a=1/20$, and
$$
\pi=\tfrac12\delta_{(0,e_1,1)}+\tfrac12\delta_{(1,-e_1,0)}.
$$
Use independent standard normals $X=X(e_1),Z$ and independent private standard normals. Fix any cutoff $\chi_a$ allowed by the target, before observations. The mean velocity is zero on the true atom and $+1$ on the false atom, with $K=1$ and level velocity $\lambda=0$. Thus the perturbed false mean is $1+\epsilon$.

Conditional on $X=x$, write $\alpha=x/\sqrt2$, $\beta=1-x/\sqrt2$, and
$$
H(t)=\tfrac12 S((t-\alpha)/s)+\tfrac12 S((t-\beta)/s),\qquad
V(t)=\tfrac12 S((t-\alpha)/s).
$$
Let $Q(r)$ be the unique solution of $H(Q)=r$, $f(r)=V(Q(r))/r$, and use the target's actual largest rank and suffix minimum. The stress mechanism is that $f'(r)<0$ on the positive-probability event $x>1/\sqrt2$, so the signed rank-transport integral need not have nonnegative density.

## Checks

### H1

The numerical parameters satisfy $0<q<1/2$, $0<\sigma<1$, $s>0$, $\sigma^2+s^2=1/2<1$, and $0<a<1/4$.

### H2

The cutoff is a fixed lawful nondecreasing $C^1$ cutoff as in the target. In particular $\chi_a=0$ on $[0,a]$, $\chi_a=1$ on $[2a,1]$, $0\le\chi_a\le1$, and $\int_a^1\chi_a'=1$. The calculation works for every such cutoff; its shape is not optimized using observations.

### H3

The displayed deterministic probability law has finite second mean moment $M_2(\pi)=1/2$. Both vectors belong to the Hilbert unit ball.

### H4

The first atom is true-tagged with mean zero. The second is false-tagged with strictly positive mean one. Thus both marks are lawful, with no false-zero ambiguity.

### H5

The isonormal background gives residual centers $\alpha,\beta$, and both private variances equal $s^2=1/4$. Each score has total variance $\tau_s^2+\sigma^2+s^2=1$. The private noises can be sampled independently for all tests, independently of $X,Z$ and the parameters. The displayed conditional tails have everywhere positive smooth density.

### H6

The velocity $b=\mathbf1_{\{\ell=0\}}$ is deterministic, bounded by one, and chosen before all observations. Every endpoint $\epsilon\ge0$ retains the lawful signs. Its moment is exactly $M_2(\pi_\epsilon)=(1+\epsilon)^2/2$.

### H7

The level is fixed at $q=1/10$, so $\lambda=0$ and every perturbation remains in the allowed level interval. No assumption of being an extremizer is used; the proposed failure concerns the general signed response in clause 4.

### NOT

The proposed signed-response failure does not occur. Here is a direct conditional calculation, with uniform bounds that permit averaging over $X$.

Put $k_T(t)=s^{-1}\phi((t-\alpha)/s)$, $k_F(t)=s^{-1}\phi((t-\beta)/s)$ and
$$
p(t)=\frac{k_T(t)}{k_T(t)+k_F(t)}.
$$
If $x>1/\sqrt2$, then $\alpha>\beta$, and
$$
\frac{d}{dt}\log\frac{k_T(t)}{k_F(t)}=\frac{\alpha-\beta}{s^2}>0.
$$
Consequently $p$ is strictly increasing. Its average over the mixture tail above any finite $t$ is strictly larger than $p(t)$; this average is exactly $V(t)/H(t)$. At $t=Q(r)$ this proves
$$
f'(r)=\frac{p(Q(r))-f(r)}r<0\quad(0<r<1).
$$
Thus the suggested negative density really exists: $(\chi_a f)'=f'<0$ for $r>2a$ on that event. This is compatible with the target, which retains its sign.

For the chosen transport, implicit differentiation of the two explicit Gaussian tails gives
$$
\dot Q(r)=1-p(Q(r)),\qquad
\dot f(r)=-\frac{k_T(Q(r))\{1-p(Q(r))\}}{2r}.
$$
The numerator changes even though the true atom's own mean stays fixed, because its inclusion threshold moves. These equal exactly the target's $h_b/h$ and $(h_{0b}-h_0h_b/h)/r$ with $h_{0b}=0$.

For completeness, the rank-distribution calculation uses actual ranks, not a free rank choice. Since $H$ is strictly decreasing, the rank inequality at $r$ is equivalent to $Z\ge B(r)$. The supremum of qualifying ranks is attained when positive: for fixed finite $Z$, $H(u_q(r)-\sigma Z)-r<0$ near $r=1$, because $H(S^{-1}(q)-\sigma Z)<1$. Continuity then gives the largest crossing away from one. Hence $\{R\ge r\}=\{Z\ge M(r)\}$. Also $B(r)\to+\infty$ as $r\uparrow1$, so all suffix minima lie in a compact subinterval away from one.

Under the coupling of private scores, every score moves by a number between zero and $\epsilon$. Therefore $0\le Q_\epsilon(r)-Q(r)\le\epsilon$ uniformly. Implicit differentiation is uniform on each compact rank interval, and the compact suffix-minimum envelope gives
$$
\dot M(r)=-\frac1\sigma\max_{t\in\mathcal A(r)}\{1-p(Q(t))\}.
$$
This includes every active minimizer, with no isolated-tie assumption. Furthermore $|M_\epsilon-M|\le\epsilon/\sigma$ everywhere.

Write $g=\chi_a f$. The exact identity for the distribution part, for each fixed $x$, is
$$
\mathbb E_Z[g(R_\epsilon)-g(R)]
=\int_a^1g'(r)\{S(M_\epsilon(r))-S(M(r))\}\,dr.
$$
It follows by integrating $g(R)=\int_a^1 g'(r)\mathbf1_{\{R\ge r\}}dr$; $g$ is absolutely continuous, including its endpoint convention. Since $0\le p,f\le1$, $|f'|\le1/r$, and therefore
$$
\int_a^1|g'(r)|dr\le1+\log(1/a).
$$
The difference quotient of the last display is bounded by $(1+\log(1/a))/(\sigma\sqrt{2\pi})$, independently of $x$.

For the payoff part, $V$ itself is unchanged, and its density is at most $1/(2s\sqrt{2\pi})$. Thus
$$
\sup_r\frac{|\chi_a(r)(f_\epsilon(r)-f(r))|}{\epsilon}
\le\frac1{2as\sqrt{2\pi}}.
$$
As monotone functions of $Z$, actual-rank functions converge under this uniform score perturbation at all continuity values of the unperturbed rank. Their exceptional jump values form a countable set and have Gaussian measure zero. The smooth quantile derivatives above then justify evaluating the payoff quotient at $R_\epsilon$ and taking its limit. Combining the payoff and distribution terms yields exactly
$$
\dot{\mathcal F}^a
=\mathbb E_X\left[\mathbb E_Z\{\chi_a(R)\dot f(R)\}
-\int_a^1(\chi_a f)'(r)\phi(M(r))\dot M(r)dr\right].
$$
The two displayed uniform bounds justify every averaging step in $X$ without restricting it to the event where the true center is higher. Their sum is smaller than the target's stated mean-transport domination bound. Negative $(\chi_a f)'$ therefore contributes a real signed loss already present in the formula; it does not contradict that formula.

## Failure

NOT fails: antipodal mixed labels do produce negative payoff-density transport beyond the cutoff, but the complete signed numerator-plus-all-minima formula reproduces that contribution with uniform Gaussian-integrable domination.
