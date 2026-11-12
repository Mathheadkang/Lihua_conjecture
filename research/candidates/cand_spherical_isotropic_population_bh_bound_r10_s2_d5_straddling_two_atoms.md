---
type: candidate
title: Dimension-five two-atom alternative straddling the cutoff boundary
status: failed
target_asset: spherical_isotropic_population_bh_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 10
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T07:46:48.544Z'
extension_version: 0.0.4
---

## Object

Set $d=5$, $u=104$, $q=2Q(u)$, and
$$
W=\frac35\delta_0+\frac15\delta_{u-u^{-1}}+\frac15\delta_{u+u^{-1}}.
$$
At each of these three means, use the uniform direction law on $\mathbb S^4$, independently of the mean, and zero residual variance. Use the stated smallest-finite-contact convention. Thus $\pi_0=3/5$.

This bounded small case has two positive-mean atoms on opposite sides of $u$, with only $W([u,\infty))=1/5$. Its check below uses the exact dimension-five cubic cap rather than the dimension-four one-atom objects named on the board.

## Checks

### H1

Pass: $d=5$ is an integer at least four.

### H2

Pass: $W$ is a Borel probability law on $[0,\infty)$, since $u-u^{-1}>0$, and its three displayed masses sum to one. Its null mass is exactly $3/5$.

### H3

Pass: the population measure is the product $W\otimes\sigma_4$. The same uniform directional law applies at every absolute mean and is independent of that mean.

### H4

Pass: the statistic is exactly $T_{\mu,v}=\mu+v^\top Z$ with $Z\sim N(0,I_5)$ and no residual observation noise.

### H5

Pass: $q=2Q(104)\in(0,1)$, and strict monotonicity of $Q$ gives $Q^{-1}(q/2)=104$.

### H6

Pass: use exactly $\mathcal C_r=\{x\geq u:F_r(x)\geq2Q(x)/q\}$, $x_r=\min\mathcal C_r$ when nonempty, the contact identity, and FDP zero when no finite contact exists. Existence for all $r\geq u$ follows from the explicit admissible cutoff in the NOT check. If $r<u$, the null rejection mass is zero at every permitted cutoff, whether or not a contact exists.

### NOT

Fail. In dimension five the first directional coordinate has density $3(1-z^2)/4$ on $[-1,1]$, by normalizing the spherical marginal. Hence, for $0\leq t\leq r$,
$$
H_r(t)=\frac12-\frac{3t}{4r}+\frac{t^3}{4r^3}.
$$
Put $x_0=u+2/u$. For every $r\geq u$, the two differences $x_0-(u-u^{-1})=3/u$ and $x_0-(u+u^{-1})=1/u$ belong to $[0,r]$. Dropping all other nonnegative tail contributions gives
$$
\begin{aligned}
F_r(x_0)
&\geq\frac15\{H_r(3/u)+H_r(1/u)\}\\
&=\frac15-\frac{3}{5ur}+\frac{7}{5u^3r^3}\\
&\geq\frac15-\frac{3}{5u^2}
>\frac16.
\end{aligned}
$$
The last inequality uses $u^2>18$. For $a=2/u$, shifting the Gaussian tail integral gives
$$
\frac{2Q(x_0)}q
=\frac{Q(u+a)}{Q(u)}
\leq e^{-au-a^2/2}
\leq e^{-2}
<\frac16.
$$
Thus $x_0$ is admissible for every $r\geq u$, so $u\leq x_r\leq x_0$ and, by monotonicity of $F_r$, $F_r(x_r)\geq F_r(x_0)>1/6$. At such radii,
$$
\operatorname{FDP}_{\rm pop}(r)
=\frac{2\pi_0H_r(x_r)}{F_r(x_r)}
\leq12\pi_0H_r(u).
$$
For $r<u$ both the FDP and $H_r(u)$ vanish, so this bound holds for every radius. If $V$ is an independent uniform direction, then $V^\top Z\sim N(0,1)$, yielding $\mathbb E H_R(u)=Q(u)$. Consequently
$$
\operatorname{FDR}_{\rm pop}\leq12\pi_0Q(u)=6q\pi_0.
$$
Meanwhile the displayed target constant at $d=5$ is
$$
M_5=\frac1{2\sqrt3},\qquad
2+4M_5(1+u^{-2})\log(3u)
=2+\frac2{\sqrt3}(1+u^{-2})\log312>7,
$$
since $2/\sqrt3>1$ and $\log312>5$. Thus the candidate satisfies the proposed bound strictly, even before adding $e^{-2u^2}$. No numerical underflow or approximate Gaussian-tail evaluation is used.

## Failure

NOT fails first: the exact dimension-five cubic caps furnish a uniform rejection-mass floor above $1/6$, which bounds FDR by $6q\pi_0$, below this target's coefficient exceeding seven.
