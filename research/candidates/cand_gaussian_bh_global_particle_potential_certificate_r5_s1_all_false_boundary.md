---
type: candidate
title: Fully false-tagged boundary law fails global maximality
status: failed
target_asset: gaussian_bh_global_particle_potential_certificate
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: fail
  NOT: unknown
mode: refute
round: 5
slot: 1
direction: boundary_degenerate
statement_digest: 5c18aaddd67e681c31bff48ee957bb54c0681a855d0bfd853d043ea65e593f90
performed_by: unknown
created_at: '2026-11-09T09:49:10.679Z'
extension_version: 0.0.4
---

## Object

Take the real Hilbert space, $\sigma=s=1/2$, $a=1/8$, $\eta=\delta=1$, and $q=S(1)$, so $U=1$. Set $\chi_a(r)=0$ for $r\le a$, $\chi_a(r)=3t^2-2t^3$ for $a<r<2a$, where $t=(r-a)/a$, and $\chi_a(r)=1$ for $r\ge2a$. Let the deterministic directing law be $\pi=\delta_{(1,0,0)}$. All parameters and laws are fixed before the Gaussian innovations. Interpret its kernels, ranks and payoffs using the stated approved conventions and declared prerequisites.

This tests the fully false-tagged boundary of the population class. Its failure is stronger than the board's vanishing-sign observation: a lawful competitor strictly improves the actual regularized objective, so this boundary law is ineligible as a counterexample.

## Checks

### H1

Pass: $\sigma,s>0$, $\sigma^2+s^2=1/2<1$, and $0<a=1/8<1/4$. The displayed cutoff is nondecreasing and $C^1$, with the required zero and unit intervals. The definitions and the declared prerequisite results are retained as hypotheses, without claiming to reverify their proofs.

### H2

Pass: $\eta=\delta=1>0$ and $0<q=q_{\max}=S(1)$.

### H3

Pass: $\pi$ is a deterministic lawful probability law with $\|v\|=0$, false tag $\ell=0$, positive mean $\theta=1$, and $M_2(\pi)=1$. It is canonical because it gives no mass to false-tagged zero means. It is not selected conditionally on any innovation.

### H4

Fail: $(\pi,q)$ is not a genuine global maximizer. Since $V_X\equiv0$, its full FDP and cutoff payoff vanish, giving
$$
J(\pi,q)=-1-\log(1/q).
$$
Compare at the same level with the lawful canonical law $\nu=\delta_{(0,0,1)}$, for which $M_2(\nu)=0$, $c_s(0)=\sqrt{1-\sigma^2}=\sqrt3/2$, and $H_{\nu,X}(z)=S(z/c_s(0))$. Put $r_0=2a=1/4$ and
$$
b=\frac{S^{-1}(qr_0)-c_s(0)S^{-1}(r_0)}{\sigma}.
$$
This is finite. On $\{Z\ge b\}$, the actual BH qualifier inequality holds at $r_0$, so the actual largest rank satisfies $R\ge r_0$. Every particle of $\nu$ is true-tagged; hence $D=1$ on this event and $\chi_a(R)=1$. Consequently
$$
\mathcal F^a(\nu;q,\sigma,s)\ge S(b)>0,
\qquad
J(\nu,q)-J(\pi,q)
=1+\frac{\mathcal F^a(\nu;q,\sigma,s)}q>0.
$$
This uses one explicit finite lawful competitor and does not assume existence or identify the value of any global maximum.

### NOT

Unknown: not evaluated after H4 fails. No conclusion about the certificate at genuine global maximizers follows from this failed object.

## Failure

H4 fails: the zero-mean all-true lawful competitor strictly improves the normalized regularized objective at the same level.
