---
type: candidate
title: >-
  Heavy positive false means create positive ranks but do not defeat microscopic
  FDP control
status: failed
target_asset: gaussian_bh_private_noise_cutoff_signed_transport_variation
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
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T06:49:06.009Z'
extension_version: 0.0.4
---

## Object

Take $q=1/10$, $\sigma=s=1/2$, $a=1/8$, and $\mathcal H=\mathbb R$. Let $Y$ have density $3y^{-4}\mathbf1_{[1,\infty)}(y)$ and define the deterministic directing law
$$
\pi=\tfrac12\delta_{(0,0,1)}+\tfrac12\mathcal L(Y,0,0).
$$
Thus the false means are unbounded and have a polynomial upper tail, while their second moment is finite. Set $b=0$, $K=1$, and $\lambda=0$. Define $\chi_a(r)=0$ for $r\le a$, $\chi_a(r)=3w^2-2w^3$ for $a<r<2a$, where $w=(r-a)/a$, and $\chi_a(r)=1$ for $r\ge2a$.

The attempted violation is the microscopic-rank conclusion in clause 1: the polynomial false tail makes the actual rank positive at every finite common-noise value, potentially sustaining FDP at very small ranks. No assertion that this law is a penalized maximizer is made.

## Checks

### H1

The numerical parameters satisfy $0<q<1/2$, $0<\sigma<1$, $s>0$, $\sigma^2+s^2=1/2<1$, and $0<a<1/4$. Also $q<S(1)$ if the normalized level interval is considered.

### H2

The specified cutoff is nondecreasing, takes values in $[0,1]$, and is $C^1$: on its transition interval its derivative is $6w(1-w)/a$, which vanishes at both joins. It has the required zero and one regions.

### H3

The law is a deterministic Borel probability on the one-dimensional unit-ball parameter space. Its second mean moment is
$$
M_2(\pi)=\tfrac12\int_1^\infty 3y^{-2}\,dy=\tfrac32<\infty.
$$
Every directing vector is zero.

### H4

The true-tagged mean is zero, and all false-tagged means are at least one. Thus both mark implications hold; in particular there is no false-tagged zero requiring canonical approximation.

### H5

Use independent standard normals $X,Z,\zeta_1,\zeta_2,\ldots$, independent also of all iid parameter draws. Since $v=0$, the background contribution is identically zero and
$$
c_s(0)^2=s^2+\tau_s^2=\tfrac34=:c^2.
$$
Conditional-on-parameters finite scores are $T_i=\theta_i+c\zeta_i+\sigma Z$, with variance $c^2+\sigma^2=1$ and independent private noises. The kernels are
$$
H(t)=\tfrac12 S(t/c)+\tfrac12\int_1^\infty S((t-y)/c)3y^{-4}\,dy,
\qquad V(t)=\tfrac12S(t/c).
$$

### H6

The fixed velocity $b=0$ is deterministic, Borel, bounded by $K=1$, and lawful for every positive perturbation size. The level velocity is zero, so every endpoint has the same allowed level.

### NOT

Fail. First verify that the potentially dangerous extreme behavior really occurs. For $t\ge1$, independence of $Y$ and a fresh standard normal $\zeta$ gives
$$
H(t)\ge\tfrac12\mathbb P(Y\ge2t)\mathbb P(c\zeta\ge-t)
\ge\frac1{32t^3}.
$$
For every fixed finite $z$, $u_q(r)-\sigma z\to\infty$ and grows as $O_z(\sqrt{\log(1/r)})$ when $r\downarrow0$. Consequently
$$
\frac{H(u_q(r)-\sigma z)}r\longrightarrow\infty.
$$
There are therefore positive qualifying ranks for every finite $z$. Nevertheless $H(u_q(1)-\sigma z)<1$, so a neighborhood of rank one contains no crossing. Continuity then shows that the largest crossing is attained at $R(z)\in(0,1)$ and satisfies the exact self-consistency identity
$$
H(u_q(R(z))-\sigma z)=R(z).
$$
The full FDP at that actual rank is exactly
$$
D(z)=\frac{F_z(qR(z))}{2R(z)},\qquad
F_z(u)=S((S^{-1}(u)-\sigma z)/c).
$$
For any $0<t\le1$, on $0<R(z)\le t$, positivity of the Stieltjes measure and $F_z(0)=0$ imply
$$
\begin{aligned}
D(z)&=\frac q2\frac{F_z(qR(z))}{qR(z)}\\
&\le\frac q2\int_{(0,qR(z)]}u^{-1}\,dF_z(u)
\le\frac q2\int_{(0,qt]}u^{-1}\,dF_z(u).
\end{aligned}
$$
Since $0\le D\le1$, this yields pointwise, and hence after integration,
$$
\mathbb E[D\mathbf1_{\{0<R\le t\}}]
\le\mathbb E_Z\min\left\{1,\frac q2\int_{(0,qt]}u^{-1}\,dF_Z(u)\right\}
\le B_{q,\sigma}(t).
$$
The asserted vanishing also holds. For each finite $z$, changing variables $u=S(w)$ gives
$$
\int_{(0,qt]}u^{-1}\,dF_z(u)
=\int_{u_q(t)}^\infty\frac{\phi((w-\sigma z)/c)}{cS(w)}\,dw.
$$
For $w\ge1$, the elementary bound $S(w)\ge e^{-3/2}\phi(w)/w$ follows by integrating $\phi$ over $[w,w+1/w]$. The integrand is therefore bounded by a constant depending on $z$ times
$$
w\exp\left\{-\frac{\sigma^2}{2c^2}w^2+\frac{\sigma z}{c^2}w\right\},
$$
which is integrable at infinity because $c^2=1-\sigma^2<1$. Its tail tends to zero as $t\downarrow0$. Dominated convergence after the outer minimum with one proves $B_{q,\sigma}(t)\to0$. The positive-rank extreme does not violate the proposed microscopic inequality.

## Failure

NOT fails: even though the polynomial false tail forces a positive actual rank at every finite common-noise value, the true Gaussian numerator satisfies the claimed microscopic bound, with an additional factor $1/2$.
