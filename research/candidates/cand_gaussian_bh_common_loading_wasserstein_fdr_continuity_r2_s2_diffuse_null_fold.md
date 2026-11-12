---
type: candidate
title: >-
  Diffuse negative nulls and exponential alternatives at an interior
  largest-crossing fold
status: failed
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:46:49.625Z'
extension_version: 0.0.4
---

## Object

Set $q=1/4$, $\sigma=1/2$, $\mathcal H=\mathbb R$, and use only the unit direction $v=1$. Let $a=w=1/2$. For $M>0$ define the deterministic tagged law
$$
\pi_M=w\,\mathcal L(-MU,1,1)+a\,\mathcal L(E,1,0),
$$
where $U$ is uniform on $[0,1]$ and $E$ is exponential with mean one. These variables describe parameter distributions, independently of the sampling randomness. Take $M=1/2$, $M_n=1/2+1/(100n)$, $\pi=\pi_M$, and $\pi_n=\pi_{M_n}$.

The true means are diffuse and negative; the alternative distribution is diffuse with unbounded support. This is not the board's coincident zero-mean null family: the full FDP here is not the true mass times a single rejection indicator. There is an interior fold of the actual largest-crossing curve, and crossing the fold gives a nonzero jump in FDP for an individual realization of the common score.

## Checks

### H1

The fixed testing level $q=1/4$ belongs to $(0,1/2)$.

### H2

The fixed loading $\sigma=1/2$ belongs to $(0,1)$, and $\tau=\sqrt3/2$.

### H3

The space $\mathbb R$ is a nonzero separable real Hilbert space. The only direction is $1$, which has norm one.

### H4

All laws are deterministic Borel probability laws on the stipulated tagged domain. True means $-MU$ are nonpositive; alternative means $E$ are nonnegative and are strictly positive almost surely. Their first moments are
$$
\int|\theta|\,d\pi_M=wM/2+a<\infty.
$$
The same properties hold for every $M_n$.

### H5

Let $\xi,Z$ be independent standard Gaussians. The series representative is the finite sum $X(1)=\xi$, so no exceptional set is needed. Put $W=\tau\xi+\sigma Z\sim N(0,1)$. Every score is exactly $\theta+W$, with unit marginal variance and the prescribed fixed common loading.

### H6

Couple the alternative portions identically and the true portions with the same $U$. The transport cost is
$$
W_1(\pi_{M_n},\pi_M)=w|M_n-M|\mathbb E U=\frac1{400n}\longrightarrow0.
$$
The upper bound follows from this coupling; equality follows from the difference of the mean-coordinate expectations, since the coordinate function is one-Lipschitz for the stipulated metric. Tags and directions do not change.

### NOT

**Clause 1: well-definedness and attained crossings.** Write $u(r)=S^{-1}(qr)$ and $t=u(r)-W$. Directly,
$$
H_M(r)=a e^{-\max(t,0)}+w\left[\frac{-t}{M}\right]_0^1,
\qquad
V_M(r)=w\left[\frac{-t}{M}\right]_0^1,
$$
where $[x]_0^1=\min(1,\max(0,x))$. These functions are continuous for $r>0$ and converge to zero as $r\downarrow0$. Every positive largest crossing is attained. If its count were strictly larger than its rank below one, continuity would produce a larger qualifying rank; hence $H_M(\rho_M)=\rho_M$. At rank one this equality is automatic. The explicit count functions give measurable ranks and FDPs, bounded by one. Finite-dimensional evaluation and Fubini also give the representative invariance in the statement.

**The actual competing-crossing geometry.** If a positive amount of true mass is rejected, every alternative is rejected, so the attained rank is at least $a$. For $r\in[a,1]$, qualification is equivalent to
$$
W\ge B_M(r),\qquad B_M(r)=u(r)+\frac{M}{w}(r-a).
$$
On this interval $u$ is strictly convex because $qr<1/2$. For $M\in[0.5,0.51]$,
$$
B_M'(a)=-q/\varphi(S^{-1}(qa))+M/w<0,
\qquad B_M'(1)=-q/\varphi(S^{-1}(q))+M/w>0.
$$
Thus $B_M$ has a unique interior minimizer $r_*(M)$. It satisfies
$$
y_*(M)=\sqrt{2\log\!\left(\frac{M}{qw\sqrt{2\pi}}\right)},
\qquad r_*(M)=S(y_*(M))/q.
$$
Put $b_*(M)=B_M(r_*(M))$ and $b_1(M)=B_M(1)$. For $W<b_*$ there is no true rejection and the FDP is zero. For $b_*\le W<b_1$, let $r_M(W)$ be the largest root of $B_M(r)=W$. The actual largest rank is this root and its FDP is $(r_M(W)-a)/r_M(W)$. For $W\ge b_1$ the rank is one and FDP is $w$. This retains the upper root when two roots compete; it does not replace the largest-crossing rule by a local crossing.

**Clause 2: microscopic estimate.** For true mean $\theta\le0$, the conditional marginal formula is exactly the stated formula and is at most $F_z$. For every fixed $z,b$, changing variables $y=S^{-1}(t)$ gives
$$
\int_{(0,b]}\frac{dF_z(t)}t
=\int_{S^{-1}(b)}^\infty
\frac{\varphi((y-\sigma z)/\tau)}{\tau S(y)}\,dy<\infty.
$$
The integrand's logarithm has leading quadratic term $-\sigma^2y^2/(2\tau^2)$ and at most a linear term and a logarithmic term. For any attained rank $0<\rho\le\alpha$, the deterministic inequality
$$
D\mathbf1_{\{0<\rho\le\alpha\}}
\le q\int\ell\,\frac{\mathbf1_{\{p\le q\alpha\}}}{p}\,d\pi
$$
holds. Conditional expectation given $Z=z$, the marginal comparison and the bound by one give the displayed envelope in the target. The weighted marginal domination follows, for example, by Stieltjes integration by parts of $1/t$, first on $[\varepsilon,q\alpha]$ and then by monotone convergence. The finite integral decreases to zero as $\alpha\downarrow0$, and dominated convergence applies to the capped envelope. For this particular family the microscopic contribution is already identically zero for $\alpha<a$, because any true rejection entails rank at least $a$.

**Clause 3: averaged continuity despite the fold.** The above exact rank formula gives
$$
F_{\pi_M}=wS(b_1(M))+
\int_{r_*(M)}^1\frac{r-a}{r}\,\varphi(B_M(r))B_M'(r)\,dr.
$$
Every term is continuous in $M\in[0.5,0.51]$. Consequently $F_{\pi_{M_n}}\to F_{\pi_M}$. The nonzero pathwise jump at $b_*(M)$ does not survive averaging as a discontinuity in $M$, since $W$ has a continuous distribution. As a numerical cross-check only, stdlib Simpson quadrature with 2000 panels gives $F_{\pi_{0.5}}\approx0.0635857193$, $F_{\pi_{0.51}}\approx0.0631017293$, and $F_{\pi_{0.5001}}\approx0.0635807619$. Continuity follows from the integral, independently of this numerical diagnostic.

**Clause 4: ordinary finite approximation and replication.** For fixed $M$, use $2k$ atoms of equal mass $1/(2k)$ with true means $-M(j-1/2)/k$ and alternative means $-\log(1-(j-1/2)/k)$ for $j=1,\ldots,k$, direction one, and canonical tags. These are rational parameter laws in the target's sense (rational masses, with unrestricted real means). Midpoint quantile coupling gives $W_1\to0$: the uniform part is immediate; for the exponential part, truncate to a bounded quantile interval and then control the integrable exponential tail. The empirical tagged mean CDFs converge uniformly to their continuous limits, so the corresponding $H,V$ converge uniformly over positive ranks for every fixed $W$.

For $W<b_*(M)$, the negative gap from the minimum prevents any true rejection for all sufficiently large $k$. For $b_*(M)<W<b_1(M)$, the largest root is transversal on the increasing branch, and uniform convergence gives convergence of the actual largest rank and numerator. For $W>b_1(M)$, all means are rejected for sufficiently large $k$. The two excluded values have Gaussian probability zero. Bounded convergence therefore gives convergence of the finite FDRs to the integral above. The same argument applies separately to each $M_n$. Each finite score array has unit diagonal covariance and admissible singular covariance (indeed all residual directions coincide), and its empirical population rank and numerator equal ordinary BH's fractional rank and false count. Uniform replication preserves the empirical law, hence exactly preserves FDR.

Thus every conclusion clause holds for this concrete family. The attempted counterexample fails NOT.

## Failure

NOT fails: a genuine interior fold produces a pathwise jump, but its switching level has Gaussian probability zero and the exact averaged full FDR is continuous under the proposed Wasserstein perturbation.
