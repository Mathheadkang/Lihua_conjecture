---
type: candidate
title: Single true Gaussian component under lawful downward translation
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

Take $q=1/10$, $\sigma=s=1/2$, $a=1/10$, $\mathcal H=\mathbb R$ and $\pi=\delta_{(0,0,1)}$. Put $c=\sqrt3/2$. Use independent standard Gaussian $X(1),Z$, and independent private normals for finite models. On $a<r<2a$, set $w=(r-a)/a$ and $\chi_a(r)=3w^2-2w^3$; extend it by zero below $a$ and one above $2a$. Perturb by $b=-1$, $K=1$, and $\lambda=0$. This candidate tests the signed derivative and its domination in the smallest possible directing support.

## Checks

### H1

$0<q=1/10<1/2$.

### H2

$0<\sigma=1/2<1$, $s=1/2>0$, and $\sigma^2+s^2=1/2<1$. Thus $\tau_s=1/\sqrt2$ and $c_s(0)=c$.

### H3

$0<a=1/10<1/4$. The displayed cutoff is nondecreasing, takes values in $[0,1]$, is $C^1$ because its derivative vanishes at both junctions, and has the required zero and one regions.

### H4

The law is deterministic and Borel, its direction has norm zero, its true mean is zero, and $M_2(\pi)=0$. Its marks are lawful.

### H5

The isonormal evaluation at the only direction is $X(0)=0$. The stated independent Gaussian background and private normals satisfy the definition. Each finite score has variance $c^2+\sigma^2=1$.

### H6

The deterministic velocity is bounded by one, and its perturbed true mean is $-\epsilon\le0$ for every $\epsilon>0$.

### H7

$\lambda=0$ leaves the level fixed and allowed.

### NOT

Fail. Write $z_r=S^{-1}(r)$. Exactly,
$$
Q_\epsilon(r)=-\epsilon+c z_r,\qquad f_\epsilon(r)=1,
\qquad B_\epsilon(r)=B_0(r)+\epsilon/\sigma.
$$
Consequently $M_\epsilon(r)=M_0(r)+\epsilon/\sigma$ and $\dot M=1/\sigma$. For this smooth positive-density single-component tail, the actual-largest-rank event is the suffix crossing event, so integration of $\chi_a'$ gives
$$
\mathcal F_\epsilon^a
=\int_a^{2a}\chi_a'(r)S\bigl(M_0(r)+\epsilon/\sigma\bigr)\,dr.
$$
(The positive actual rank is attained because $B_0$ is continuous and tends to $+\infty$ at $1$.) Hence
$$
\dot{\mathcal F}^a
=-\frac1\sigma\int_a^{2a}\chi_a'(r)\phi(M_0(r))\,dr.
$$
This is exactly the asserted full signed response: $\dot f=0$, $(\chi_a f)'=\chi_a'$, and $\dot M=1/\sigma$. Its absolute difference quotient is at most $1/(\sigma\sqrt{2\pi})$, below the claimed larger bound. Thus this concrete one-component perturbation does not refute the tested conclusion.

## Failure

NOT fails: exact common translation reproduces the signed cutoff derivative and satisfies its domination.
