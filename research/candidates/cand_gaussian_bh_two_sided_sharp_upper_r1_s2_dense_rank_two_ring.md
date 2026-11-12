---
type: candidate
title: Dense rank-two Gaussian null directions on a circle
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:34:06.454Z'
extension_version: 0.0.4
---

## Object

For $q\in(0,e^{-2})$, put $L=\log(1/q)$ and
$N=\lceil\exp(L^2)\rceil$. Let $Z_1,Z_2$ be independent standard normals and set
$$
\alpha_i=\frac{\pi i}{N},\qquad
T_i=\cos(\alpha_i)Z_1+\sin(\alpha_i)Z_2,
\qquad i=0,\ldots,N-1.
$$
All means are zero. Use two-sided p-values and ordinary BH at level $q$. Here the number of loading types grows with $q^{-1}$, so this probes beyond the fixed-type union obstruction in the companion candidate. The finite Gaussian arrays themselves, not a population model, are the proposed objects.

## Checks

### H1

$N$ is a finite positive integer at every $q$ and is allowed to grow as above.

### H2

The deterministic mean vector is zero, so every hypothesis is a true null. The FDR equals the probability of at least one BH rejection.

### H3

The covariance is
$$
\Sigma_{ij}=\cos(\alpha_i-\alpha_j).
$$
It is the Gram matrix of unit vectors in $\mathbb R^2$, hence symmetric positive semidefinite with unit diagonal.

### H4

$T=AZ$ is exactly jointly Gaussian with this covariance, with no random means or covariance mixtures.

### H5

Write $p(c)=2\overline\Phi(c)$ and $u_q=p^{-1}(q)$. Conditional on the polar representation $Z=\rho(\cos\psi,\sin\psi)$, let
$$
f_N(c;\rho,\psi)=\frac1N
\#\{i:\rho|\cos(\alpha_i-\psi)|\geq c\}.
$$
The event of a BH rejection is exactly
$$
qK_N(\rho,\psi)\geq1,\qquad
K_N(\rho,\psi)=\sup_{u_q\leq c\leq\rho}
\frac{f_N(c;\rho,\psi)}{p(c)},
$$
with supremum zero when $\rho<u_q$. Indeed a qualifying empirical count at any threshold gives a qualifying BH rank, and conversely a qualifying BH rank supplies such a threshold. This retains the largest-rank step-up procedure and all ties.

### NOT

Fail. In fact the finite arrays satisfy
$$
\lim_{q\downarrow0}\frac{\operatorname{FDR}^{(2)}_{\rm BH}}q
=C_2,\qquad C_2=\sqrt{\frac2{\pi e}},
$$
so their FDR divided by $q\sqrt{\log(1/q)}$ tends to zero. Here is a uniform finite-array justification of the displayed limit.

The continuum angular proportion is
$$
f(c/\rho)=\frac2\pi\arccos(c/\rho),\qquad0\leq c\leq\rho.
$$
Counting equally spaced points in the corresponding circular interval gives
$$
\sup_{\psi,\,0\leq c\leq\rho}
|f_N(c;\rho,\psi)-f(c/\rho)|\leq\frac2N.
$$
Fix a bounded real $t$ and consider radii with
$$
\frac{\rho^2}2=\log\frac1{C_2q}+t.
$$
Then $\rho\sim\sqrt{2L}$, $\rho/u_q\to1$, and
$\rho(\rho-u_q)=\tfrac12\log L+O(1)\to\infty$.
For $c\in[u_q,\rho]$, set $\delta=\rho(\rho-c)$.
Uniform Mills-ratio and arccos expansions give, for $\delta>0$ in this interval,
$$
\frac{f(c/\rho)}{p(c)}
=e^{\rho^2/2}\frac{2\sqrt\delta}{\sqrt\pi}e^{-\delta}
\{1+o(1)\}.
$$
The errors are uniform: $0\leq\delta=O(\log L)$,
$\delta/\rho^2\to0$, and $\delta^2/\rho^2\to0$.
At $\delta=0$ the continuum ratio is zero. Since the interval eventually contains $\delta=1/2$, maximizing $\sqrt\delta e^{-\delta}$ yields
$$
\sup_{u_q\leq c\leq\rho}\frac{f(c/\rho)}{p(c)}
=\{C_2+o(1)\}e^{\rho^2/2}.
$$
The lattice error in the supremum is at most
$$
\frac2{Np(\rho)}
=O\!\left(\frac\rho N e^{\rho^2/2}\right)
=o(e^{\rho^2/2}),
$$
uniformly in $\psi$. Thus
$$
qK_N(\rho,\psi)=e^t\{1+o(1)\}
$$
uniformly in angle. For any fixed $\varepsilon>0$, the radii
$\rho_\pm^2/2=\log(1/(C_2q))\pm\varepsilon$ therefore bracket every conditional radial threshold for a BH rejection when $q$ is small. The rejection event is increasing in $\rho$, because every p-value decreases as $\rho$ increases.

Finally $\mathbb P(\|Z\|\geq x)=e^{-x^2/2}$ in dimension two. Consequently
$$
C_2qe^{-\varepsilon}\leq\operatorname{FDR}^{(2)}_{\rm BH}
\leq C_2qe^{\varepsilon}
$$
for every sufficiently small $q$. Sending $q$ to zero and then $\varepsilon$ to zero proves the claimed finite-array limit. No numerical extrapolation or interchange of an unverified population limit is involved.

## Failure

NOT fails: the exact growing finite Gaussian arrays have FDR asymptotic to $\sqrt{2/(\pi e)}q$, which is smaller than the conjectured scale by a factor tending to zero.
