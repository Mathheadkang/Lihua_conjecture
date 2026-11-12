---
type: candidate
title: Coincident zero-mean one-particle tag swap does not break mass variation
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:02:24.062Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space $\mathbb R$, $\sigma=s=1/2$, $q=a=1/10$, $\rho=1$, and $\lambda=0$. Define $\chi_a(r)=0$ for $r\le a$, $\chi_a(r)=3t^2-2t^3$ with $t=(r-a)/a$ for $a<r<2a$, and $\chi_a(r)=1$ for $r\ge2a$.

Let $\pi=\delta_{(0,0,1)}$ and $\nu=\delta_{(0,0,0)}$, with coordinates $(\theta,v,\ell)$. Thus $\pi_\epsilon=(1-\epsilon)\pi+\epsilon\nu$ for $0<\epsilon<1/20$. This tests whether adding the smallest possible false-tagged zero particle creates an extra rank or endpoint term in the claimed mass derivative.

## Checks

### H1

The constants satisfy $\sigma,s>0$, $\sigma^2+s^2=1/2<1$, $0<a<1/4$, and $0<q=1/10<S(1)$. The specified cutoff is nondecreasing and $C^1$, including the two joining points, and has the required values on $[0,a]$ and $[2a,1]$.

### H2

Both laws are deterministic, supported in the unit ball, and lawful in the closed tag convention: the true tag has $\theta=0\le0$, while the false tag has $\theta=0\ge0$. Their second mean moments are zero. They are fixed before innovations, and the approved population construction applies on the common Hilbert space.

### H3

For the stated interval, $\epsilon\rho<\min(a/2,1)$ and $\epsilon|\lambda|=0\le1/2$. The perturbed level is exactly $q$, so remains allowed.

### NOT

Fail for the proposed fixed-rank and full signed derivative violation. Put $c=\sqrt{1-\sigma^2}=\sqrt3/2$. Since $v=0$, the background disappears and both particle kernels are $K(z)=S(z/c)$. Consequently, for every background and every $\epsilon$,

$$
H_\epsilon=H=H_\nu=K,\qquad V=K,\quad V_\nu=0,\quad V_\epsilon=(1-\epsilon)K.
$$

For $0<r<1$ this gives

$$
Q_\epsilon(r)=Q(r)=cS^{-1}(r),\qquad
V_\epsilon(Q_\epsilon(r))=(1-\epsilon)r,\qquad f_\epsilon(r)=1-\epsilon.
$$

In particular the true-mass change is $\epsilon r\le\epsilon<2\epsilon\rho$, including the continuous endpoint at $r=1$. Direct differentiation gives $\dot Q=0$ and $\dot f=-1$. The displayed target formulas give precisely the same answers, because $H_\nu-H=0$ and $V_\nu(Q)-V(Q)=-r$. The endpoint formula gives $\dot f(1)=0-1=-1$ as well.

Total kernels and levels are identical, so the entire actual rank map, every suffix minimum, and every active set are unchanged: $R_\epsilon=R$, $M_\epsilon=M$, and $\dot M=0$. Hence

$$
\mathcal F^a(\pi_\epsilon;q,\sigma,s)
=(1-\epsilon)\mathbb E[\chi_a(R)],\qquad
\dot{\mathcal F}^{a}=-\mathbb E[\chi_a(R)].
$$

This is exactly the target's complete signed formula: its payoff term is $-\mathbb E[\chi_a(R)]$ and its rank term is zero. The conditional payoff difference quotient has absolute value at most one, well below the proposed bound's first term $2\rho/a=20$. There is no cancellation or derivative interchange issue in this object, since the finite-$\epsilon$ identity is exact. Also $M_2(\pi_\epsilon)=0$ exactly. This particular attempted counterexample therefore supplies no violation; it does not verify claims for populations with differing score kernels.

## Failure

NOT fails: swapping a true zero-mean tag for a coincident false zero-mean tag preserves the whole actual rank map and changes the full fractional payoff exactly by its asserted affine mass term.
