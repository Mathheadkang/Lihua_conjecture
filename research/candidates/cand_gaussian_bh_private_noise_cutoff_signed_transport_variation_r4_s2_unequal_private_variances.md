---
type: candidate
title: Unequal private variances with a moving narrow false component
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
round: 4
slot: 2
direction: small_cases
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:58:26.202Z'
extension_version: 0.0.4
---

## Object

Take q=1/10, sigma=1/2, s=1/4, a=1/10 and the stipulated cutoff chi_a. On the one-dimensional unit ball put mass 1/2 at each of

$$
x_0=(\theta,v,\ell)=(0,0,1),\qquad x_1=(1,1,0).
$$

Use mean velocity b(x_0)=0, b(x_1)=-1 and lambda=0. Thus the false component moves toward the null while retaining positive mean for 0<=epsilon<1. The residual loading is tau_s=sqrt(11)/4. Conditional on X=x, the two Gaussian score centers before the common displacement are 0 and A=1+sqrt(11)x/4, with private standard deviations c_0=sqrt(3)/2 and c_1=1/4. This tests a narrow moving false component against a broad stationary true component. Unlike the equal-variance location and antipodal families on the board, their conditional private variances are different.

## Checks

### H1

The level satisfies 0<q=1/10<1/2.

### H2

The noise parameters satisfy 0<sigma<1, s>0 and sigma^2+s^2=5/16<1.

### H3

The cutoff parameter satisfies 0<a=1/10<1/4; choose the cutoff required in the statement, without changing it.

### H4

The directing law is deterministic with M_2=1/2. Its true mark has mean zero and its false mark has mean one, so both marks are lawful. Both residual directions belong to the closed unit ball.

### H5

Take X,Z and all individual private Gaussian noises independent. The true score has variance c_0^2+sigma^2=1. The false score has variance tau_s^2+c_1^2+sigma^2=11/16+1/16+1/4=1. The stipulated finite model therefore has independent private noises and the correct unit marginal variances.

### H6

The bounded deterministic velocity has K=1 and is chosen before observations. The true mean remains zero and the false mean is 1-epsilon>0 for 0<=epsilon<1. Hence the right perturbation is lawful and preserves finite second moment.

### H7

The level perturbation lambda=0 is allowed. R is the actual largest non-strict population BH crossing of this Gaussian mixture; no alternative optimizing rank is used.

### NOT

Fail for the proposed mechanism: unequal private variances and motion of the narrow component do not violate the complete signed response.

Here is a direct calculation conditional on every finite background x. Write

$$
H_x(t)=\tfrac12 S(t/c_0)+\tfrac12 S((t-A)/c_1),\quad
V_x(t)=\tfrac12 S(t/c_0),
$$

and write k_j(t)=phi((t-A_j)/c_j)/c_j, with A_0=0 and A_1=A. These are strictly positive smooth densities. The quantile perturbation and fixed-rank payoff perturbation, obtained by differentiating these two displayed tails, are

$$
\dot Q_x(r)=-\frac{k_1(Q_x(r))}{k_0(Q_x(r))+k_1(Q_x(r))},\qquad
\dot f_x(r)=\frac{k_0(Q_x(r))k_1(Q_x(r))}
{2r[k_0(Q_x(r))+k_1(Q_x(r))]}.
$$

In particular the positive true-numerator response cannot be omitted. Moving only the false scores down by epsilon gives the pathwise quantile sandwich Q_x(r)-epsilon<=Q_{x,epsilon}(r)<=Q_x(r). Consequently |B_{x,epsilon}-B_x|<=epsilon/sigma on all ranks. On each suffix [r,1), B_x tends to infinity at its right endpoint because Q_x tends to minus infinity and u_q stays finite. Its minima therefore remain in a compact interior set under sufficiently small epsilon. Differentiating the minimum on this compact set gives, retaining all tied minimizers,

$$
\dot M_x(r)=\min_{t\in\mathcal A_x(r)}
\frac{k_1(Q_x(t))}{\sigma[k_0(Q_x(t))+k_1(Q_x(t))]}.
$$

This derivative is nonnegative and at most 1/sigma. It need not be evaluated at an arbitrarily selected minimizer.

For completeness the full response follows independently from the mixture's actual crossings. With g_x=chi_a f_x, crossing equivalence gives P_Z(R_x>=r)=S(M_x(r)), and integration by parts gives E_Z g_x(R_x)=integral_a^1 g_x'(r)S(M_x(r))dr. Split the perturbed expectation into the payoff change at R_{x,epsilon} and the distribution change of the fixed payoff g_x. The quantile sandwich sandwiches the perturbed rank between the original ranks at common noises z-epsilon/sigma and z+epsilon/sigma. Thus ranks converge except at the countable discontinuities of the monotone function z -> R_x(z), a Gaussian-null set.

The true tail is stationary and has density bounded by 1/(2c_0 sqrt(2pi)); the payoff difference quotient above the cutoff is therefore bounded by 1/(2a c_0 sqrt(2pi)). Also f_x'=((k_0/(k_0+k_1))-f_x)/r, so |f_x'|<=1/r and integral_a^1 |g_x'|<=1+log(1/a). The distribution difference quotient is bounded in integral by [1+log(1/a)]/(sigma sqrt(2pi)). Both constants are independent of x. Dominated convergence in r, Z and X yields exactly

$$
\frac{d}{d\epsilon}\mathcal F^a\bigg|_{0+}
=\mathbb E_X\left[\mathbb E_Z\{\chi_a(R_x)\dot f_x(R_x)\}
-\int_a^1 g_x'(r)\phi(M_x(r))\dot M_x(r)\,dr\right].
$$

This rejects the suggested variance-asymmetry response mechanism, including possible changes of the largest crossing. It is not a verification of the target's general compactification, optimizer or value-limit conclusions.

## Failure

NOT fails: a narrow moving false component and a broad stationary true component still give exactly the full signed numerator-plus-all-minima response, with explicit domination uniform in the Gaussian background.
