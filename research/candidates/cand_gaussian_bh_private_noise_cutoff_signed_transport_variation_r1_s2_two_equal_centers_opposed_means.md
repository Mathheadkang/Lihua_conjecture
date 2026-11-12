---
type: candidate
title: Two coincident Gaussian components with opposite lawful mean velocities
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
round: 1
slot: 2
direction: small_cases
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:42:50.925Z'
extension_version: 0.0.4
---

## Object

Take $q=1/10$, $\sigma=s=1/2$, $a=1/10$, $\mathcal H=\mathbb R$, and
$$
\pi=\tfrac12\delta_{(0,0,1)}+\tfrac12\delta_{(0,0,0)}.
$$
Let $c=\sqrt3/2$. Use independent standard Gaussian $X(1),Z$ and independent private noises. On $a<r<2a$, set $w=(r-a)/a$ and $\chi_a(r)=3w^2-2w^3$, extended by zero and one. Put $b(0,0,1)=-1$, $b(0,0,0)=1$, $K=1$, and $\lambda=0$. This tests whether a first-order change in the true numerator at fixed total tail is omitted by the response formula.

## Checks

### H1

$0<q=1/10<1/2$.

### H2

$0<\sigma=1/2<1$, $s=1/2>0$, and $\sigma^2+s^2=1/2<1$. The private standard deviation at both directions is $c$.

### H3

$0<a=1/10<1/4$. The cubic interpolation and constant extensions give the required nondecreasing $C^1$ cutoff in $[0,1]$.

### H4

This is a deterministic Borel two-point probability law with directions in the unit ball and $M_2=0$. The true zero and false-tagged zero both belong to the allowed analytic completion.

### H5

The sole direction is zero, so $X$ drops out. The background and independent private noises meet the definition and give marginal variance $c^2+\sigma^2=1$.

### H6

Both velocities are deterministic and bounded by one. The perturbed true mean is $-\epsilon$ and the perturbed false mean is $\epsilon$, so the pushforward is lawful for every $\epsilon>0$.

### H7

The fixed level, $\lambda=0$, remains allowed.

### NOT

Fail. At the unperturbed law, put $z_r=S^{-1}(r)$ and $k(t)=\phi(t/c)/c$. Then
$$
H(t)=S(t/c),\quad Q(r)=c z_r,\quad f(r)=\tfrac12,
\quad h=k,\quad h_b=0,\quad h_0=k/2,\quad h_{0b}=-k/2.
$$
The exact perturbed tails are
$$
H_\epsilon(t)=\tfrac12 S((t+\epsilon)/c)+\tfrac12 S((t-\epsilon)/c),
\quad V_\epsilon(t)=\tfrac12 S((t+\epsilon)/c).
$$
Differentiation of these finite Gaussian sums gives $\dot H=0$, $\dot V=-k/2$, and therefore
$$
\dot Q(r)=0,\qquad \dot f(r)=-\frac{\phi(z_r)}{2cr}.
$$
The vanishing $\dot H$ is locally uniform in thresholds. For each fixed positive $r$, suffix minimizers remain in a compact threshold region away from rank one; uniform first differentiation there gives $\dot M(r)=0$. Thus the target formula gives the complete nonzero first-order response
$$
\dot{\mathcal F}^a
=-\mathbb E_Z\left[\chi_a(R)\frac{\phi(S^{-1}(R))}{2cR}\mathbf1_{\{R>0\}}\right].
$$
It agrees with the direct payoff variation: the total population tail and hence cutoff crossing function have zero first derivative, while the true component loses tail mass at rate $k/2$. The derivative is dominated because $R>a$ on the cutoff support and $k\le1/(c\sqrt{2\pi})$. This tests and confirms the explicit payoff term rather than providing a contradiction.

## Failure

NOT fails: the formula retains exactly the true-numerator loss when the total-tail first variation cancels.
