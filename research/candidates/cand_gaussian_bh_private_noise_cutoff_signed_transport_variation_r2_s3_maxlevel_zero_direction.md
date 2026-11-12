---
type: candidate
title: Zero Hilbert direction and pure level descent at the upper level endpoint
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
  H8: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:49:06.009Z'
extension_version: 0.0.4
---

## Object

Take $q=q_{\max}=S(1)$, $\sigma=s=1/2$, $a=1/8$, $\mathcal H=\mathbb R$, and $\pi=\delta_{(0,0,1)}$. Let $b=0$, $K=0$, and $\lambda=-1$, so $q_\epsilon=q(1-\epsilon)$. Choose
$$
\chi_a(r)=\begin{cases}
0,&r\le a,\\
3w^2-2w^3,&a<r<2a,\quad w=(r-a)/a,\\
1,&r\ge2a.
\end{cases}
$$
The proposed failure mechanism was a level response at the allowed upper endpoint with zero mean velocity and a zero Hilbert direction. This does not repeat common translation: the directing law is fixed and only the BH level moves.

## Checks

### H1

$0<S(1)<1/2$, and this level is the permitted upper endpoint $q_{\max}$.

### H2

$0<\sigma=1/2<1$.

### H3

$s=1/2>0$ and $\sigma^2+s^2=1/2<1$, giving $\tau_s^2=1/2$.

### H4

$0<a=1/8<1/4$. The displayed cutoff takes values in $[0,1]$, has derivative $6w(1-w)/a\ge0$ on the transition interval, and has zero derivative at both joins. It is therefore nondecreasing and $C^1$, with the required constant pieces.

### H5

The Hilbert space is nonzero and separable; the deterministic Borel probability has $\|v\|=0\le1$, a lawful true tag at $\theta=0$, and $M_2(\pi)=0$.

### H6

Take independent standard Gaussian $X(1)$, $Z$, and private $\zeta_i$. Since $X(0)=0$, the center is zero and the private variance is
$$
c^2=s^2+\tau_s^2=3/4.
$$
The finite scores are $T_i=c\zeta_i+\sigma Z$ with independent private innovations, and marginal variance $c^2+\sigma^2=1$.

### H7

$b=0$ is bounded, deterministic and lawful; $\pi_\epsilon=\pi$ for all $\epsilon$. Thus $\dot Q=\dot f=0$.

### H8

$\lambda=-1$ is finite and points into the permitted level interval at $q=q_{\max}$; $0<q_\epsilon\le q_{\max}$ for $0\le\epsilon<1$.

### NOT

Fail: the tested pure-level response agrees with the asserted signed formula. Explicitly,
$$
H(t)=V(t)=S(t/c),\qquad Q(r)=cS^{-1}(r),\qquad f(r)=1,
$$
$$
B_\epsilon(r)=\frac{S^{-1}(q(1-\epsilon)r)-cS^{-1}(r)}\sigma.
$$
For every fixed $r>0$, $B_\epsilon(t)\to+\infty$ as $t\uparrow1$, uniformly for $\epsilon$ in a sufficiently small interval, since the first quantile stays finite there and $Q(t)\to-\infty$. Suffix minima are thus attained away from one. The derivative is
$$
\partial_\epsilon B_\epsilon(t)=\frac{m(S^{-1}(q(1-\epsilon)t))}{\sigma(1-\epsilon)}.
$$
For $0\le\epsilon\le1/2$ it is at most $2m(1)/\sigma$, uniformly in $t$, since the argument is at least one and $m$ decreases. Uniform Taylor expansion on the compact set containing all suffix minimizers, followed by choosing minimizing subsequences, gives
$$
\dot M(r)=\frac1\sigma\min_{t\in\mathcal A(r)}m(u_q(t)).
$$
Indeed, evaluation at every unperturbed active minimizer gives the upper bound for the directional minimum; any limit point of perturbed minimizers is active and gives the reverse bound. This uses all active minima, without a uniqueness assumption.

For the actual largest rank, $\{R\ge r\}$ is equivalent to existence of $t\ge r$ with $Z\ge B(t)$, hence to $Z\ge M(r)$. Since $D=1$ whenever $R>0$ and $\chi_a(0)=0$, the exact payoff is
$$
\mathcal F^a(q_\epsilon)=\int_a^{2a}\chi_a'(r)S(M_\epsilon(r))\,dr.
$$
The displayed uniform bound on $\partial_\epsilon B_\epsilon$ passes to the minima and dominates the integral difference quotients by $2m(1)\chi_a'(r)/(\sigma\sqrt{2\pi})$. Therefore
$$
\dot{\mathcal F}^a=-\frac1\sigma\int_a^{2a}\chi_a'(r)\phi(M(r))
\min_{t\in\mathcal A(r)}m(u_q(t))\,dr<0.
$$
This is exactly clause 4 with $\dot f=\dot Q=0$, $\lambda=-1$, and $(\chi_af)'=\chi_a'$. The zero mean-transport bound is not contradicted: that bound is asserted for $\lambda=0$, whereas this object's nonzero response comes from the separately retained level term. This calculation does not establish optimizer status or audit the remaining clauses.

## Failure

NOT fails: pure level descent at $q=q_{\max}$ yields precisely the signed all-minima response, including a nonzero level term despite zero mean velocity.
