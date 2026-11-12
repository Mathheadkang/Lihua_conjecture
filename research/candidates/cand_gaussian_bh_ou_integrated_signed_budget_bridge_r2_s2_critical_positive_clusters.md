---
type: candidate
title: Growing-rank near-perfect positive clusters retain nonpositive signed excess
status: failed
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
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
slot: 2
direction: extremal
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:02:23.534Z'
extension_version: 0.0.4
---

## Object

For each integer N>=3 let rho_N=1-1/log(N+e), choose any 0<q_N<=S(1), and take independent standard normals G_0,G_1,...,G_N. Set

$$
T_i=\sqrt{\rho_N}G_0+\sqrt{1-\rho_N}G_i,\qquad \theta_i=0,\quad 1\le i\le N.
$$

All labels are true nulls. The covariance has diagonal one and off-diagonal rho_N. Its rank grows as N even though correlations tend to one on the inverse-logarithmic scale. Use the full ordinary-BH FDP f=1{R_q>0}, without a cutoff, a changed testing procedure, or an absolute jump surrogate. This is distinct from independent null dust and from the singular opposed-block families on the board. The possible motivation is that many rare extremes can have short OU persistence; the calculation below rules out positive FDR excess for this positively correlated realization before any such heuristic is needed.

## Checks

### H1

Pass: N is a finite positive integer for every family member; there is no bound on its growth.

### H2

Pass: theta is the zero vector in R^N, so I_0=[N] and pi_0=1.

### H3

Pass: Sigma_N=(1-rho_N)I_N+rho_N 11^T has eigenvalues 1-rho_N>0 with multiplicity N-1 and 1+(N-1)rho_N>0 with multiplicity one. It is unit diagonal and positive definite.

### H4

Pass: q_N is any member of (0,S(1)], including sequences tending to zero.

### H5

Pass: the displayed representation is finite dimensional, with unit loadings v_i=sqrt(rho_N)e_0+sqrt(1-rho_N)e_i in R^{N+1}. The unused direction is harmless; no dimension reduction is assumed.

### H6

Pass: because every hypothesis is null, the actual BH FDP equals 1 on the event of any rejection and zero otherwise. All thresholds, simultaneous events and the largest qualifying BH rank are retained. J(f) means exactly the OU integral of the spatial Euclidean gradient of this indicator after Mehler smoothing.

In particular, J is finite without replacing it by a sum of positive jumps. Direct Mehler differentiation gives, with a=e^{-t} and s=sqrt(1-a^2), grad T_t f=(a/s)E[G' f(ax+sG')]. For any unit direction u and 0<=f<=1, |E[(u dot G')f]|<=1/sqrt(2pi): project onto u dot G', then bound the conditional factor by a number in [0,1]. Taking the supremum over u gives ||grad T_t f||<=(a/s)/sqrt(2pi). The integral in t is pi/(2sqrt(2pi)). Differentiation is justified by the integrable derivatives of the finite-dimensional Gaussian convolution kernel. This bound is used only for well-definedness, not to infer the BH gate.

### H7

Pass: F=P(R_q>0)>0 because {T_1>=u(q/N)} is contained in the BH rejection event and has probability q/N. Also F<1: a nonempty open neighborhood of T=0 has no rejection, since u(q)>=1, and Sigma_N is positive definite.

### NOT

Fail: the entire growing-rank family has F<=q, hence normalized bridge ratio zero for every member and every admissible q_N. Here is a direct calculation using actual BH ranks.

Put alpha=q/N, U_i=S(T_i), and let R_i^0 be the ordinary BH rank with only p_i replaced by zero. The deterministic BH identity is that i is rejected exactly when U_i<=alpha R_i^0, and then R=R_i^0. Consequently

$$
F_i=\sum_{r=1}^N\frac1r\int_0^{\alpha r}P(R_i^0=r\mid U_i=u)\,du.
$$

For 1<=r<=N define C_r(u)=P(R_i^0>=r | U_i=u), and set C_{N+1}=0. Conditional on T_i=z, every other score has mean rho_N z and a conditional covariance independent of z. Coupling by a fixed residual vector makes all other scores increase as z increases. BH rank is coordinatewise nondecreasing in scores, so C_r(u) is nonincreasing in u. Since C_1=1, telescoping the preceding finite sum gives

$$
F_i=\alpha+\sum_{r=2}^N\left[\frac1r\int_0^{\alpha r}C_r(u)\,du-\frac1{r-1}\int_0^{\alpha(r-1)}C_r(u)\,du\right]\le\alpha.
$$

Each bracket is nonpositive because the average of a nonincreasing function over an initial interval decreases with interval length. Thus F=sum_i F_i<=q. No independence between U_i and R_i^0 was assumed.

The full conditional-p-path quantities can also be distinguished exactly. All true-null means are zero, so the approved finite signed identity gives total expected net charge N(F/q-1)<=0. On each conditional path, increasing t decreases u(t), and all score slopes Sigma_ij are nonnegative; hence R_i(t) is nonincreasing. Therefore A_i(t)=min{t/(q r_i(t)),1}, with the stated rank-zero convention, is nondecreasing. Every actual net jump has A_i(t^-)-A_i(t^+)<=0, and the positive charge B_i is identically zero. These signed and positive quantities are not the OU norm J(f); the gate ratio vanishes because its actual FDR numerator is zero.

## Failure

NOT fails: nonnegative correlations make the full FDR excess nonpositive, uniformly in the growing rank, critical correlation scale, and q_N; no value or lower bound for J is needed for this zero ratio.
