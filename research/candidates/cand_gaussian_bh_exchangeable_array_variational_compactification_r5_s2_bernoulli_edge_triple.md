---
type: candidate
title: Independent Bernoulli residual edges fail at three coordinates
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: fail
  NOT: unknown
mode: refute
round: 5
slot: 2
direction: small_cases
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T06:02:21.987Z'
extension_version: 0.0.4
---

## Object

Set $\sigma=1/2$ and $q=S(1)$. For every $i\ge1$ set $(\theta_i,\ell_i)=(0,1)$. Independently for every unordered pair $\{i,j\}$, draw $B_{ij}\sim\operatorname{Bernoulli}(1/2)$ and set $C_{ij}=C_{ji}=B_{ij}$, with $C_{ii}=1$. Draw the parameter array independently of all Gaussian innovations. This is an attempted jointly exchangeable residual-array law, motivated by allowing elementary pairwise residual randomness rather than a prescribed common negative correlation.

## Checks

### H1

Pass: $0<\sigma=1/2<1$.

### H2

Pass: $q=S(1)\in(0,1/2)$, and it also belongs to the normalized level interval $(0,q_{\max}]$.

### H3

Pass: every mark belongs to $E_{\rm mark}$ because $\ell_i=1$ and $\theta_i=0\le0$. All marks are canonical, and $\mathbb E\theta_1^2=0$.

### H4

Pass: the constant marks and the iid unordered-pair variables are invariant in law under simultaneous finite permutations of the indices. Thus the attempted parameter law is jointly exchangeable.

### H5

Pass: its parameter randomness is sampled independently of the Gaussian innovations, as specified in the construction.

### H6

Pass: $C$ is symmetric, $C_{ii}=1$, and every entry lies in $[-1,1]$.

### H7

Fail: not every finite principal matrix is positive semidefinite almost surely. Dimensions one and two pass: the possible two-coordinate matrices have off-diagonal entry zero or one and eigenvalues $(1,1)$ or $(0,2)$. At dimension three, however, the event

$$
E=\{B_{12}=1,\ B_{23}=1,\ B_{13}=0\}
$$

has probability $1/8$. On $E$,

$$
C_{1:3,1:3}=\begin{pmatrix}1&1&0\\1&1&1\\0&1&1\end{pmatrix},\qquad
(1,-1,1)C_{1:3,1:3}(1,-1,1)^{\mathsf T}=-1.
$$

Consequently the attempted array has positive probability of violating the required residual positive semidefiniteness and does not define a law in $\mathfrak P$. This is a three-coordinate obstruction from inconsistent perfect-correlation edges; it differs from the board's constant negative-correlation extension obstruction.

### NOT

Unknown: checking stops at H7. No completed Gaussian FDR, logarithmic bound, extremum, or directing representation conclusion is evaluated for this unlawful residual array.

## Failure

H7 fails: an iid Bernoulli residual-edge array contains, with probability $1/8$, a three-coordinate path whose residual quadratic form equals $-1$.
