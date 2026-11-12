---
type: candidate
title: >-
  Singular antipodal null pair has cancelling signed OU mixture but no FDR
  excess
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
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T21:56:18.237Z'
extension_version: 0.0.4
---

## Object

For every $0<q\leq S(1)$, take $N=2$, $d=1$, $\theta=(0,0)$, $v_1=1$, $v_2=-1$, and $\Sigma=\left(\begin{smallmatrix}1&-1\\-1&1\end{smallmatrix}\right)$. Write $b=u(q/2)>0$. The full actual FDP is $f(x)=\mathbf1\{|x|\geq b\}$, with endpoint values immaterial to its Gaussian integral.

## Checks

### H1

$N=2$ is finite and positive.

### H2

Both means are real and zero, so $I_0=\{1,2\}$ and $\pi_0=1$.

### H3

The displayed Gram matrix has eigenvalues zero and two, hence is positive semidefinite with unit diagonal.

### H4

The family has $0<q\leq S(1)<1/2$.

### H5

$T=(G,-G)$ is a finite latent Gaussian representation with both vector norms equal to one.

### H6

The two p-values are $S(x)$ and $1-S(x)$. Rank two cannot qualify, because it would require both p-values to be at most $q<1/2$. Rank one qualifies exactly when $\min\{S(x),1-S(x)\}\leq q/2$. Thus the stated $f$ is the full actual BH FDP. Its distinct net jumps are $-1$ at $-b$ and $+1$ at $b$.

For $\rho=e^{-t}$ and $s=\sqrt{1-\rho^2}$, direct differentiation and the identity $\phi(x)\varphi_s(b-\rho x)=\phi(b)\varphi_s(x-\rho b)$ give
$$
J(f)=\phi(b)\int_0^1\left\|\varphi_s(\cdot-\rho b)-\varphi_s(\cdot+\rho b)\right\|_{L^1}\,d\rho
=\phi(b)\int_0^1\left[4\Phi\!\left(\frac{\rho b}{\sqrt{1-\rho^2}}\right)-2\right]\,d\rho.
$$
The signed mixture is combined before its norm. Its integrand is strictly positive for $0<\rho<1$ and at most two, so $0<J(f)<\infty$. At $\rho=0$ the opposite charges cancel exactly.

For either null's conditional p-path, the p-values are $(t,1-t)$ up to exchange. On $0<t<q$, $R_i(t)=1$ for $t\leq q/2$ and zero for $t>q/2$. Therefore $A_i(t)=\min\{2t/q,1\}$ is continuous. Exact net conditional jump charge and positive conditional jump charge are both zero, separately from the nonzero full-FDP OU budget.

### H7

$F=2S(b)=q>0$.

### NOT

$F=q\pi_0$, so the bridge ratio is zero for every family member, despite cancellation of signed OU components.

## Failure

NOT fails: this singular antipodal family reaches the baseline exactly and never has positive FDR excess.
