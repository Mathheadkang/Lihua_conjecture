---
type: candidate
title: >-
  Opposed residual directions and nonuniform downward transport of two true
  atoms
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
round: 3
slot: 3
direction: small_cases
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:53:53.692Z'
extension_version: 0.0.4
---

## Object

Take $q=1/10$, $\sigma=s=1/2$, $a=1/10$, and $\tau_s=1/\sqrt2$. On the one-dimensional directing space set
$$
\pi=\tfrac12\delta_{(-1,+1,1)}+\tfrac12\delta_{(-1,-1,1)}.
$$
The coordinates are mean, residual direction, and true tag. Use independent standard normals $X,Z$ and independent private normals in every finite model. Give the first atom velocity zero and the second velocity $-1$, and set $\lambda=0$. Thus this is a nonuniform lawful mean transport, not a common translation. Conditional centers are $-1+\tau_sX$ and $-1-\tau_sX$, and both private standard deviations are $s$.

For $a<r<2a$ set $w=(r-a)/a$ and $\chi_a(r)=3w^2-2w^3$; set $\chi_a=0$ below $a$ and $\chi_a=1$ above $2a$.

This tests two opposed residual directions with an identically true population. There is no single residual Gaussian displacement absorbing both centers, unlike the common-direction mixture mechanism on the board. Nonuniform transport changes ranks while the full positive-rank FDP remains one.

## Checks

### H1

$0<q=1/10<1/2$.

### H2

$0<\sigma=1/2<1$.

### H3

$s=1/2>0$ and $\sigma^2+s^2=1/2<1$.

### H4

$0<a=1/10<1/4$.

### H5

The displayed cutoff is nondecreasing and $C^1$, has derivative zero at both joins, takes values in $[0,1]$, vanishes through $a$, and equals one from $2a$ onward.

### H6

$\pi$ is deterministic, both directions have norm one, both true means are $-1\le0$, and $M_2(\pi)=1$. The prescribed private variance is $s^2=1/4$.

### H7

The independent normals give variance $\tau_s^2+s^2+\sigma^2=1$ for every score, with independent private noises. All kernels below are explicit finite Gaussian mixtures.

### H8

The deterministic velocity has $|b|\le K=1$. The perturbed means are $-1$ and $-1-\epsilon$, so all retained true tags remain lawful for $\epsilon\ge0$. The fixed level is allowed throughout.

### NOT

The proposed counterexample fails: its exact cutoff response agrees with the claimed signed formula. Write
$$
A_+=-1+\tau_sX,\quad A_-=-1-\tau_sX,\quad
k_\pm(t)=s^{-1}\phi((t-A_\pm)/s).
$$
Then
$$
H_\epsilon(t)=\tfrac12S((t-A_+)/s)+\tfrac12S((t-A_-+\epsilon)/s),
\qquad
\dot Q(r)=-\frac{k_-(Q(r))}{k_+(Q(r))+k_-(Q(r))}.
$$
Implicit differentiation is valid because the mixture density is strictly positive. Since all tags are true, $v_\epsilon(r)=r$ and $f_\epsilon(r)=1$ on $0<r\le1$, whence $\dot f=0$. The payoff is exactly $\chi_a(R)$, including rank zero.

For this explicit mixture, qualifying rank $t$ is equivalent to $Z\ge B_\epsilon(t)$; hence the largest-rank survival probability is $S(M_\epsilon(r))$. No choice of a local crossing is made. Because $Q_\epsilon(1-)=-\infty$, $B_\epsilon(t)\to+\infty$ as $t\uparrow1$, uniformly for small $\epsilon$ and for each fixed $X$. Also $|Q_\epsilon-Q|\le\epsilon$, so minimizers cannot escape this endpoint. Local uniform implicit differentiation and the elementary minimum comparison therefore give
$$
\dot M(r)=\min_{t\in\mathcal A(r)}
\frac{k_-(Q(t))}{\sigma[k_+(Q(t))+k_-(Q(t))]}.
$$
For completeness, upper bounds follow by testing each unperturbed minimizer; a sequence of perturbed minimizers has a convergent subsequence in the same compact set, whose limit is an unperturbed minimizer, giving the reverse bound. This includes every tied minimizer, without asserting uniqueness or numerical ties.

The layer-cake identity for this cutoff gives directly
$$
\mathcal F_\epsilon^a
=\mathbb E_X\int_a^{2a}\chi_a'(r)S(M_\epsilon(r))\,dr.
$$
Here $|M_\epsilon-M|\le\epsilon/\sigma$ and $\int\chi_a'=1$, so differentiation is dominated in both $r$ and $X$ by $1/(\sigma\sqrt{2\pi})$. Consequently
$$
\dot{\mathcal F}^a
=-\mathbb E_X\int_a^{2a}\chi_a'(r)\phi(M(r))\dot M(r)\,dr,
$$
exactly the target formula with $\dot f=0$ and $(\chi_af)'=\chi_a'$. The difference quotient bound just obtained is smaller than the stated bound for $K=1$.

## Failure

NOT fails: opposed residual centers and nonuniform transport preserve the full signed response, including its all-minima dependence, even though the positive-rank FDP is identically one.
