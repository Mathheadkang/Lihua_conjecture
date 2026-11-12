---
type: candidate
title: Two separated Gaussian mixture branches with competing cutoff minima
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
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:49:06.009Z'
extension_version: 0.0.4
---

## Object

Take $q=1/10$, $\sigma=s=2/5$, $a=1/10000$, $\mathcal H=\mathbb R$, $v=1$, and
$$
\pi=\frac{99}{100}\delta_{(0,1,1)}+\frac1{100}\delta_{(3/2,1,0)}.
$$
Let $\chi_a(r)=0$ for $r\le a$, $\chi_a(r)=1$ for $r\ge2a$, and
$\chi_a(r)=3x^2-2x^3$ for $x=(r-a)/a\in(0,1)$.
Set $b(0,1,1)=0$, $b(3/2,1,0)=1$ and $b=0$ elsewhere; set $\lambda=0$.
This tests the familiar failure of a single selected stationary branch to describe an envelope when a second branch competes. It does not presume that the target makes that selection error.

Write $c=2/5$, $\tau=\sqrt{17}/5$, $d=\sqrt{21}/5$. The deterministic residual tails after removing the common displacement $\tau X$ are
$$
H(t)=.99S(t/c)+.01S((t-3/2)/c),\qquad V(t)=.99S(t/c).
$$
For orientation only, a numerical stationary-point calculation gives local cutoff minima at score coordinates approximately $0.0341330291$ and $1.9069797593$, with ranks approximately $0.4713372751$ and $0.0015456220$. Their cutoff heights divided by $\sigma$ are approximately $4.0979275595$ and $4.2513785513$. These numerical diagnostics are not used to establish a check, do not assert an exact tie, and do not certify the complete list of global minimizers.

## Checks

### H1

The fixed levels and smoothing parameters satisfy $0<q<1/2$, $0<\sigma<1$, $s>0$ and $\sigma^2+s^2=8/25<1$.

### H2

We have $0<a<1/4$. The specified cubic cutoff takes values in $[0,1]$, is nondecreasing and $C^1$, and has the prescribed zero and one regions.

### H3

The law is a deterministic Borel probability on a nonzero separable Hilbert space's unit ball. Its second mean moment is $M_2=9/400<\infty$.

### H4

The true-tagged atom has mean zero and the false-tagged atom has strictly positive mean. Both atoms have unit direction, so the marks and directions are lawful.

### H5

Use independent standard normals $X,Z,\zeta_i$. The scores are $\theta_i+\tau X+c\zeta_i+\sigma Z$. Their conditional-on-parameters variances are $17/25+4/25+4/25=1$, and the private noises are independent across tests.

### H6

The specified velocity is deterministic, Borel and bounded by one. It keeps the true mean at zero and changes the false mean from $3/2$ to $3/2+\epsilon$, which is lawful for every sufficiently small positive $\epsilon$.

### H7

The joint level velocity is the finite number zero, so $q_\epsilon=q$ remains allowed. No attained maximum is claimed or used; the extremal clauses are not the conclusion this object attempts to contradict.

### NOT

Fail: the complete signed derivative agrees with the target for this object. This conclusion has an analytic verification independent of the stationary-point numerics above.

Let $Q$ be the upper quantile of $H$, and set
$$
h_0(t)=.99\phi(t/c)/c,\qquad h_1(t)=.01\phi((t-3/2)/c)/c,
\qquad \alpha(r)=\frac{h_1(Q(r))}{h_0(Q(r))+h_1(Q(r))}.
$$
Differentiating the two explicit tails and the identity $H_\epsilon(Q_\epsilon(r))=r$ gives
$$
\dot Q(r)=\alpha(r),\qquad
\dot f(r)=-\frac{h_0(Q(r))\alpha(r)}r.
$$
The common displacement makes $Q_X(r)=\tau X+Q(r)$ and leaves $f$ unchanged. Define
$$
j(r)=S^{-1}(qr)-Q(r),\qquad J(r)=\min_{t\in[r,1]}j(t),\qquad
\mathcal A(r)=\operatorname*{argmin}_{t\in[r,1]}j(t).
$$
Since $Q(r)\to-\infty$ as $r\uparrow1$, $j(r)\to+\infty$, and the displayed minima are attained away from one for each $r>0$. These facts do not require that the numerically located minima be global or exhaustive. The combined common displacement $W=\tau X+\sigma Z$ is $N(0,d^2)$, and the actual largest-rank crossing gives
$$
\mathbb P(R\ge r)=S(J(r)/d).
$$
The score coupling has $|Q_\epsilon(r)-Q(r)|\le\epsilon$. On every compact rank interval away from one, implicit differentiation is uniform because $h_0+h_1$ is continuous and positive. Together with $j(r)\to+\infty$ and the coupling bound, this prevents minimizers from escaping to one. The elementary compact-minimum envelope argument therefore gives, retaining every active minimizer,
$$
\dot J(r)=-\max_{t\in\mathcal A(r)}\alpha(t).
$$
Put $g=\chi_a f$. The survival representation is $\mathcal F^a=\int_a^1g'(r)S(J(r)/d)\,dr$. Separating the payoff change from the rank-distribution change gives
$$
\dot{\mathcal F}^a
=\mathbb E\left[-\chi_a(R)\frac{h_0(Q(R))\alpha(R)}R\right]
+\int_a^1g'(r)\frac{\phi(J(r)/d)}d
\max_{t\in\mathcal A(r)}\alpha(t)\,dr.
$$
For this separation, the payoff difference quotients are bounded by $2/(ac\sqrt{2\pi})$; the rank-survival difference quotients are bounded by $1/(d\sqrt{2\pi})$. Also $\int_a^1|g'|\le1+\log(1/a)$ because $0\le f\le1$ and $|f'|\le1/r$. Thus all displayed differentiation is dominated. Rank convergence follows from the actual crossing identity outside the null set of common-displacement jump levels; $\chi_a\dot f$ extends continuously through the two rank endpoints. No tied-minimum linearity is used.

Finally $M_X(r)=(J(r)-\tau X)/\sigma$, so
$$
\dot M_X(r)=-\frac{\max_{t\in\mathcal A(r)}\alpha(t)}\sigma,
\qquad
\mathbb E_X\frac{\phi((J(r)-\tau X)/\sigma)}\sigma
=\frac{\phi(J(r)/d)}d.
$$
Substituting these identities into the target's formula reproduces the two terms above with their signs. Hence this competing-branch object does not refute the signed-response conclusion. This check does not establish the target's separate compactness, extremizer, or regularizer-removal assertions.

## Failure

NOT fails for the tested signed-response mechanism: direct integration over the combined Gaussian common displacement yields exactly the target's full payoff term and all-minima rank-distribution term.
