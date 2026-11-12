---
type: candidate
title: Exponentially growing all-null perfectly dependent family
status: failed
target_asset: gaussian_bh_two_sided_exact_pivotal_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 5
direction: extremal
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:02:43.032Z'
extension_version: 0.0.4
---

## Object

For each integer $m\ge1$, let $q_m=e^{-m}$, $N_m=2^m$,
$\theta=0\in\mathbb R^{N_m}$, and $\Sigma=\mathbf1\mathbf1^{\mathsf T}$.
Take $T_j=Z$ for all $j$, where $Z\sim N(0,1)$, and use ordinary two-sided
BH. This probes simultaneously unbounded dimension, maximal singular
dependence, and a forced-zero rank that spends almost all its probability
at its minimum value while its largest possible reciprocal threshold is
$N_m/q_m$. It is distinct from a shifted negatively correlated pair:
here the entire null multiplicity moves as one tied cluster.

## Checks

### H1

For every $m$, $N_m$ is a finite positive integer and all means are finite.
The sequence is allowed to depend on $q_m$ without a uniform dimension cap.

### H2

$\Sigma$ is symmetric PSD because $x^{\mathsf T}\Sigma x=(\sum_jx_j)^2\ge0$,
and its diagonal equals 1. The vector $T=Z\mathbf1$ is jointly Gaussian,
with a rank-one covariance; no nonsingularity condition is imposed.

### H3

$0<q_m<1$. For the optional small-level fixed notation, take $m\ge2$,
so $q_m\le e^{-2}<2\overline\Phi(1)$.
Every p-value equals $P=2\overline\Phi(|Z|)$, which is uniform on $(0,1)$.

### H4

Every coordinate is a true null, so $I_0=[N_m]$ and $\pi_0=1$.
For every $i$, $c_i=\mathbf1$ and $Y_i=0$ identically.

### NOT

The proposed amplification fails. For a common p-value $P$, a rank $k$
qualifies precisely when $P\le q_m k/N_m$. Thus the ordinary BH rank is
$N_m$ on $\{P\le q_m\}$ and 0 otherwise. Since every rejection is false,
$\operatorname{FDR}=\mathbb P(P\le q_m)=q_m$.

When only coordinate $i$ is forced to zero, its forced-zero rank is
$N_m$ on $\{P\le q_m\}$ and 1 on $\{P>q_m\}$: in the second case all ranks
$k\ge2$ fail because their nonzero order statistic is $P>q_m$.
Consequently

$$
a(T_i;\tau_i(T_i,0))=\frac{\mathbf1\{P\le q_m\}}{q_m}.
$$

The potentially huge value $N_m/q_m$ is never attained: when $\tau_i=q_m/N_m$
the null does not pass even the larger threshold $q_m$.
Therefore $\Delta_i=0$ for every $i$ and
$q_m\pi_0+(q_m/N_m)\sum_i\Delta_i=q_m=\operatorname{FDR}$ exactly.
For any Borel grid-valued $g$, $g(Y_i)=g(0)$ is a fixed positive threshold,
so $\mathbb E a(T_i;g(Y_i))=1$ as well.
Each branch threshold has only one jump, at
$\overline\Phi^{-1}(q_m/2)$, consistent with the stated finite-jump bound.
Repeating every coordinate any finite number of times changes only the
cluster size; the above threshold, FDP and $\Delta_i=0$ remain the same.

## Failure

NOT fails: the small forced-zero threshold occurs only when its numerator vanishes, so arbitrarily large perfectly tied null clusters give FDR exactly q and zero pivotal excess.
