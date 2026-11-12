---
type: candidate
title: Orthogonal two-dimensional fold with a negative conditional-FDP jump
status: failed
target_asset: gaussian_bh_diffuse_fold_deformation_recovery
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
performed_by: unknown
created_at: '2026-11-09T01:41:12.916Z'
extension_version: 0.0.4
---

## Object

Take the smallest non-antipodal residual dimension, namely the Euclidean plane, and set
$$
q=1/4,\qquad p=1/2,\qquad \sigma=1/\sqrt {10},\qquad
v_0=e_1,\qquad v_1=e_2,\qquad \vartheta(c)=51/100-c/2.
$$
Use independent standard normal coordinates for the isonormal process and an independent standard normal common score. Thus the resulting standard scores have correlation $\rho=1/10$. Use the prescribed fixed bump $\chi$; the argument below works for every bump allowed by the definition. This tests the sign of the full jump in a small-dimensional example with strictly positive correlation, rather than an independent-score calibration.

## Checks

### H1

$q=1/4$ belongs to $(0,1/2)$.

### H2

$p=1/2$ and $\sigma=1/\sqrt {10}$ belong to $(0,1)$.

### H3

The residual directions are distinct unit vectors in a nonzero separable Hilbert space. The two scores are jointly standard Gaussian and
$$
\rho=\sigma^2+(1-\sigma^2)\langle e_1,e_2\rangle=1/10\in(-1,1).
$$

### H4

The deterministic law is exactly
$$
\pi=\tfrac12\delta_{(0,e_1,1)}+
\tfrac12\int_0^1\delta_{(51/100-c/2,e_2,0)}\,dc.
$$
The quantile is smooth, has derivative $-1/2$, and has endpoint value $1/100>0$. All labels are canonical and all means are bounded.

### H5

Write $u(r)=S^{-1}(r/4)$ and $A=1/8$. Then
$$
g'(c)=1/2-A/\phi(u(r(c))),\qquad
g''(c)=A^2u(r(c))/\phi(u(r(c)))^2>0.
$$
Here $u(1)=0.6744897501\ldots>0$, $g'(0)<0$, and $g'(1)>0$. More explicitly put
$$
w=\sqrt{2\log(4/\sqrt{2\pi})},\quad
r_*=4S(w),\quad c_*=2r_*-1,\quad b=w-51/100+c_*/2.
$$
These give
$$
w=0.9668048695\ldots,\quad r_*=0.6672831793\ldots,\quad
c_*=0.3345663586\ldots,\quad b=0.6240880489\ldots.
$$
Consequently $c_*\in(0,1)$ is the unique global minimum and $g''(c_*)>0$.

### H6

The bump is precisely the prescribed smooth compactly supported $\chi$, with $0\le\chi\le1$, equal to one on $[-1,1]$ and zero outside $[-2,2]$. No monotonicity or symmetry of $\chi$ is added.

### NOT

Fail: this object satisfies the conclusions, including both signs, the actual largest crossings and finite recovery. The following checks exclude a counterexample based only on a predicted local coefficient.

**Actual full-FDR formula, including false-only crossings.** For fixed scores put $A_y(r)=\int_0^1\mathbf1_{\{\vartheta(c)+y\ge u(r)\}}\,dc$ and $H_y^+(r)=p+(1-p)A_y(r)$. Its globally largest qualifying rank is exactly $R_y=r_\vartheta(y)$: for $r>p$, the inequality $H_y^+(r)\ge r$ is equivalent to $y\ge g((r-p)/(1-p))$. The rank $p$ always qualifies. Every actual crossing is at most $R_y$ because $H_\pi\le H_y^+$. If $X_0\ge u(R_y)$, the actual count agrees with the forced count at $R_y$, so the actual largest rank is $R_y$ and its FDP is $p/R_y$. Conversely, true rejection at any actual largest rank $R\le R_y$ implies $X_0\ge u(R)\ge u(R_y)$. On the complementary event, every actual crossing rejects only alternatives and has FDP zero. This argument includes all non-strict endpoint crossings and applies verbatim to both admissible perturbed quantiles.

**Both deformations are admissible.** Put $\alpha=\min_{[0,1]}g''>0$, $\beta=\max_{[0,1]}g''$, and choose
$$
K\ge1,\qquad K^2\ge2\|\chi''\|_\infty/\alpha.
$$
For either sign, the perturbed barrier has second derivative at least $\alpha/2$. Its derivative at $c_*$ remains zero, and its value there is exactly $b+\delta\epsilon$. Thus its unique global minimum occurs exactly at the required point and value. For small $\epsilon$, its support is interior, $\epsilon<1/200$, and $\sqrt\epsilon\|\chi'\|_\infty/K<1/4$. The perturbed quantile is then positive and has derivative below $-1/4$. Coupling identical $c$, directions and labels gives
$$
W_1(\pi_\epsilon^\delta,\pi)
\le4K(1-p)\epsilon^{3/2}.
$$

**The global crossing switches and both signed variations.** On the changed support $|c-c_*|\le2K\sqrt\epsilon$, Taylor's theorem gives $0\le g(c)-b\le2\beta K^2\epsilon$. Hence outside $|y-b|\le C\epsilon$, with $C=2\beta K^2+2$, membership in every level sublevel set is unchanged, so the two globally largest auxiliary ranks agree. This assertion compares whole sublevel sets, not a chosen root. Inside the window, strong convexity puts every point in an active sublevel set within $O(\sqrt\epsilon)$ of $c_*$. Every active largest rank is therefore $r_*+O(\sqrt\epsilon)$. Between the two minimum values the inactive rank is exactly $p$; the active rank tends uniformly to $r_*$. At the minimum values the non-strict convention includes the single minimizing point and gives rank $r_*$.

The conditional kernel is smooth on a fixed compact neighborhood of these ranks and levels. The common-active interval consequently contributes $O(\epsilon^{3/2})$ to the FDR difference. The birth/death interval has length exactly $\epsilon$ and gives
$$
F(\pi_\epsilon^\delta)-F(\pi)
=-\delta\epsilon\phi(b)[k(b,r_*)-k(b,p)]+O(\epsilon^{3/2}).
$$
Direct evaluation for this object gives
$$
k(b,r_*)=0.1361398523\ldots,\quad k(b,p)=0.1371044067\ldots,
$$
$$
\Delta=-0.0009645543\ldots,\qquad
-\phi(b)\Delta=+0.0003167094\ldots.
$$
Thus the positive-barrier deformation increases FDR to first order and the negative-barrier deformation decreases it. The signed formula retains this negative jump; replacing it by its positive part would fail this check. The exact coefficient throughout is the displayed normal-survival expression; decimals are only its numerical evaluation.

**Ordinary finite recovery.** For each fixed sufficiently small $\epsilon$ and either sign, use the rational law with weight $1/2$ at the true zero atom and weight $1/(2n)$ at each of the $n$ positive midpoint means $\vartheta_\epsilon^\delta((j-1/2)/n)$, all in direction $e_2$. If $L_\epsilon=\| (\vartheta_\epsilon^\delta)'\|_\infty$, direct midpoint coupling bounds its Wasserstein error by $L_\epsilon/(4n)$. The approved continuity and finite-approximation theorem in the pack implies convergence of its full actual BH FDR to $F(\pi_\epsilon^\delta)$. Choose $n$ large enough to satisfy both error bounds $\epsilon^2$. Realize the law using $n$ identical true copies and one copy of each alternative, for $N=2n$. Every alternative is strictly positive, every label is canonical, and the unit marginal variances and positive semidefinite covariance follow from the given Gaussian construction. The dependency identifies its ordinary largest-rank BH FDR with the law's population FDR. This proves both recovered signed limits by errors at most $\epsilon^2$, without interchanging a finite-copy derivative and a limit.

**Conditional balance and nonemptiness.** Were the stated finite comparison to hold, the two recovered families and their $o(\epsilon)$ costs would imply both $-\phi(b)\Delta\le0$ and $+\phi(b)\Delta\le0$. Thus this example, whose jump is negative, cannot satisfy that additional comparison premise; it does not refute the conditional conclusion. Finally $M=51/100>a=1/2>0$, and
$$
\frac{1/8}{\phi(u(1))}<1/2<\frac{1/8}{\phi(u(p))}.
$$
So the specified linear nonemptiness clause also holds for this object.

## Failure

NOT fails: both globally correct signed variations and their ordinary canonical finite recoveries agree with the target; the negative jump supplies a sign check rather than a counterexample.
